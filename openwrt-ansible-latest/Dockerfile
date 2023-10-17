FROM openwrt/rootfs:latest
LABEL maintainer="Sebastian Gumprich"

RUN mkdir -p /var/lock && \
    opkg update && \
    if [[ $(opkg list-upgradable) ]]; then opkg list-upgradable | cut -f 1 -d ' ' | xargs opkg upgrade; fi && \
    opkg install python3 python3-pip python3-cryptography \
    sudo bash sed shadow-su shadow-groupadd shadow-useradd shadow-usermod

RUN pip3 install --no-cache-dir --upgrade pip && \
    pip3 install --no-cache-dir ansible

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

# https://molecule.readthedocs.io/en/latest/examples.html#docker-with-non-privileged-user
# Create `ansible` user with sudo permissions and membership in `DEPLOY_GROUP`
# This template gets rendered using `loop: "{{ molecule_yml.platforms }}"`, so
# each `item` is an element of platforms list from the molecule.yml file for this scenario.
ENV ANSIBLE_USER=ansible DEPLOY_GROUP=deployer SUDO_GROUP=sudo
RUN set -xe \
    && groupadd -r ${ANSIBLE_USER} \
    && groupadd -r ${SUDO_GROUP} \
    && groupadd -r ${DEPLOY_GROUP} \
    && useradd -m -g ${ANSIBLE_USER} ${ANSIBLE_USER} \
    && usermod -aG ${SUDO_GROUP} ${ANSIBLE_USER} \
    && usermod -aG ${DEPLOY_GROUP} ${ANSIBLE_USER} \
    && sed -i "/^%${SUDO_GROUP}/s/ALL\$/NOPASSWD:ALL/g" /etc/sudoers

RUN opkg remove --autoremove \
    python3-pip shadow-groupadd shadow-useradd shadow-usermod sed

# delete file created by systemd that prevents login via ssh
RUN rm -f /{var/run,etc,run}/nologin

CMD [ "ansible-playbook", "--version" ]
