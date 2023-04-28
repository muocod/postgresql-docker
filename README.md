# postgresql-docker

``` make up``` to deploy

``` make down``` to undeploy

``` make destroy``` to undeploy and delete postgres data

### docker-compose.yml

```
version: '3.8'

services:

  postgres:
    image: postgres:15.2-alpine
    deploy:
      replicas: 1
      update_config:
        parallelism: 1
        delay: 6s
        order: start-first
      resources:
        limits:
          cpus: "1"
          memory: 1g
        reservations:
          cpus: "1"
          memory: 1g
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
    network_mode: host
 ```
 
 
