FROM centos:6
MAINTAINER Sebastian Gumprich

# Install Ansible and other requirements.
RUN yum makecache fast && \
    yum -y install deltarpm epel-release initscripts yum-utils && \
    yum-config-manager --add-repo=https://releases.ansible.com/ansible/rpm/release/epel-6-x86_64/ && \
    yum-config-manager --save --setopt=releases.ansible.com_ansible_rpm_release_epel-6-x86_64_.gpgkey=https://releases.ansible.com/keys/RPM-GPG-KEY-ansible-release.pub && \
    yum -y update && \
    yum -y install \
      ansible \
      sudo \
      which && \
    yum clean all

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
