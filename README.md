# truenas-exporter

Prometheus metrics exporter for TrueNAS CORE, packaged for arm64 Kubernetes deployment.

Based on [neilschelly/truenas_exporter](https://github.com/neilschelly/truenas_exporter).

## Metrics

- Pool status and health
- Dataset usage (available/used bytes)
- Disk temperatures (via SMART)
- Interface traffic (rx/tx bytes, errors)
- ZFS ARC stats (via SNMP)
- Replication and snapshot task status
- System alerts

## Configuration

Set `TRUENAS_USER` and `TRUENAS_PASS` environment variables. Pass `--target <IP>` as the argument.

```
docker run -e TRUENAS_USER=root -e TRUENAS_PASS=password \
  ghcr.io/malkolm/truenas-exporter:latest \
  --target 10.0.30.5 --port 9912 --skip-snmp
```

Default port: `9912`
