# Prometheus, Alertmanager, Pushgateway, Grafana, Alerta and Karma

This repository can be used to create a monitoring stack based on the following components:

- Prometheus
- Alertmanager
- Pushgateway
- Grafana
- Alerta
- Karma

There's a ```docker-compose``` that can be used to deploy every component using docker.
All the services on the ```docker-compose``` have health-checks.

## Prometheus

Prometheus configuration collects metrics from Alertmanager, Karma, Pushgateway and Grafana using static config.
If you want to add targets from node_exporter or telegraf you can create the following files under ```./prometheus```:

- ./prometheus/node_exporter-targets.json
- ./prometheus/telegraf-targets.json

Rules are under ```./prometheus/rules```.

There's a file ```prometheus-consul.yml``` that uses Consul has a Service Discovery and also creates job name.
For this to be done automatically you just need to register the service on Consul and add the ```prometheus``` tag.

Prometheus is listening on port 9090.

## Alertmanager

The default configuration sends alerts using webhooks to Alerta and Karma gets also alerts from Alertmanager automatically.
For Slack integration change the ```alertmanager/alertmanager.yml``` file.

Alertmanager is listening on port 9093.

## Pushgateway

The Pushgateway has the default configuration.

Pushgateway is listening on port 9091.

## Grafana

Grafana is provisioned with datasource for Prometheus and some dashboards.

Grafana is listening on port 3000.

## Alerta

Default configuration with MongoDB has database.

Alerta is listening on port 8088.

## Karma

Default configuration gets alerts from Alertmanager.

Karma is listening on port 8080.

# Long-Term-Storage

If you want to have LTS install M3DB, uncomment prometheus.yml configuration and change the M3DB server.

# TODO

- Alerta health-check
- MongoDB health-check
- Alerta prometheus metrics

# External Links

- [Prometheus](https://github.com/prometheus/prometheus)
- [Alertmanager](https://prometheus.io/docs/alerting/alertmanager/)
- [Pushgateway](https://github.com/prometheus/pushgateway)
- [Node Exporter](https://github.com/prometheus/node_exporter)
- [Telegraf](https://www.influxdata.com/time-series-platform/telegraf/)
- [Provisioning Grafana](https://grafana.com/docs/administration/provisioning/)
- [Alerta](https://alerta.io/)
- [Karma](https://github.com/prymitive/karma)
- [M3DB Single Node Deployment](https://m3db.github.io/m3/how_to/single_node/)
- [Reloading Prometheus’ Configuration](https://www.robustperception.io/reloading-prometheus-configuration)
- [Sending alert notifications to multiple destinations](https://www.robustperception.io/sending-alert-notifications-to-multiple-destinations)
