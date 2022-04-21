FROM debian:bullseye
LABEL maintainer="Sebastian Gumprich"

RUN apt-get update -y && apt-get install -y --no-install-recommends --fix-missing && \
    DEBIAN_FRONTEND=noninteractive \
    apt-get install -y --no-install-recommends \
      python3 python3-yaml sudo \
      curl gcc python3-pip python3-dev libffi-dev libssl-dev systemd
RUN pip install --no-cache-dir --upgrade cffi && \
    pip install --no-cache-dir ansible

RUN apt-get -f -y --auto-remove remove \
      gcc python3-pip python3-dev libffi-dev libssl-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /usr/share/doc /usr/share/man

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
