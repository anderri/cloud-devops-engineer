---
description: >-
  Docker is a set of platform as a service products that use OS-level
  virtualization to deliver software in packages called containers. The service
  has both free and premium tiers. The software that hos
---

# Docker

DOCKER vs VM/OS\


Advantages:\
Docker runs on the application layer only. \
Smaller Size = MB vs GB \
Speed: Faster \
Compatibility: Can run on many different OS Host&#x20;

![](<../.gitbook/assets/Screen Shot 2022-08-12 at 1.12.21 pm.png>)

What problems do containers solve? \
\
First, Docker helps you package applications and their dependencies into portable application images that are straightforward to distribute to artifact repositories and then onto container hosts that will run them. In another words, your software stays system agnostic, making software simpler to use, and less work to develop.&#x20;

* Meaning apps run the same, no matter where they are of what machine they are running
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

**Image vs Container**

![](<../.gitbook/assets/Screen Shot 2022-08-12 at 1.20.53 pm.png>)

**Version and Tag**&#x20;

Version: 5.0.5&#x20;

****

****

****

**Basic Commands**&#x20;

| Docker +                | Explanation                 | test |
| ----------------------- | --------------------------- | ---- |
| pull                    | download image              |      |
| run                     | attached mode - on terminal |      |
| start                   |                             |      |
| stop                    |                             |      |
| ps                      | list running containers     |      |
| ps -a                   |                             |      |
| logs + container id     |                             |      |
| exec -it DB /bin/bash   |                             |      |
| network ls              |                             |      |
| network create postgres |                             |      |

| RUN OPTIONS    |                                     |   |
| -------------- | ----------------------------------- | - |
| -d             | detached mode                       |   |
| -p             | docker port 6000 and host port 6795 |   |
| -- name DB     | container name = DB                 |   |
| postgres:10.10 | image name and tag/version          |   |
| net --name     |                                     |   |

{% code title="example" %}
```
docker run -d\ 
-p 27017:27017 \
-- name DB \ 
--net network \
postgres:10.10 

```
{% endcode %}

![](../.gitbook/assets/Docker-commands-cheat-sheet-by-PhoenixNAP-scaled.jpeg)
