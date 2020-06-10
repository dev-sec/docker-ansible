FROM archlinux/base:latest
MAINTAINER Sebastian Gumprich

# Update, install sudo and systemd, cleanup and remove unneeded unit files.
RUN  pacman -S -y \
  && pacman -S --noconfirm \
    sudo \
    systemd \
  && \
  (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -vf $i; done); \
    rm -vf /lib/systemd/system/multi-user.target.wants/*; \
    rm -vf /etc/systemd/system/*.wants/*; \
    rm -vf /lib/systemd/system/local-fs.target.wants/*; \
    rm -vf /lib/systemd/system/sockets.target.wants/*udev*; \
    rm -vf /lib/systemd/system/sockets.target.wants/*initctl*; \
    rm -vf /lib/systemd/system/basic.target.wants/*;

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

# Switch default target from graphical to multi-user.
RUN systemctl set-default multi-user.target

CMD [ "ansible-playbook", "--version" ]