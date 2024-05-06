# vector

A lightweight, ultra-fast tool for building observability pipelines. #log#devops#vector#role#ansible#

## TOC

- [vector](#vector)
  - [TOC](#toc)
  - [Description](#description)
  - [Requirements](#requirements)
  - [Role variables](#role-variables)
  - [License](#license)
  - [Links](#links)


## Description

Role that setup vector daemon in docker.  
Various pre defined templates supported.  

## Requirements

Python3 plus Ansible >=2.9.10 installed on host system (BSD, Linux, MacOS), Python3 and Docker on a target (Linux) system.
Pregenerated SSH Public and Private keys for both. 
User must have sudoers record on target system or better be a root user in moment of rolling Ansible scripts.

## Role variables
| Variable                | Default | Comments             |
|-------------------------|---------|----------------------|
| vector_purge            | no | Purge existing installation |
| vector_image_name       | timberio/vector | Docker image |
| vector_image_version    | 0.23.0-debian | Docker image tag |
| vector_home             | /opt/vector | Host directory to use for app data |
| vector_etc              | {{ vector_home }}/etc | Config location |
| vector_tls              | {{ vector_home }}/tls | Directory to store/use TLS certs |
| vector_data             | {{ vector_home }}/data | Directory to store vector data (local cache, temp files, etc.) |
| vector_container_name   | {{ vector_home \| basename }} | Docker container name |
| vector_template         | templates/etc/vector/default_vector_collector_client.toml.j2 | Configuration template to use |
| vector_publish_ip       | 127.0.0.1 | Host IP to publish container port |
| vector_publish_port     | 8686 | Host port to use |
| vector_publish          | [ ] | A list of ports to publish (optional) |
| vector_systemd_version  | 245 | Major version of systemd running on host (needed for logs gathering) |
| vector_cpus             | 1 | Amount of CPU cores allowed to use |
| vector_memory           | 256M | Memory limit |
| vector_network_mode     | default | Docker network mode |
| vector_recreate         | yes | Force recreate docker container |
| vector_forward_docker   | yes | Enable log forwarding for docker containers |
| vector_forward_journald | yes | Enable system log forwarding |
| vector_volume_custom    | [ ] | Custom volumes |
| vector_autogenerate_tls | no | Generate selfsigned TLS certs |
| vector_state            | started | Container state |
| vector_labels           | {}  | container labels |

## License

Apache-2.0

## Links

* Website: https://vector.dev
* Docs: https://vector.dev/docs
* Chat: https://chat.vector.dev
