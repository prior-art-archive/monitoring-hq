# Monitoring HQ
This repository contains documentation and baseline setup of a Prometheus + grafana service which is intended to serve as a centralized monitoring and alerting component of the Prior Art Archive.

The repository is driven by docker and involves the following:

1. An instance of [prometheus](https://prometheus.io/) which handles the collection of metrics.
2. An instance of [grafana](https://grafana.com/) which handles the rendering of metrics.
3. An instance of [alertmanager](https://github.com/prometheus/alertmanager) which triggers alerts based on metric outcomes.

## Setup
