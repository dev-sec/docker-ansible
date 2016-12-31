FROM ubuntu:16.04
MAINTAINER Sebastian Gumprich


# Install dependencies.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       python-yaml python-jinja2 python-httplib2 python-paramiko python-pkg-resources libffi-dev \
       software-properties-common \
       python-software-properties \
       python-pip python-dev \
       python-setuptools \
       build-essential python-all-dev python-mysqldb sshpass \
    && rm -rf /var/lib/apt/lists/* \
    && rm -Rf /usr/share/doc && rm -Rf /usr/share/man \
    && apt-get clean

# Install Ansible.
RUN pip install wheel
RUN pip install ansible==1.9.6

RUN rm -rf /var/lib/apt/lists/* \
    && rm -Rf /usr/share/doc && rm -Rf /usr/share/man \
    && touch -m -t 200101010101.01 /var/lib/apt/lists \
	&& apt-get remove -y python-pip python-dev python-httplib2 python-paramiko python-pkg-resources libffi-dev \
    && rm -rf /var/lib/apt/lists/* \
    && rm -Rf /usr/share/doc && rm -Rf /usr/share/man \
    && apt-get clean \
    && apt-get -y autoremove

# Install Ansible inventory file
RUN mkdir /etc/ansible/
RUN echo "[local]\nlocalhost ansible_connection=local" > /etc/ansible/hosts

CMD [ "ansible-playbook", "--version" ]
