# DevOps Monitoring Stack

# 🚀 DevOps Monitoring Stack

Ein vollständiges Monitoring- und Logging-Setup auf Basis von Docker Compose, Prometheus, Grafana, Loki und Promtail.

## ✅ Features
- **Prometheus** ➔ Metrik-Sammlung & Monitoring
- **Node Exporter** ➔ Systemmetriken (CPU, RAM, Disk, etc.)
- **Grafana** ➔ Dashboards für Metriken und Logs
- **Loki** ➔ Zentrale Log-Sammlung
- **Promtail** ➔ Log-Sammlung von lokalen Files
- Docker Compose für einfaches Deployment
- Persistente Volumes für dauerhafte Speicherung

---

## 🚀 Architektur

+------------------+ +---------------+ | Node Exporter | <---> | Prometheus | +------------------+ +---------------+ | +-------------+ | Grafana | +-------------+ /
+-------------------+ +-----------------+ | Loki (Log Storage)| | Alertmanager (*)| +-------------------+ +-----------------+ | +-----------+ | Promtail | +-----------+

yaml
Copy
Edit

(*) Optional in einer späteren Version

---

## ✅ Stack Komponenten & Ports

| Service       | Beschreibung                | Port     |
|---------------|-----------------------------|----------|
| Prometheus    | Metrik-Scraper              | `9090`   |
| Node Exporter | Systemmetriken              | `9100`   |
| Grafana       | Dashboards & Visualisierung | `3000`   |
| Loki          | Zentrales Logging Backend   | `3100`   |
| Promtail      | Log-Sammlung (Local)        | -        |

---

## ✅ Quickstart (lokale Umgebung)

### 1. Projekt klonen
```bash
git clone git@github.com:DaSanCu/devops-monitoring-stack.git
cd devops-monitoring-stack
2. Docker Compose starten
bash
Copy
Edit
docker compose up -d
3. Zugänge
Grafana ➔ http://localhost:3000
Login: admin / admin ➔ Passwort ändern!
✅ Data Sources in Grafana einrichten
1. Prometheus
Type: Prometheus
URL: http://prometheus:9090
2. Loki
Type: Loki
URL: http://loki:3100
✅ Dashboards & Logs
Node Exporter Full Dashboard
Gehe zu ➔ Dashboards ➔ Import
Importiere Dashboard mit ID 1860
Datenquelle ➔ Prometheus auswählen
Logs anzeigen (Loki)
Explore ➔ Data Source ➔ Loki
Query:
arduino
Copy
Edit
{job="varlogs"}
Optional ➔ Live Tail aktivieren
✅ Verzeichnisstruktur
arduino
Copy
Edit
devops-monitoring-stack/
├── docker-compose.yml
├── grafana/
│   └── data/
├── prometheus/
│   ├── prometheus.yml
│   └── data/
├── loki/
│   ├── config.yaml
│   └── data/
└── promtail/
    └── config.yaml
✅ Volumes / Persistent Storage
Damit alle Daten bei einem Neustart erhalten bleiben, nutzen wir Volumes:

Prometheus ➔ ./prometheus/data
Grafana ➔ ./grafana/data
Loki ➔ ./loki/data
✅ Voraussetzungen
Docker & Docker Compose installiert
WSL2 & Docker Desktop mit WSL2 Integration (für Windows)
Ports 3000, 9090, 9100, 3100 offen
✅ Geplante Features
Alertmanager & Benachrichtigungen
CI/CD Pipeline zur Automatisierung (GitHub Actions)
Kubernetes Deployment
Security Hardening (Benutzer & Passwörter via .env)
✅ Autor
👨‍💻 David Sánchez
GitHub

Test deployment Fri Mar 21 14:06:27 CET 2025
