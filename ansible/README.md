# Ansible Setup für Monitoring Stack (Docker Compose)

Dieses Verzeichnis enthält ein Ansible Playbook zur automatisierten Bereitstellung des Monitoring-Stacks mit Docker Compose.

## Struktur

- `inventory.ini`: Zielsystem (in der Regel `localhost`)
- `roles/docker/`: Installiert Docker & Compose
- `monitoring-setup.yml`: Führt den Stack aus

## Voraussetzungen

- Ansible
- Git
- SSH-Zugriff bei Remote-Nutzung

## Ausführung

```bash
cd ansible
ansible-playbook -i inventory.ini monitoring-setup.yml -K
```

Dies installiert Docker, zieht das Repository (wenn gewünscht) und startet `docker-compose up -d`.

