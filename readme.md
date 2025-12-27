# Prometheus, Grafana, and cAdvisor Docker Stack

This repository deploys Prometheus for metrics collection, Grafana for visualization, and cAdvisor for container monitoring using Docker Compose. Clone and run on any server with Docker installed for instant monitoring dashboards.

## Features
- One-command deployment with `docker-compose up -d`.
- cAdvisor exposes Docker container metrics on port 8080.
- Prometheus scrapes metrics and serves queries on port 9090.
- Grafana dashboard on port 3000 with pre-configured Docker templates.

## Prerequisites
- Docker and Docker Compose installed on the server.
- Basic ports open: 3000 (Grafana), 9090 (Prometheus), 8080 (cAdvisor).

## Quick Start
Clone the repository:
```bash
git clone https://github.com/rameshlinuxadmin/prometheus-grafana-cadvisor.git
cd prometheus-grafana-cadvisor
```
Start the stack:
```bash
docker-compose up -d
```
Verify containers:
```bash
docker ps
```
Expected output shows three running services: cadvisor, prometheus, grafana.

## Access Services
- cAdvisor: [http://your-server-ip:8080/containers/](http://your-server-ip:8080/containers/) (live container metrics).
- Prometheus: [http://your-server-ip:9090/graph](http://your-server-ip:9090/graph) (query interface).
- Grafana: [http://your-server-ip:3000](http://your-server-ip:3000) (admin/admin; add Prometheus datasource at http://prometheus:9090).

## Screenshots
![Docker PS Output](Images/docker-ps.png)  
![Grafana Login](Images/grafana-login.png)  
![Grafana Dashboard](Images/grafana-dashboard.png)

## Troubleshooting
- Check logs: `docker-compose logs -f`.
- Restart: `docker-compose down && docker-compose up -d`.
- Grafana datasource: Ensure URL is `http://<prometheus-IP>:9090`.  