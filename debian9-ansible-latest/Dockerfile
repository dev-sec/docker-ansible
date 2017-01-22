FROM debian:stretch
MAINTAINER Sebastian Gumprich

RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;

RUN apt-get update -y  &&  apt-get install --fix-missing && \
    DEBIAN_FRONTEND=noninteractive \
    apt-get install -y \
      python python-yaml sudo \
      curl gcc python-pip python-dev libffi-dev libssl-dev systemd
RUN pip install --upgrade cffi && \
    pip install ansible

RUN apt-get -f -y --auto-remove remove \
      gcc python-pip python-dev libffi-dev libssl-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /usr/share/doc /usr/share/man

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
