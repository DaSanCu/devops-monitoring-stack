# Kubernetes Monitoring Stack

Dieses Verzeichnis enthält YAML-Dateien für die Bereitstellung eines kompletten Monitoring-Stacks in Kubernetes, bestehend aus:

- Prometheus
- Grafana
- Loki & Promtail
- Alertmanager
- Node Exporter

## Nutzung

```bash
cd k8s
kubectl apply -R -f .
```

## Zugriff

- Zugriff auf Grafana über NodePort (`kubectl get svc`)
- Standardzugangsdaten: `admin` / `admin`

## Namespace

Standardmäßig werden alle Ressourcen im `default` Namespace erstellt.
