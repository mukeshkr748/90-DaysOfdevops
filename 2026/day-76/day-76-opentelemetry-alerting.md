Day 76 – OpenTelemetry and Alerting
1. OpenTelemetry

OpenTelemetry is a standard and collection of tools used to generate and collect telemetry data from applications.

It can work with:

Metrics
Logs
Traces

Basic flow:

Application
    |
    v
OpenTelemetry
    |
    +---- Metrics
    +---- Logs
    +---- Traces

For this beginner practice, OpenTelemetry was studied at a basic conceptual level.

No advanced OpenTelemetry Collector or distributed tracing setup was used.

2. Alerting

Alerting helps notify us when something important happens in a monitoring system.

For example:

up = 1  → Target is UP
up = 0  → Target is DOWN

A simple Prometheus alert rule was created.

3. Basic Alert Rule
groups:
  - name: basic-alerts
    rules:
      - alert: PrometheusDown
        expr: up == 0
        for: 1m
        labels:
          severity: warning
        annotations:
          summary: "Prometheus target is down"
          description: "A Prometheus target is not responding."

This rule checks the up metric.

If a target remains down for 1 minute, the PrometheusDown alert can fire.

4. Basic Prometheus Check

The following command was used:

curl -s 'http://localhost:9090/api/v1/query?query=up'

The Prometheus target returned:

up = 1

This means the target was available.

5. What I Learned
Basic concept of OpenTelemetry.
Metrics, logs and traces.
Basic concept of alerting.
Prometheus up metric.
Difference between up = 1 and up = 0.
Created a simple Prometheus alert rule.
Avoided advanced OpenTelemetry and alerting configuration.
Day 76 Status

OpenTelemetry basics: Completed

Alerting basics: Completed

Simple alert rule: Completed

Advanced tracing/alerting: Not covered
