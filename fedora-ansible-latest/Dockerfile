FROM fedora/systemd-systemd:latest
LABEL maintainer="Sebastian Gumprich"

RUN dnf -y update \
    && dnf -y install ansible python python3-libselinux \
    && dnf clean all

RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
