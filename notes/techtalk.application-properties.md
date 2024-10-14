---
id: 5wh2b9tbbczp7rgxk7vg2q1
title: Application Properties
desc: ''
updated: 1723636850026
created: 1723636850026
isDir: false
---
spring.datasource.url=jdbc:postgresql://localhost:5432/employees
spring.datasource.username=postgres
spring.datasource.password=secret
spring.jpa.show-sql=true

## Hibernate Properties
# The SQL dialect makes Hibernate generate better SQL for the chosen database
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.PostgreSQLDialect

# Hibernate ddl auto (create, create-drop, validate, update)
spring.jpa.hibernate.ddl-auto = update

management.endpoints.web.exposure.include=*