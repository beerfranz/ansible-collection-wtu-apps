# Ansible Collection - wtu.apps

Compile all applications for Worship the Useless.

Installed with docker-compose.

Applications:
* Nextcloud
* Web site
* CRM
* Supervision

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
