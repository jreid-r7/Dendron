---
id: oprjqgonpcet678yjdzok0z
title: Prometheus Yml
desc: ''
updated: 1724744015406
created: 1723636850027
isDir: false
---
```yaml
global:
  scrape_interval: 15s
  scrape_timeout: 10s
  evaluation_interval: 15s
alerting:
  alertmanagers:
    - static_configs:
        - targets: []
      scheme: http
      timeout: 10s
      api_version: v1
scrape_configs:
  - job_name: 'spring-actuator'
    honor_timestamps: true
    scrape_interval: 15s
    scrape_timeout: 5s
    metrics_path: '/actuator/prometheus'
    scheme: http
    static_configs:
      - targets: ['10.15.24.84:8080']
  
  ```