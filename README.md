# golang-docker-template

---

## docker compose

### Start container

```
$ docker compose -f docker-compose.yml up
```

### Start container with go-delve/delve

```
$ docker compose -f docker-compose.yml -f docker-compose-debug.yml up
```

## Check if the container is working

```
$ curl -X GET http://localhost:8000
Hello World
```
