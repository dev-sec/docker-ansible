FROM ubuntu:14.04
MAINTAINER Sebastian Gumprich


# Install dependencies.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       software-properties-common \
       python-software-properties \
    && rm -rf /var/lib/apt/lists/* \
    && rm -Rf /usr/share/doc && rm -Rf /usr/share/man \
    && apt-get clean
# Install Ansible.
RUN apt-add-repository -y ppa:ansible/ansible-1.9 \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
       ansible \
    && rm -rf /var/lib/apt/lists/* \
    && rm -Rf /usr/share/doc && rm -Rf /usr/share/man \
    && touch -m -t 200101010101.01 /var/lib/apt/lists \
	&& apt-get clean

# Install Ansible inventory file
RUN echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
