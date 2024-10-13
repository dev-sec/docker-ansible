FROM alpine:latest
LABEL maintainer="Sebastian Gumprich"

RUN apk add --no-cache ansible sudo openrc linux-pam openssh-server-pam bash

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

# https://molecule.readthedocs.io/en/latest/examples.html#docker-with-non-privileged-user
# Create `ansible` user with sudo permissions and membership in `DEPLOY_GROUP`
# This template gets rendered using `loop: "{{ molecule_yml.platforms }}"`, so
# each `item` is an element of platforms list from the molecule.yml file for this scenario.
ENV ANSIBLE_USER=ansible DEPLOY_GROUP=deployer SUDO_GROUP=wheel
RUN set -xe \
    && adduser -D ${ANSIBLE_USER} ${DEPLOY_GROUP} \
    && addgroup ${ANSIBLE_USER} ${ANSIBLE_USER} \
    && addgroup ${ANSIBLE_USER} ${SUDO_GROUP} \
    && sed -i "s/^# %${SUDO_GROUP} ALL=(ALL:ALL) NOPASSWD: ALL/%${SUDO_GROUP} ALL=(ALL:ALL) NOPASSWD: ALL/" /etc/sudoers

# delete file created by systemd that prevents login via ssh
RUN rm -f /{var/run,etc,run}/nologin

CMD [ "ansible-playbook", "--version" ]
