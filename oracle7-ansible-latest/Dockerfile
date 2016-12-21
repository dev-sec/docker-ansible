FROM oraclelinux:7
MAINTAINER Sebastian Gumprich

# Install Ansible and other requirements.
RUN yum makecache fast \
 && yum -y install deltarpm epel-release initscripts wget

RUN wget http://mirror.de.leaseweb.net/epel/7/x86_64/e/epel-release-7-8.noarch.rpm
RUN rpm -ihv epel-release-7-8.noarch.rpm

RUN yum -y update \
 && yum -y install \
      ansible \
      sudo \
      which \
 && yum clean all

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


# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

VOLUME ["/sys/fs/cgroup"]
CMD [ "ansible-playbook", "--version" ]
