# Ansible Role: Elasticsearch [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![pipeline status](https://gitlab.effenco.com/infrastructure/ansible-roles/elasticsearch/badges/master/pipeline.svg)](https://gitlab.effenco.com/infrastructure/ansible-roles/elasticsearch/commits/master)

# TODO: ADDAPT THE README!

Install a dockerized version of Elasticsearch on an host.

## Role Dependancies

- Docker deployed on the host (Tested with [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker/))

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
---
# The docker image and version used to create the service
elasticsearch_docker_image: docker.elastic.co/elasticsearch/elasticsearch-oss
elasticsearch_version: 7.2.0

# The name of the service / container
elasticsearch_docker_name: es
elasticsearch_docker_hostname: "{{ elasticsearch_docker_name }}"

# If the service have to be started
elasticsearch_enabled: true

# The docker network in which to add the container
elasticsearch_docker_network: elk

# Http network bind settings
elasticsearch_http_host: 0.0.0.0
elasticsearch_http_port: 9200

# Name of the elasticsearch cluster
elasticsearch_cluster_name: effenco-elk-cluster

# Root directory of elasticsearch
elasticsearch_path: /opt/elasticsearch
```

- `elasticsearch_docker_image`: The origin image you want to use.

- `elasticsearch_version`: The version of Elasticsearch you want to install.

- `elasticsearch_docker_name`: The name of the docker container and service.

- `elasticsearch_docker_hostname`: The hostname of the docker inside of the docker network.

- `elasticsearch_enabled`: If the service is enabled or not.

- `elasticsearch_docker_network`: The name of the docker network to join.

- `elasticsearch_http_host`: The hostname to expose for http.

- `elasticsearch_http_port`: The port to expose for http.

- `elasticsearch_cluster_name`: The name of the Elasticsearch cluster.

- `elasticsearch_path`: The path to elasticsearch on the host.

## Example Playbook

This is an example of how to use this role:

```yaml
    - hosts: monitoring
        roles:
            - docker
            - { role: elasticsearch }
```

## License

MIT
