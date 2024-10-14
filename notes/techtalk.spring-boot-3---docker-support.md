---
id: lkohubq4x5z5jcwbujgvkpn
title: Spring Boot 3   Docker Support
desc: ''
updated: 1723636850026
created: 1723636850026
isDir: false
---
Dependencies:
actuator
data-jpa
rest-repositories
docker-compose
prometheus
postgresql
lombok

Person: [[person.class]]

PersonRepository: [[personrepository.class]]

application.properties: [[application.properties]]

http://localhost:8080
http://localhost:8080/people
http://localhost:8080/actuator
http://localhost:8080/actuator/metrics
http://localhost:8080/actuator/prometheus

Curl:
curl -i -H "Content-Type:application/json" -d '{"firstName": "Frodo", "lastName": "Baggins"}' http://localhost:8080/people
curl -i -H "Content-Type:application/json" -d '{"firstName": "Bilbo", "lastName": "Baggins"}' http://localhost:8080/people

Folders:
prometheus/prometheus.yml
grafana/datasource.yml

Files: 
[[prometheus.yml]] ** Change the IP **
[[datasource.yml]]
[[compose.yml]]

http://localhost:9090
http://localhost:3000

Grafana Dashboards: https://grafana.com/grafana/dashboards/
4701 - JVM
12900 - Spring-Boot