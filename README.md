# single-k8s-ansible

Create a single-node [Kubernetes](https://kubernetes.io/) cluster using [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Provision using Vagrant

Requirements:

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Let Vagrant handle everything

```bash
vagrant up
```

[![asciicast](https://asciinema.org/a/K47rwH7J6VCNAWxGp4qEmoyVH.svg)](https://asciinema.org/a/K47rwH7J6VCNAWxGp4qEmoyVH)

## Provision Directly via Ansible

```bash
INVENTORY_HOST=192.168.1.100
SSH_USER=bob
KEY_FILE_PATH="/home/${USER}/.ssh/id_rsa"

ansible-playbook \
  -i "${INVENTORY_HOST}", \
  -u "${SSH_USER}" \
  --private-key "${KEY_FILE_PATH}" \
  playbook.yml
```

[![asciicast](https://asciinema.org/a/470229.svg)](https://asciinema.org/a/470229)
