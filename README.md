# Ansible Role: Elasticsearch [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![pipeline status](https://gitlab.effenco.com/infrastructure/ansible-roles/elasticsearch/badges/master/pipeline.svg)](https://gitlab.effenco.com/infrastructure/ansible-roles/elasticsearch/commits/master)

# TODO: ADDAPT THE README!

Install a dockerized version of Elasticsearch on an host.

## Role Dependancies

- Docker deployed on the host (Tested with [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker/))

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
---
MOTD_CONTACT: sysadmin@lanets.ca

# Name of the interfaces to read the Ip address.
MOTD_PRIVATE_INTERFACE: x
MOTD_PUBLIC_INTERFACE: x

# Welcome message and font. Select a font here: http://www.figlet.org/fontdb.cgi
MOTD_WELCOME_FONT: banner3
MOTD_WELCOME: DHMTL

# Users to disable default motd
users: []
```

- `MOTD_CONTACT`: The contact email address to show.

- `MOTD_PRIVATE_INTERFACE`: Network interface you want to read the private Ip address to show.

- `MOTD_PUBLIC_INTERFACE`: Network interface you want to read the public Ip address to show.

> Set the network interface to *x* or do not set it for no interface.

- `MOTD_WELCOME_FONT`: The font of the welcome word. (Select a font on the [Figlet Website](http://www.figlet.org/fontdb.cgi))

- `MOTD_WELCOME`: The welcome word.

- `users`: Global variable containing all the users. Will disable the default motd on all listed users.

## Example Playbook

This is an example of how to use this role:

```yaml
    - hosts: servers
        roles:
            - docker
            - { role: elasticsearch }
```

## License

MIT
