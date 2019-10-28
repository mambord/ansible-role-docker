# ansible-role-docker
This role installs docker on a Debian system. Also it is aware of services installed by [ansible-role-iptables](https://github.com/mambord/ansible-role-iptables).

### Docker installation
Default values used for the installation:

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
### Docker compose
docker-compose is installed with pip, because the ansible module [docker_compose](https://docs.ansible.com/ansible/latest/modules/docker_compose_module.html ) does currently not work with docker-compose installed from apt.

```yaml
docker_compose: no
```

### Docker SDK for Python
Docker SDK for Python is used by ansibles [docker_compose](https://docs.ansible.com/ansible/latest/modules/docker_compose_module.html ) module.
```yaml
docker_sdk_python: no
```

### Docker user

Define a list with users that are added to the docker group:

```yaml
docker_user:
  - peter
  - markus
```

### Insecure registries
Define a list with insecure registries:
```yaml
docker_insecure_registries:
  - registry.example.com:5000
  - myregistry.com:5000
```
Have a look at https://docs.docker.com/registry/insecure/ for more informations.
