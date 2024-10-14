---
id: 83yo4yr0ewt0h2lxd66m1ik
title: Compose Yml
desc: ''
updated: 1723650916404
created: 1723636850026
isDir: false
---
```yaml
  prometheus:  
    image: prom/prometheus  
    container_name: prometheus  
    command:  
      - '--config.file=/etc/prometheus/prometheus.yml'  
    ports:  
      - 9090:9090  
    restart: unless-stopped  
    volumes:  
      - ./prometheus:/etc/prometheus  
      - prom_data:/prometheus  
  grafana:  
    image: grafana/grafana  
    container_name: grafana  
    ports:  
      - 3000:3000  
    restart: unless-stopped  
    environment:  
      - GF_SECURITY_ADMIN_USER=admin  
      - GF_SECURITY_ADMIN_PASSWORD=grafana  
    volumes:  
      - ./grafana:/etc/grafana/provisioning/datasources  
volumes:  
  prom_data:
```