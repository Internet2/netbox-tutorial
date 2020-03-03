---
title: Shutting down and cleaning up
layout: page
---

## Shutting down

To turn off your Docker Compose services us this command from inside the `netbox-tutorial/netbox-docker` directory:

```terminal
$ docker-compose stop
```

(To start then again, use `docker-compose start` or the command from [Getting Started]({% link getting-started.md %}).)

## Removing all services and data

To completely remove it (*and the data you created in the lab*):

```terminal
$ docker-compose down -v
```
