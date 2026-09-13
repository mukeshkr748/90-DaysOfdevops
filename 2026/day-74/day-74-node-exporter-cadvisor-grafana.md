# Day 74 – Node Exporter, cAdvisor and Grafana

## 1. Node Exporter

Node Exporter collects system/server metrics and exposes them for Prometheus.

Examples:
- CPU metrics
- Memory metrics
- Disk metrics

Node Exporter was started using Docker:

```bash
docker run -d \
  --name node-exporter \
  -p 9100:9100 \
  prom/node-exporter:latest

Metrics were checked using:

curl -s http://localhost:9100/metrics | head
2. cAdvisor

cAdvisor collects container-level metrics.

Examples:

Container CPU usage
Container memory usage
Container information

cAdvisor was started using Docker:

docker run -d \
  --name cadvisor \
  -p 8080:8080 \
  gcr.io/cadvisor/cadvisor:latest

Metrics were checked using:

curl -s http://localhost:8080/metrics | head

Container CPU metrics were successfully displayed.

3. Grafana

Grafana is used to visualize metrics in dashboards.

Grafana was started using Docker:

docker run -d \
  --name grafana \
  -p 3000:3000 \
  grafana/grafana:latest

Grafana health was checked using:

curl -s http://localhost:3000/api/health
4. Basic Observability Flow
Server / EC2
     |
     v
Node Exporter
     |
     v
Prometheus
     |
     v
Grafana Dashboard

For Docker containers:

Docker Containers
       |
       v
    cAdvisor
       |
       v
    Prometheus
       |
       v
     Grafana
5. Components Learned
Component	Purpose
Node Exporter	Server/system metrics
cAdvisor	Docker container metrics
Prometheus	Collects and stores metrics
Grafana	Visualizes metrics
6. What I Learned
Basic use of Node Exporter.
Basic use of cAdvisor.
Basic use of Grafana.
How Node Exporter exposes server metrics.
How cAdvisor exposes container metrics.
Basic role of Prometheus in monitoring.
Basic role of Grafana in visualization.
Day 74 Status

Node Exporter: Completed

cAdvisor: Completed

Grafana: Completed

Basic monitoring stack: Completed
