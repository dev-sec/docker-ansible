FROM debian:buster
LABEL maintainer="Sebastian Gumprich"

RUN apt-get update -y  &&  apt-get install -y --fix-missing && \
    DEBIAN_FRONTEND=noninteractive \
    apt-get install -y \
      python python-yaml sudo \
      curl gcc python-pip python-dev libffi-dev libssl-dev systemd && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir --upgrade cffi && \
    pip install --no-cache-dir ansible

RUN apt-get -f -y --auto-remove remove \
      gcc python-pip python-dev libffi-dev libssl-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /usr/share/doc /usr/share/man

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

# https://molecule.readthedocs.io/en/latest/examples.html#docker-with-non-privileged-user
# Create `ansible` user with sudo permissions and membership in `DEPLOY_GROUP`
# This template gets rendered using `loop: "{{ molecule_yml.platforms }}"`, so
# each `item` is an element of platforms list from the molecule.yml file for this scenario.
ENV ANSIBLE_USER=ansible DEPLOY_GROUP=deployer SUDO_GROUP=sudo
RUN set -xe \
  && groupadd -r ${ANSIBLE_USER} \
  && groupadd -r ${DEPLOY_GROUP} \
  && useradd -m -g ${ANSIBLE_USER} ${ANSIBLE_USER} \
  && usermod -aG ${SUDO_GROUP} ${ANSIBLE_USER} \
  && usermod -aG ${DEPLOY_GROUP} ${ANSIBLE_USER} \
  && sed -i "/^%${SUDO_GROUP}/s/ALL\$/NOPASSWD:ALL/g" /etc/sudoers

# Make sure systemd doesn't start agettys on tty[1-6].
RUN rm -f /lib/systemd/system/multi-user.target.wants/getty.target

# delete file created by systemd that prevents login via ssh
RUN rm -f /{var/run,etc,run}/nologin

CMD [ "ansible-playbook", "--version" ]
