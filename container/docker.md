---
description: >-
  Docker is a set of platform as a service products that use OS-level
  virtualization to deliver software in packages called containers. The service
  has both free and premium tiers. The software that hos
---

# Docker

{% embed url="https://www.youtube.com/watch?v=_dfLOzuIg2o" %}

{% embed url="https://www.youtube.com/watch?v=3c-iBn73dDE" %}

****

**Basic Commands**&#x20;

docker pull&#x20;

docker run -d -p6000:6795 --name DB postgres:10.10

docker start&#x20;

docker stop

docker ps

docker ps -a

docker logs 7f4225261ae

docker exec -it DB /bin/bash

docker network ls&#x20;

docker network create postgres

docker run -d -p 27017:27017 postgres:10.10 --net --name&#x20;



docker run -d \\\
\-p 27017:27017 \\\
\-- name DB \ \
\--net network \\\
postgres:10.10
