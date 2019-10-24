# ansible-role-docker
This role installs docker on a Debian system. Also it is aware of services installed by [ansible-role-iptables](https://github.com/mambord/ansible-role-iptables).

### Default values

```yaml
docker_requirements:
  - apt-transport-https
  - ca-certificates
  - curl
  - gnupg2
  - software-properties-common

docker_packages:
  - docker-ce
  - docker-ce-cli
  - containerd.io

docker_gpg_key_url: https://download.docker.com/linux/debian/gpg
docker_gpg_key_fingerprint: 9DC858229FC7DD38854AE2D88D81803C0EBFCD88

docker_repository: deb [arch=amd64] https://download.docker.com/linux/debian buster stable
```
### Docker user

Define a list with user that are added to docker group:

```yaml
docker_user:
  - peter
  - markus
```
