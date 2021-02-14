# Ansible Collection - wtu.apps

Compile all applications for Worship the Useless.

Installed with docker-compose.

Applications:
* Traefik: Reverse proxy (TLS termination, forward trafik to other apps)
* Nextcloud: Files sharing with web UI
* Grafana: dashboard web UI for metrics & logs
* Matomo: website statistics
* Fluent-bit: log collector
* Loki: log database
* cAdvisor: metrics collector for dockers
* Prometheus: metrics database

## Installation

All applications can be installed on diffent servers, except some applications that you should install on all servers:
* fluent-bit: local log collector
* cAdvisor: local docker metrics collector

## Run tests

Run local tests:

```
ansible-playbook -i tests/hosts tests/test.yml --limit local
```
