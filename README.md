# Ansible Collection - wtu.apps

Compile all applications for Worship the Useless.

Installed with docker-compose.

Applications:
* File sharing: Nextcloud
* Web site
* CRM
* Supervision
  * SuiteCRM

Technical apps:
* Security
  * Traefik: Reverse proxy with TLS termination
* Logs
  * Fluentd: Log collector
  * Loki: Log database
* Metrics
  * cAdvisor: Metrics collector for dockers
  * Prometheus: Metrics database
* Grafana: Web UI for logs & metrics

## Installation

All applications can be installed on diffent servers, except some applications that you should install on all servers:
* fluent-bit: local log collector
* cAdvisor: local docker metrics collector

## Run tests

Run local tests:

```
ansible-playbook -i tests/hosts tests/test.yml --limit local
```
