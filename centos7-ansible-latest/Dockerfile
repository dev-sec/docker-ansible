FROM centos:7
MAINTAINER Sebastian Gumprich
ENV container=docker
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8


# Install systemd -- See https://hub.docker.com/_/centos/
RUN yum -y update; yum clean all; \
(cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;

# Install requirements.
RUN yum makecache fast && \
    yum -y install deltarpm epel-release initscripts && \
    yum-config-manager --add-repo=https://releases.ansible.com/ansible/rpm/release/epel-7-x86_64/ && \
    yum-config-manager --save --setopt=releases.ansible.com_ansible_rpm_release_epel-7-x86_64_.gpgkey=https://releases.ansible.com/keys/RPM-GPG-KEY-ansible-release.pub && \
    yum -y update && \
    yum -y install \
      sudo \
      python3-pip \
      which && \
    yum clean all

# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Upgrade pip so cryptography package works.
RUN python3 -m pip install --upgrade pip

RUN pip3 install ansible

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
  
VOLUME ["/sys/fs/cgroup"]
CMD [ "ansible-playbook", "--version" ]
