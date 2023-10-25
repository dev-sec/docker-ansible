FROM opensuse/tumbleweed:latest
LABEL maintainer="Sebastian Gumprich"
ENV container=docker

RUN zypper install -y python ansible dbus-1 systemd-sysvinit shadow sudo && \
    zypper clean

RUN cp /usr/lib/systemd/system/dbus.service /etc/systemd/system/; \
    sed -i 's/OOMScoreAdjust=-900//' /etc/systemd/system/dbus.service

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
  && groupadd -r ${SUDO_GROUP} \
  && useradd -m -g ${ANSIBLE_USER} ${ANSIBLE_USER} \
  && usermod -aG ${SUDO_GROUP} ${ANSIBLE_USER} \
  && usermod -aG ${DEPLOY_GROUP} ${ANSIBLE_USER} \
  && sed -i "s/^# \(%${SUDO_GROUP} ALL=(ALL:ALL) NOPASSWD: ALL\)/\\1/g" /etc/sudoers

# delete file created by systemd that prevents login via ssh
RUN rm -f /{var/run,etc,run}/nologin

VOLUME ["/sys/fs/cgroup", "/run"]
CMD [ "ansible-playbook", "--version" ]
