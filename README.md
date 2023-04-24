# Summary
These are Docker containers that include ansible latest stable Ansible version.

They are meant for testing purposes and are mainly used for [dev-sec](https://github.com/dev-sec/) and the [ansible-test-framework](https://github.com/rndmh3ro/ansible-test-framework).

# Container

| Base operating system             | Github                                        | Docker Hub                                             |
| --------------------------------- | --------------------------------------------- |------------------------------------------------------- |
| [CentOS 7][centos]                | [docker-centos7-ansible-latest][]             | [rndmh3ro/docker-centos7-ansible-latest][]             |
| [CentOS 8][centos]                | [docker-centos8-ansible-latest][]             | [rndmh3ro/docker-centos8-ansible-latest][]             |
| [CentOS Stream 8][centos]         | [docker-centosstream8-ansible-latest][]        | [rndmh3ro/docker-centosstream8-ansible-latest][]      |
| [CentOS Stream 9][centos]         | [docker-centosstream9-ansible-latest][]       | [rndmh3ro/docker-centosstream9-ansible-latest][]       |
| [Rocky Linux 8][centos]           | [docker-rocky8-ansible-latest][]              | [rndmh3ro/docker-rocky8-ansible-latest][]              |
| [Rocky Linux 9][centos]           | [docker-rocky9-ansible-latest][]              | [rndmh3ro/docker-rocky9-ansible-latest][]              |
| [Debian 10][debian]               | [docker-debian10-ansible-latest][]            | [rndmh3ro/docker-debian10-ansible-latest][]            |
| [Oracle 7][oracle]                | [docker-oracle7-ansible-latest][]             | [rndmh3ro/docker-oracle7-ansible-latest][]             |
| [Ubuntu 18.04][ubuntu]            | [docker-ubuntu1804-ansible-latest][]          | [rndmh3ro/docker-ubuntu1804-ansible-latest][]          |
| [Ubuntu 20.04][ubuntu]            | [docker-ubuntu2004-ansible-latest][]          | [rndmh3ro/docker-ubuntu2004-ansible-latest][]          |
| [Ubuntu 22.04][ubuntu]            | [docker-ubuntu2204-ansible-latest][]          | [rndmh3ro/docker-ubuntu2204-ansible-latest][]          |
| [Alpine][alpine]                  | [docker-alpine-ansible-latest][]              | [rndmh3ro/docker-alpine-ansible-latest][]              |
| [Amazon Linux][amazon]            | [docker-amazon-ansible-latest][]              | [rndmh3ro/docker-amazon-ansible-latest][]              |
| [Amazon Linux 2][amazon]          | [docker-amazon2-ansible-latest][]             | [rndmh3ro/docker-amazon2-ansible-latest][]             |
| [Amazon Linux 2023][amazon]       | [docker-amazon2023-ansible-latest][]          | [rndmh3ro/docker-amazon2023-ansible-latest][]          |
| [Fedora][fedora]                  | [docker-fedora-ansible-latest][]              | [rndmh3ro/docker-fedora-ansible-latest][]              |
| [OpenSuse Tumbleweed][tumbleweed] | [docker-opensuse_tumbleweed-ansible-latest][] | [rndmh3ro/docker-opensuse_tumbleweed-ansible-latest][] |
| [Arch Linux][arch]                | [docker-arch-ansible-latest][]                | [rndmh3ro/docker-arch-ansible-latest][]                |
| [OpenWRT][openwrt]                | [docker-openwrt-ansible-latest][]             | [rndmh3ro/docker-openwrt-ansible-latest][]             |

# Author

Sebastian Gumprich <github@gumpri.ch>

[centos]: https://hub.docker.com/_/centos/
[rocky]: https://hub.docker.com/r/rockylinux/
[debian]: https://hub.docker.com/_/debian/
[oracle]: https://hub.docker.com/_/oraclelinux/
[ubuntu]: https://hub.docker.com/_/ubuntu/
[alpine]: https://hub.docker.com/_/alpine/
[amazon]: https://hub.docker.com/_/amazonlinux/
[fedora]: https://hub.docker.com/_/fedora/
[arch]: https://hub.docker.com/_/archlinux/
[tumbleweed]: https://hub.docker.com/r/opensuse/tumbleweed
[openwrt]: https://hub.docker.com/r/openwrtorg/rootfs
[docker-centos6-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centos6-ansible-latest/Dockerfile
[docker-centos7-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centos7-ansible-latest/Dockerfile
[docker-centos8-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centos8-ansible-latest/Dockerfile
[docker-centosstream8-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centosstream8-ansible-latest/Dockerfile
[docker-centosstream9-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centosstream9-ansible-latest/Dockerfile
[docker-rocky8-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/rocky8-ansible-latest/Dockerfile
[docker-rocky9-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/rocky9-ansible-latest/Dockerfile
[docker-debian10-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/debian10-ansible-latest/Dockerfile
[docker-oracle6-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/oracle6-ansible-latest/Dockerfile
[docker-oracle7-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/oracle7-ansible-latest/Dockerfile
[docker-ubuntu1804-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/ubuntu1804-ansible-latest/Dockerfile
[docker-ubuntu2004-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/ubuntu2004-ansible-latest/Dockerfile
[docker-ubuntu2204-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/ubuntu2204-ansible-latest/Dockerfile
[docker-alpine-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/alpine-ansible-latest/Dockerfile
[docker-amazon2-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/amazon2-ansible-latest/Dockerfile
[docker-amazon2023-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/amazon2023-ansible-latest/Dockerfile
[docker-fedora-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/fedora-ansible-latest/Dockerfile
[docker-opensuse_tumbleweed-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/opensuse_tumbleweed-ansible-latest/Dockerfile
[docker-arch-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/arch-ansible-latest/Dockerfile
[docker-openwrt-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/openwrt-ansible-latest/Dockerfile
[rndmh3ro/docker-centos6-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centos6-ansible
[rndmh3ro/docker-centos7-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centos7-ansible
[rndmh3ro/docker-centos8-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centos8-ansible
[rndmh3ro/docker-centosstream8-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centosstream8-ansible
[rndmh3ro/docker-centosstream9-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centosstream0-ansible
[rndmh3ro/docker-rocky8-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-rocky8-ansible
[rndmh3ro/docker-rocky9-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-rocky9-ansible
[rndmh3ro/docker-debian10-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-debian10-ansible
[rndmh3ro/docker-oracle6-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-oracle6-ansible
[rndmh3ro/docker-oracle7-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-oracle7-ansible
[rndmh3ro/docker-ubuntu1604-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu1604-ansible
[rndmh3ro/docker-ubuntu1804-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu1804-ansible
[rndmh3ro/docker-ubuntu2004-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu2004-ansible
[rndmh3ro/docker-ubuntu2204-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu2204-ansible
[rndmh3ro/docker-alpine-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-alpine-ansible
[rndmh3ro/docker-amazon2-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-amazon2-ansible
[rndmh3ro/docker-amazon2023-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-amazon2023-ansible
[rndmh3ro/docker-fedora-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-fedora-ansible
[rndmh3ro/docker-opensuse_tumbleweed-ansible-latest]: https://hub.docker.com/repository/docker/rndmh3ro/docker-opensuse_tumbleweed-ansible
[rndmh3ro/docker-arch-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-arch-ansible
[rndmh3ro/docker-openwrt-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-openwrt-ansible
