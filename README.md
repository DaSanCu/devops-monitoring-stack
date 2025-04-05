# DevOps Monitoring Stack

Willkommen im **DevOps Monitoring Stack** Projekt. Dieses Repository zeigt eine vollständige Observability-Lösung mit **Docker Compose**, **Kubernetes (K8s)**, **Ansible** und **Helm**. Es ist modular aufgebaut, sodass jede Technologie separat betrachtet und getestet werden kann.

## 🔍 Ziel des Projekts

Dieses Projekt wurde mit dem Ziel entwickelt, gängige Tools und Konzepte der Infrastrukturüberwachung und -bereitstellung zu demonstrieren. Es simuliert ein realistisches Setup, das sowohl im Container-basierten als auch im Kubernetes-Umfeld funktioniert.

## 📁 Projektstruktur

```bash
devops-monitoring-stack/
│
├── docker-compose/     # Komplettes Stack-Setup via Docker Compose
├── k8s/                # Kubernetes Manifeste für manuelles Deployment
├── helm/               # Helm Chart zum einfachen Ausrollen im Cluster
├── ansible/            # Ansible-Playbook für die automatisierte Installation des Docker Stacks
└── README.md           # Diese Datei
```

## 🧪 Wie man das Projekt nutzt

Wähle die passende Variante je nach Umgebung oder Tool-Fokus:

### 1. Docker Compose

```bash
cd docker-compose
docker compose up -d
```

Zugängliche Services:
- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000 (Login: admin / admin)
- Alertmanager: http://localhost:9093

### 2. Kubernetes (K8s)

```bash
cd k8s
kubectl apply -f .
```

Nutze `kubectl get pods` und `kubectl port-forward` um auf die Services zuzugreifen.

### 3. Ansible

Installiert den Docker Stack inklusive Docker & Docker Compose:

```bash
cd ansible
ansible-playbook -i inventory.ini monitoring-setup.yml -K
```

> Funktioniert unter Ubuntu/Linux am besten.

### 4. Helm

Installiert den Stack als Helm-Chart (z. B. mit Minikube):

```bash
cd helm/monitoring
helm install monitoring .
```

## 💡 Hinweise

- `grafana-data/`, `prometheus/data/` und `loki/data/` sind aus `.gitignore` ausgeschlossen, um lokale Volumes nicht mit zu versionieren.
- Minikube-Nutzer müssen ggf. Port-Forwarding verwenden, um Zugriff auf Services zu erhalten.

## ✅ Anforderungen

- Docker & Docker Compose
- Kubernetes oder Minikube
- Ansible (optional)
- Helm (optional)
- Linux/WSL empfohlen für Ansible & kubectl-Kompatibilität

---

📫 **Fragen oder Feedback?** Einfach melden oder ein Issue auf GitHub öffnen.

Viel Spaß beim Ausprobieren! 🚀
