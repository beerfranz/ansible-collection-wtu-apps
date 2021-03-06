# Ansible Collection - beerfranz.wtu_apps

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
* Prometheus Node Exporter: metrics collector for server
* Prometheus: metrics database

## Usage

All applications can be installed on diffent servers, except some applications that you should install on all servers:
* fluent-bit: local log collector
* cAdvisor: local docker metrics collector
* Prometheus Node Exporter: local system metrics collector

`ansible-galaxy collection install beerfranz.wtu_apps`

Playbook example:
```
---
- name: install cAdvisor, fluent-bit, traefik and nextcloud
  hosts: all
  tasks:
    - name: install cadvisor
      import_role:
        name: beerfranz.wtu_apps.cadvisor
    - name: install fluent-bit
      import_role:
        name: beerfranz.wtu_apps.fluent_bit
    - name: install traefik
      import_role:
        name: beerfranz.wtu_apps.traefik
    - name: install nextcloud
      import_role:
        name: beerfranz.wtu_apps.nextcloud
```

## Run tests

Run local tests:

```
ansible-playbook -i tests/hosts tests/test.yml --limit local
```
