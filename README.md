# Grafana compose

Runs Grafana + Tempo + Loki. Grafana is preloaded with sources for Tempo, Prometheus (scraping Tempo), and Loki, and has auth disabled. All data is stored locally.

Suitable as is for local development. Production usage can fork the repo and customize for their needs, such as enabling auth on Grafana, and switch another data store like AWS S3 for storage.

- Grafana + Tempo: https://github.com/grafana/tempo/tree/main/example/docker-compose/local

- Loki: https://grafana.com/docs/loki/latest/setup/install/docker/#install-with-docker-compose

## Environment

Use this as the starting point for a custom compose `.env`. It's not required, these values will also be defaulted if not provided.

```shell
GRAFANA_VERSION=latest
GRAFANA_PORT=3000
TEMPO_VERSION=latest
LOKI_VERSION=latest
PROMETHEUS_VERSION=latest
```