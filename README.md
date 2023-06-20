# Summary
These are Docker containers that include ansible latest stable Ansible version.

They are meant for testing purposes and are mainly used for [dev-sec](https://github.com/dev-sec/) and the [ansible-test-framework](https://github.com/rndmh3ro/ansible-test-framework).

# Container

| Base operating system             | Dockerfile                                    | Container Image                                               | Docker Hub                                             |
|-----------------------------------|-----------------------------------------------|---------------------------------------------------------------|--------------------------------------------------------|
| [CentOS 7][centos]                | [docker-centos7-ansible-latest][]             | [ghcr.io/dev-sec/docker-centos7-ansible-latest][]             | [rndmh3ro/docker-centos7-ansible-latest][]             |
| [CentOS 8][centos]                | [docker-centos8-ansible-latest][]             | [ghcr.io/dev-sec/docker-centos8-ansible-latest][]             | [rndmh3ro/docker-centos8-ansible-latest][]             |
| [CentOS Stream 8][centos]         | [docker-centosstream8-ansible-latest][]       | [ghcr.io/dev-sec/docker-centosstream8-ansible-latest][]       | [rndmh3ro/docker-centosstream8-ansible-latest][]       |
| [CentOS Stream 9][centos]         | [docker-centosstream9-ansible-latest][]       | [ghcr.io/dev-sec/docker-centosstream9-ansible-latest][]       | [rndmh3ro/docker-centosstream9-ansible-latest][]       |
| [Rocky Linux 8][rocky]            | [docker-rocky8-ansible-latest][]              | [ghcr.io/dev-sec/docker-rocky8-ansible-latest][]              | [rndmh3ro/docker-rocky8-ansible-latest][]              |
| [Rocky Linux 9][rocky ]           | [docker-rocky9-ansible-latest][]              | [ghcr.io/dev-sec/docker-rocky9-ansible-latest][]              | [rndmh3ro/docker-rocky9-ansible-latest][]              |
| [Debian 10][debian]               | [docker-debian10-ansible-latest][]            | [ghcr.io/dev-sec/docker-debian10-ansible-latest][]            | [rndmh3ro/docker-debian10-ansible-latest][]            |
| [Debian 11][debian]               | [docker-debian11-ansible-latest][]            | [ghcr.io/dev-sec/docker-debian11-ansible-latest][]            | [rndmh3ro/docker-debian11-ansible-latest][]            |
| [Debian 12][debian]               | [docker-debian12-ansible-latest][]            | [ghcr.io/dev-sec/docker-debian12-ansible-latest][]            | [rndmh3ro/docker-debian12-ansible-latest][]            |
| [Oracle 7][oracle]                | [docker-oracle7-ansible-latest][]             | [ghcr.io/dev-sec/docker-oracle7-ansible-latest][]             | [rndmh3ro/docker-oracle7-ansible-latest][]             |
| [Ubuntu 18.04][ubuntu]            | [docker-ubuntu1804-ansible-latest][]          | [ghcr.io/dev-sec/docker-ubuntu1804-ansible-latest][]          | [rndmh3ro/docker-ubuntu1804-ansible-latest][]          |
| [Ubuntu 20.04][ubuntu]            | [docker-ubuntu2004-ansible-latest][]          | [ghcr.io/dev-sec/docker-ubuntu2004-ansible-latest][]          | [rndmh3ro/docker-ubuntu2004-ansible-latest][]          |
| [Ubuntu 22.04][ubuntu]            | [docker-ubuntu2204-ansible-latest][]          | [ghcr.io/dev-sec/docker-ubuntu2204-ansible-latest][]          | [rndmh3ro/docker-ubuntu2204-ansible-latest][]          |
| [Alpine][alpine]                  | [docker-alpine-ansible-latest][]              | [ghcr.io/dev-sec/docker-alpine-ansible-latest][]              | [rndmh3ro/docker-alpine-ansible-latest][]              |
| [Amazon Linux 2][amazon]          | [docker-amazon2-ansible-latest][]             | [ghcr.io/dev-sec/docker-amazon2-ansible-latest][]             | [rndmh3ro/docker-amazon2-ansible-latest][]             |
| [Amazon Linux 2023][amazon]       | [docker-amazon2023-ansible-latest][]          | [ghcr.io/dev-sec/docker-amazon2023-ansible-latest][]          | [rndmh3ro/docker-amazon2023-ansible-latest][]          |
| [Fedora 37][fedora]               | [docker-fedora37-ansible-latest][]            | [ghcr.io/dev-sec/docker-fedora37-ansible-latest][]            | [rndmh3ro/docker-fedora37-ansible-latest][]            |
| [Fedora 38][fedora]               | [docker-fedora38-ansible-latest][]            | [ghcr.io/dev-sec/docker-fedora38-ansible-latest][]            | [rndmh3ro/docker-fedora38-ansible-latest][]            |
| [OpenSuse Tumbleweed][tumbleweed] | [docker-opensuse_tumbleweed-ansible-latest][] | [ghcr.io/dev-sec/docker-opensuse_tumbleweed-ansible-latest][] | [rndmh3ro/docker-opensuse_tumbleweed-ansible-latest][] |
| [Arch Linux][arch]                | [docker-arch-ansible-latest][]                | [ghcr.io/dev-sec/docker-arch-ansible-latest][]                | [rndmh3ro/docker-arch-ansible-latest][]                |
| [OpenWRT][openwrt]                | [docker-openwrt-ansible-latest][]             | [ghcr.io/dev-sec/docker-openwrt-ansible-latest][]             | [rndmh3ro/docker-openwrt-ansible-latest][]             |

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
[docker-centos7-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centos7-ansible-latest/Dockerfile
[docker-centos8-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centos8-ansible-latest/Dockerfile
[docker-centosstream8-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centosstream8-ansible-latest/Dockerfile
[docker-centosstream9-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/centosstream9-ansible-latest/Dockerfile
[docker-rocky8-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/rocky8-ansible-latest/Dockerfile
[docker-rocky9-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/rocky9-ansible-latest/Dockerfile
[docker-debian10-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/debian10-ansible-latest/Dockerfile
[docker-debian11-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/debian11-ansible-latest/Dockerfile
[docker-debian12-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/debian12-ansible-latest/Dockerfile
[docker-oracle7-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/oracle7-ansible-latest/Dockerfile
[docker-ubuntu1804-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/ubuntu1804-ansible-latest/Dockerfile
[docker-ubuntu2004-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/ubuntu2004-ansible-latest/Dockerfile
[docker-ubuntu2204-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/ubuntu2204-ansible-latest/Dockerfile
[docker-alpine-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/alpine-ansible-latest/Dockerfile
[docker-amazon2-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/amazon2-ansible-latest/Dockerfile
[docker-amazon2023-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/amazon2023-ansible-latest/Dockerfile
[docker-fedora37-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/fedora37-ansible-latest/Dockerfile
[docker-fedora38-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/fedora38-ansible-latest/Dockerfile
[docker-opensuse_tumbleweed-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/opensuse_tumbleweed-ansible-latest/Dockerfile
[docker-arch-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/arch-ansible-latest/Dockerfile
[docker-openwrt-ansible-latest]: https://github.com/rndmh3ro/docker-ansible/blob/master/openwrt-ansible-latest/Dockerfile
[ghcr.io/dev-sec/docker-centos7-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-centos7-ansible
[ghcr.io/dev-sec/docker-centos8-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-centos8-ansible
[ghcr.io/dev-sec/docker-centosstream8-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-centosstream8-ansible
[ghcr.io/dev-sec/docker-centosstream9-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-centosstream0-ansible
[ghcr.io/dev-sec/docker-rocky8-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-rocky8-ansible
[ghcr.io/dev-sec/docker-rocky9-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-rocky9-ansible
[ghcr.io/dev-sec/docker-debian10-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-debian10-ansible
[ghcr.io/dev-sec/docker-debian11-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-debian11-ansible
[ghcr.io/dev-sec/docker-debian12-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-debian12-ansible
[ghcr.io/dev-sec/docker-oracle7-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-oracle7-ansible
[ghcr.io/dev-sec/docker-ubuntu1804-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-ubuntu1804-ansible
[ghcr.io/dev-sec/docker-ubuntu2004-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-ubuntu2004-ansible
[ghcr.io/dev-sec/docker-ubuntu2204-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-ubuntu2204-ansible
[ghcr.io/dev-sec/docker-alpine-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-alpine-ansible
[ghcr.io/dev-sec/docker-amazon2-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-amazon2-ansible
[ghcr.io/dev-sec/docker-amazon2023-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-amazon2023-ansible
[ghcr.io/dev-sec/docker-fedora37-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-fedora37-ansible
[ghcr.io/dev-sec/docker-fedora38-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-fedora38-ansible
[ghcr.io/dev-sec/docker-opensuse_tumbleweed-ansible-latest]: https://hub.docker.com/repository/docker/rndmh3ro/docker-opensuse_tumbleweed-ansible
[ghcr.io/dev-sec/docker-arch-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-arch-ansible
[ghcr.io/dev-sec/docker-openwrt-ansible-latest]: https://github.com/dev-sec/docker-ansible/pkgs/container/docker-openwrt-ansible
[rndmh3ro/docker-centos7-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centos7-ansible
[rndmh3ro/docker-centos8-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centos8-ansible
[rndmh3ro/docker-centosstream8-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centosstream8-ansible
[rndmh3ro/docker-centosstream9-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-centosstream0-ansible
[rndmh3ro/docker-rocky8-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-rocky8-ansible
[rndmh3ro/docker-rocky9-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-rocky9-ansible
[rndmh3ro/docker-debian10-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-debian10-ansible
[rndmh3ro/docker-debian11-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-debian11-ansible
[rndmh3ro/docker-debian12-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-debian12-ansible
[rndmh3ro/docker-oracle7-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-oracle7-ansible
[rndmh3ro/docker-ubuntu1804-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu1804-ansible
[rndmh3ro/docker-ubuntu2004-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu2004-ansible
[rndmh3ro/docker-ubuntu2204-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-ubuntu2204-ansible
[rndmh3ro/docker-alpine-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-alpine-ansible
[rndmh3ro/docker-amazon2-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-amazon2-ansible
[rndmh3ro/docker-amazon2023-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-amazon2023-ansible
[rndmh3ro/docker-fedora37-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-fedora37-ansible
[rndmh3ro/docker-fedora38-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-fedora38-ansible
[rndmh3ro/docker-opensuse_tumbleweed-ansible-latest]: https://hub.docker.com/repository/docker/rndmh3ro/docker-opensuse_tumbleweed-ansible
[rndmh3ro/docker-arch-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-arch-ansible
[rndmh3ro/docker-openwrt-ansible-latest]: https://hub.docker.com/r/rndmh3ro/docker-openwrt-ansible
