# Monitoring HQ
This repository contains documentation and baseline setup of a Prometheus + Grafana service which is intended to serve as a centralized monitoring and alerting component of the Prior Art Archive.

The repository is driven by docker and involves the following:

1. An instance of [prometheus](https://prometheus.io/) which handles the collection of metrics.
2. (SOON) An instance of [grafana](https://grafana.com/) which handles the rendering of metrics.
3. (SOON) An instance of [alertmanager](https://github.com/prometheus/alertmanager) which triggers alerts based on metric outcomes.

## Setup
We're using [Docker](https://www.docker.com/) and `docker-compose` which will let you set up your own Prometheus server to make improvements and modifications to this repository.

To run the project locally:

```
docker-compose up
```

## Building and Deploying

The project is run on [AWS ECS], which means in order to actually deploy you will need to [install the ecs-cli](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html).

You will also need read access to the following services:

1. [Our Docker organization](https://hub.docker.com/u/priorartarchive): `priorartarchive`
2. An AWS account with permission to interact with ECS

Once you've done that, this is how you would deploy a new version:

```
> docker-compose build
> docker-compose push
> ecs-cli compose service down --cluster prior-art-archive-monitoring
> ecs-cli compose service up --cluster prior-art-archive-monitoring
```

Note that `prior-art-archive-monitoring` can be whatever name you have set up.