FROM amazonlinux
MAINTAINER Sebastian Gumprich

# Install Ansible and other requirements.
RUN rpm -ihv http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

RUN yum makecache fast && \
    yum -y install deltarpm && \
    yum -y update && \
    yum -y install ansible sysvinit initscripts --enablerepo=epel && \
    yum clean metadata && \
    yum clean all

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
