FROM alpine:latest
MAINTAINER Sebastian Gumprich

RUN apk add --update ansible

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
