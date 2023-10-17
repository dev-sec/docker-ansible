FROM quay.io/centos/centos:stream9
LABEL maintainer="Sebastian Gumprich"
ENV container=docker

# Install systemd -- See https://hub.docker.com/_/centos/
RUN yum -y update; yum clean all; \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;

# Install Ansible and other requirements.
RUN yum makecache --timer \
 && yum -y install initscripts \
 && yum -y update \
 && yum -y remove python36 \
 && yum -y install \
      sudo \
      which \
      hostname \
      python3-pip \
 && yum clean all

# upgrade pip because of the rust dependency error
RUN python3 -m pip install --no-cache-dir --upgrade pip && \
   pip3 install --no-cache-dir ansible

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
