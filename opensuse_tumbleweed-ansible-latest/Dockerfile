FROM opensuse/tumbleweed:latest
MAINTAINER Sebastian Gumprich
ENV container=docker

RUN zypper install -y python ansible dbus-1 systemd-sysvinit shadow

RUN cp /usr/lib/systemd/system/dbus.service /etc/systemd/system/; \
    sed -i 's/OOMScoreAdjust=-900//' /etc/systemd/system/dbus.service

# Install Ansible inventory file.
RUN mkdir -p /etc/ansible
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

VOLUME ["/sys/fs/cgroup", "/run"]
CMD [ "ansible-playbook", "--version" ]
