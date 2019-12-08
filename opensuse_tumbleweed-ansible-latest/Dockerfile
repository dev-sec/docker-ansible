FROM opensuse/tumbleweed:latest
MAINTAINER Sebastian Gumprich
ENV container=docker

RUN zypper install -y python ansible systemd

# Install Ansible inventory file.
RUN mkdir -p /etc/ansible
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

VOLUME ["/sys/fs/cgroup"]
CMD [ "ansible-playbook", "--version" ]
