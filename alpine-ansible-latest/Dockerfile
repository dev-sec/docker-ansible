FROM alpine:latest
MAINTAINER Sebastian Gumprich

RUN apk add --update ansible

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

# delete file created by systemd that prevents login via ssh
RUN rm -f /{var/run,etc,run}/nologin

CMD [ "ansible-playbook", "--version" ]
