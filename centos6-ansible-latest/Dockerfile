FROM centos:6
MAINTAINER Sebastian Gumprich

# Install Ansible and other requirements.
RUN yum makecache fast && \
    yum -y install deltarpm epel-release initscripts && \
    yum -y update && \
    yum -y install \
      ansible \
      sudo \
      which && \
    yum clean all

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
