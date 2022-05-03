```bash
docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions
```

```bash
sudo nano /etc/docker/daemon.json
```

```json
{
    "log-driver": "loki",
    "log-opts": {
        "loki-url": "http://localhost:3100/loki/api/v1/push",
        "loki-batch-size": "400"
    }
}
```
```bash
sudo systemctl restart docker
```
