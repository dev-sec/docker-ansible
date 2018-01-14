FROM amazonlinux
MAINTAINER Sebastian Gumprich

# Install Ansible and other requirements.
RUN yum makecache fast && \
    yum -y install deltarpm epel-release && \
    yum-config-manager --enable epel && \
    yum -y update && \
    yum -y install ansible sysvinit initscripts && \
    yum clean metadata && \
    yum clean all

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
