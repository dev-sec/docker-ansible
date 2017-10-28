FROM debian:wheezy
MAINTAINER Sebastian Gumprich

RUN apt-get update -y  &&  apt-get install --fix-missing && \
    DEBIAN_FRONTEND=noninteractive \
    apt-get install -y \
      python python-yaml sudo \
      curl gcc python-dev libffi-dev libssl-dev

RUN curl -o /tmp/get-pip.py https://bootstrap.pypa.io/get-pip.py && python /tmp/get-pip.py
RUN pip install ansible

RUN apt-get -f -y --auto-remove remove \
      gcc python-pip python-dev libffi-dev libssl-dev curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /usr/share/doc /usr/share/man

# Install Ansible inventory file
RUN mkdir -p /etc/ansible \
    && echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
