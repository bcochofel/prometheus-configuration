# Prometheus, Alertmanager, Pushgateway, Grafana, Alerta and Karma

This repository can be used to create a monitoring stack based on the following components:

- Prometheus
- Alertmanager
- Pushgateway
- Grafana
- Alerta
- Karma

There's a ```docker-compose``` that can be used to deploy every component using docker.

## Prometheus

Prometheus configuration collects metrics from Alertmanager, Karma, Pushgateway and Grafana using static config.
If you want to add targets from node_exporter or telegraf you can create the following files under ```/etc/prometheus```:

- /etc/prometheus/node_exporter-targets.json
- /etc/prometheus/telegraf-targets.json

Rules are under ```./prometheus/rules```.

There's a file ```prometheus-consul.yml``` that uses Consul has a Service Discovery and also creates job name.
For this to be done automatically you just need to register the service on Consul and add the ```prometheus``` tag.

## Alertmanager

## Pushgateway

## Grafana

## Alerta

## Karma

# High-Availability

# External Links

- [Prometheus](https://github.com/prometheus/prometheus)
- [Alertmanager](https://prometheus.io/docs/alerting/alertmanager/)
- [Pushgateway](https://github.com/prometheus/pushgateway)
- [Grafana](https://grafana.com/)
- [Alerta](https://alerta.io/)
- [Karma](https://github.com/prymitive/karma)
