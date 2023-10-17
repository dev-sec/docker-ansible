FROM amazonlinux:2023
LABEL maintainer="Sebastian Gumprich"

# Install Ansible and other requirements.
RUN yum makecache --timer && \
    yum -y install initscripts && \
    yum -y update && \
    yum -y install \
      sudo \
      which \
      hostname \
      python3 \
      python3-pip && \
    yum clean all

RUN pip3 install --no-cache-dir ansible

# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
RUN mkdir -p /etc/ansible && \
    echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

# https://molecule.readthedocs.io/en/latest/examples.html#docker-with-non-privileged-user
# Create `ansible` user with sudo permissions and membership in `DEPLOY_GROUP`
# This template gets rendered using `loop: "{{ molecule_yml.platforms }}"`, so
# each `item` is an element of platforms list from the molecule.yml file for this scenario.
ENV ANSIBLE_USER=ansible DEPLOY_GROUP=deployer SUDO_GROUP=wheel
RUN set -xe \
  && groupadd -r ${ANSIBLE_USER} \
  && groupadd -r ${DEPLOY_GROUP} \
  && useradd -m -g ${ANSIBLE_USER} ${ANSIBLE_USER} \
  && usermod -aG ${SUDO_GROUP} ${ANSIBLE_USER} \
  && usermod -aG ${DEPLOY_GROUP} ${ANSIBLE_USER} \
  && sed -i "/^%${SUDO_GROUP}/s/ALL\$/NOPASSWD:ALL/g" /etc/sudoers

# delete file created by systemd that prevents login via ssh
RUN rm -f /{var/run,etc,run}/nologin

VOLUME ["/sys/fs/cgroup"]
CMD [ "ansible-playbook", "--version" ]
