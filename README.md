# K8s Sidecar Container Test

This project deploys Nginx using a Helm chart with an OpenTelemetry (OTEL) sidecar container that collects logs from the Nginx pod and exports them to Splunk.

## Components

- Nginx server logging to files instead of stdout
- OTEL Collector sidecar that reads log files and exports to Splunk HEC

## Deployment

```bash
helm install nginx-test ./nginx-chart
```

## Configuration

- Splunk URL: http://10.10.10.10:8088/services/collector/event
- Token: XXX-XX-XXXX
- Index: test_idx

## Logs

Logs are written to /var/log/nginx/access.log and error.log on the pod, collected by OTEL, and exported to Splunk.
