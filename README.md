# dpi-elk
[![Elastic Stack version](https://img.shields.io/badge/Elastic%20Stack-8.14.0-00bfb3?style=flat&logo=elastic-stack)](https://www.elastic.co/blog/category/releases)

DPI implementation of using Docker setup for an ELK (ElasticSearch--Logstash--Kibana) stack for geospatial data visualization.

Stand up the current version of the ELK stack with Docker Compose. The aim is primarily to leverage the geodata capabilities of ElasticSearch with the visualization power of Kibana, for integrated maps with dashboards for analysis.

This implementation uses the [current Docker images][elastic-docker] from Elastic:

* [Elasticsearch](https://github.com/elastic/elasticsearch/tree/main/distribution/docker)
* [Logstash](https://github.com/elastic/logstash/tree/main/docker)
* [Kibana](https://github.com/elastic/kibana/tree/main/src/dev/build/tasks/os_packages/docker_generator)

> [!IMPORTANT]
> This implementation is currently built on the Basic licence for the ES stack, to avoid startup on the Trial licence.
> If proceeding, will need to build in licencing parameters in a later version.

---

## Containerize the following (or run individually in early testing until Container is created)

Set up a Ubuntu VM on GCP and in the SSH:
```sh
apt update
apt upgrade
apt-get install -y docker
apt-get install -y docker-compose git
apt update
git clone https://github.com/the-epeecurean/dpi-elk.git
cd dpi-elk
chown -R $(whoami):root dpi-elk/
docker-compose up setup
docker-compose up
```

