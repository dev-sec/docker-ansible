FROM oraclelinux:6
MAINTAINER Sebastian Gumprich

# Install Ansible and other requirements.
RUN yum makecache fast \
 && yum -y install deltarpm epel-release initscripts wget

RUN wget http://mirror.de.leaseweb.net/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN rpm -ihv epel-release-6-8.noarch.rpm

RUN yum -y update \
 && yum -y install \
      ansible \
      sudo \
      which \
 && yum clean all

# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
