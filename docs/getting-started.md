---
title: Getting Started
layout: page
---

The easiest way to get started is to use Git to clone the tutorial repository which will give you a copy of the course materials, and the supporting files needed to get the lab up and running with Docker compose.

```terminal
$ git clone --recursive https://github.com/Internet2/netbox-tutorial
Cloning into 'netbox-tutorial'...
remote: Enumerating objects: 68, done.
remote: Counting objects: 100% (68/68), done.
remote: Compressing objects: 100% (46/46), done.
remote: Total 68 (delta 17), reused 61 (delta 15), pack-reused 0
Unpacking objects: 100% (68/68), 160.12 KiB | 709.00 KiB/s, done.
Submodule 'netbox-docker' (https://github.com/netbox-community/netbox-docker.git) registered for path 'netbox-docker'
Cloning into '/Users/steinhof/Desktop/netbox-tutorial/netbox-docker'...
remote: Enumerating objects: 45, done.
remote: Counting objects: 100% (45/45), done.
remote: Compressing objects: 100% (34/34), done.
remote: Total 1846 (delta 24), reused 24 (delta 10), pack-reused 1801
Receiving objects: 100% (1846/1846), 487.30 KiB | 7.38 MiB/s, done.
Resolving deltas: 100% (1049/1049), done.
Submodule path 'netbox-docker': checked out '80f514fa90997bc7b132ea06b84056c6720f37d0'
```

Change to the new directory created by this command, and take a look at the files in the repository:

```terminal
$ cd netbox-tutorial
$ ls -l
total 16
-rw-r--r--   1 _user_   _group_      62 Mar  3 14:46 README.md
-rw-r--r--   1 _user_   _group_    1082 Mar  3 14:46 docker-compose.yml
drwxr-xr-x  13 _user_   _group_     416 Mar  3 14:46 docs
drwxr-xr-x  25 _user_   _group_     800 Mar  3 14:46 netbox-docker
```

Change to the `netbox-docker` directory:

```terminal
$ cd netbox-docker/
```

And start the Docker Compose services:

```terminal
$ docker-compose -f docker-compose.yml -f ../docker-compose.override.yml up -d
Starting netbox-docker_postgres_1    ... done
Starting netbox-docker_redis-cache_1 ... done
Starting netbox-docker_redis_1       ... done
Starting netbox-docker_netbox-worker_1 ... done
Starting netbox-docker_netbox_1        ... done
Starting netbox-docker_nginx_1         ... done
```

You can see the logs of all these services with this command:

```terminal
$ docker-compose logs -f
```

Press `Ctrl-C` to exit the log command.

The services will taka a few minutes to spin up, when they are finished, the NetBox interface should be available from your machine at <http://localhost:9797/>.


See [Shutting down and cleaning up]({% link clean-up.md %}) for commands to turn off and remove these services.
