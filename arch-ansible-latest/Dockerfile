FROM archlinux/base:latest
MAINTAINER Sebastian Gumprich

# Update archlinux-keyring.
RUN pacman -S -y \
  && pacman -S --noconfirm \
    archlinux-keyring

# Install glibc, python and Ansible and clear caches.
RUN pacman -S -y \
  && pacman -S --noconfirm \
    glibc \
    python \
    ansible \
  && yes | pacman -Scc || true

# Install Ansible inventory file.
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]