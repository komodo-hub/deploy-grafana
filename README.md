# Deploy Grafana

Part of the [Komodo Hub collection.](https://github.com/komodo-hub/komodo-hub)

Runs Grafana + Tempo + Loki. Grafana is preloaded with sources for Tempo, Prometheus (scraping Tempo), and Loki, and has auth disabled. All data is stored locally.

Suitable as is for local development. Production usage can fork the repo and customize for their needs, such as enabling auth on Grafana, and switch another data store like AWS S3 for storage.

- Grafana + Tempo: https://github.com/grafana/tempo/tree/main/example/docker-compose/local

- Loki: https://grafana.com/docs/loki/latest/setup/install/docker/#install-with-docker-compose

## Komodo Resource TOML

```toml
[[stack]]
name = "grafana"
[stack.config]
repo = "komodo-hub/deploy-grafana"
ignore_services = ["tempo-init"]
environment = """
  # Change the port to access Grafana UI
  GRAFANA_PORT = 3000
  # https://docs.docker.com/engine/logging/configure
  LOGGING_DRIVER = local
  # Custom image versions
  GRAFANA_TAG = latest
  TEMPO_TAG = latest
  LOKI_TAG = latest
  PROMETHEUS_TAG = latest
  MEMCACHED_TAG = latest
"""
```