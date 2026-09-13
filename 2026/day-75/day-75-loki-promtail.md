Day 75 – Loki and Promtail Documentation
Day 75 – Log Management with Loki and Promtail
1. What is Log Management?

Log management means collecting and storing application and system logs so that they can be checked when troubleshooting.

2. Loki

Loki is a log aggregation system from Grafana.

It can be used to collect and store logs.

Loki was started using Docker:

docker run -d \
  --name loki \
  -p 3100:3100 \
  grafana/loki:latest
3. Loki Health Check

Loki was checked using:

curl -s http://localhost:3100/ready

Result:

ready

This confirmed that Loki was running correctly.

4. Promtail

Promtail is a log collection agent that can read log files and send them to Loki.

Basic flow:

Application / System Logs
          |
          v
       Promtail
          |
          v
         Loki
5. Promtail Practical

A basic Promtail configuration was created with Loki as the destination.

However, while starting the Promtail Docker container, the EC2 instance ran out of disk space.

Error:

no space left on device

The root filesystem was almost full:

/dev/root   19G   18G   296M   99% /

Therefore, Promtail was not started successfully.

No running Docker containers or important images were removed because they were being used by the current monitoring and Kubernetes setup.

6. Basic Difference
Tool	Purpose
Loki	Stores and queries logs
Promtail	Collects logs and sends them to Loki
Prometheus	Collects metrics
Grafana	Visualizes metrics and logs
7. What I Learned
Basic concept of log management.
Basic purpose of Loki.
Basic purpose of Promtail.
Basic Loki health check.
Basic log flow from Promtail to Loki.
Difference between metrics and logs.
Disk-space problems can affect Docker image downloads and containers.
Day 75 Status

Loki: Completed

Promtail concept: Completed

Promtail practical: Skipped because of EC2 disk-space limitation

Advanced logging: Not covered
