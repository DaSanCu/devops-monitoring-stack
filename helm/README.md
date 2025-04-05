# Helm Chart für Monitoring Stack

Dieses Verzeichnis enthält ein Helm-Chart zur Bereitstellung eines vollständigen Monitoring-Stacks in Kubernetes.

## Komponenten

- Prometheus
- Grafana
- Loki
- Promtail
- Alertmanager
- Node Exporter

## Nutzung

```bash
cd helm
helm install monitoring ./monitoring
```

## Konfiguration

Die Datei `values.yaml` enthält alle anpassbaren Einstellungen wie SMTP, Ressourcen, Replikas etc.

## Zugriff

Die Services sind als `NodePort` verfügbar. Grafana ist typischerweise auf Port `3000` erreichbar.
