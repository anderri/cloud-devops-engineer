---
description: >-
  Docker is a set of platform as a service products that use OS-level
  virtualization to deliver software in packages called containers. The service
  has both free and premium tiers. The software that hos
---

# Docker

What problems do containers solve? \
\
First, Docker helps you package applications and their dependencies into portable application images that are straightforward to distribute to artifact repositories and then onto container hosts that will run them.

* Missing or incorrect application dependencies
* Conflicts between programs running on the same computer such as library dependencies or ports
* Limiting the amount of resources such as cpu and memory an application can use
* Missing, complicated, or immature scripts to install, start, stop, and uninstall an application

Docker images also allow you to define metadata that helps operators _run_ the application, including:

* a default command Docker should run to start the application, e.g. /start.sh
* ports, environment variables, and the working directory the application expects to use
* directories (volumes) the application expects to files to be mounted into
* labels that describe what is inside the image using key-value pairs

### Running applications in isolation

Second, Docker’s container engine and command line tool make it simple to retrieve application images and start isolated instances of each application process.

Let’s step through how Docker turns an image into a container:

![](https://nodramadevops.com/wp-content/uploads/2019/06/Basic-Flow-of-Docker-Container-Execution.png)



What is docker-composer?&#x20;

Is a tool that was developed to help define and share multi-container applications.



Why do we need a registry?&#x20;

A place for developers to store container images and share them out via a process of uploading (pushing) to the registry and downloading (pulling) into another system, like a [Kubernetes cluster](https://www.redhat.com/en/topics/containers/what-is-a-kubernetes-cluster)





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
