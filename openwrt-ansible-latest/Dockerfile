FROM openwrtorg/rootfs:latest
MAINTAINER Sebastian Gumprich

RUN mkdir -p /var/lock && \
    opkg update && \
    opkg list-upgradable | cut -f 1 -d ' ' | xargs opkg upgrade && \
    opkg install python3 python3-pip python3-cryptography

RUN pip3 install ansible

RUN opkg remove python3-pip --autoremove && \
    rm -rf /tmp/*

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
