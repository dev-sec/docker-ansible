FROM oraclelinux:7-slim
MAINTAINER Sebastian Gumprich

# Add Oracle EPEL repo that contains Ansible
RUN yum-config-manager --add-repo=http://yum.oracle.com/repo/OracleLinux/OL7/developer_EPEL/x86_64/

# Install Ansible and other requirements.
RUN yum makecache fast \
 && yum -y update \
 && yum -y install --enablerepo=* \
      sudo \
      which \
      ansible \
      systemd \
 && yum clean all

RUN rm -rf /var/cache/yum;

# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

VOLUME ["/sys/fs/cgroup"]
CMD [ "ansible-playbook", "--version" ]
