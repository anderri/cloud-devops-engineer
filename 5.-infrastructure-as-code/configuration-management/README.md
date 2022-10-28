# 8. Infrastructure as Code - IaC

\
\
Next, you define the following Ansible playbook:

### What is Infrastructure as Code?

The idea behind infrastructure as code (IAC) is that you write and execute code to define, deploy, update, and destroy your infrastructure. This represents an important shift in mindset in which you treat all aspects of operations as software - even those aspects that represent hardware (e.g., setting up physical servers). In fact, a key insight of DevOps is that you can manage almost everything in code, including servers, databases, networks, log files, application configuration, documentation, automated tests, deployment process, and so on.&#x20;

There are five broad categories of IAC tools:

* Ad hoc scripts
* Configuration management tools
* Server templating tools
* Orchestration tools
* Provisioning tools

Let's look at these one at a time.&#x20;

#### Ad Hoc Scripts

The most straightforward approach to automation anything is to write an ad hoc script. You take whatever task you were doing manually, break it down into discrete steps, use your favorite scripting language (e.g., Bash, Ruby, Python) to define each of those steps in code, and execute that script on your server, as shown in Figure 1-1.&#x20;

![](<../../.gitbook/assets/Screen Shot 2022-10-28 at 2.15.19 pm.png>)



#### Configuration Management Tools

Chef, Puppet, Ansible, and SaltStack are all configuration management tools, which means that they are designed to install and manage software on existing servers. For example, here is an Ansible Role called web-server.yml that configures the same Apache web server as the setup-webserver.sh script:&#x20;

```yaml
// Some code
- name: Update the apt-get cache
  apt:
    update_cache: yes
- name: Install PHP
  apt:
    name: php
- name: Install Apache
  apt:
    name: apache2
- name: Copy the code from the repository
  git: repo=https:// 
- name: Start Apache
  service: name=apache2 state=started enabled=yes
```

#### Coding conventions

Ansible enforces a consistent, predictable structure, including documentation, file layout, clearly named parameters, secrets management, and so on. While every developer organizes their ad hoc scripts in a different way, most configuration management tools come with a set of conventions that makes it easier to navigate the code.&#x20;

#### Idempotence&#x20;

Writing an ad hoc script that works once isn't too difficult; writing an ad hoc script works correctly even if you run it over and over again is a lot more difficult. Every time you go to create a folder in your script, you need to remember to check whether that folder already exists; every time you add a line of configuration to a file, you need to check that line doesn't exist; every time you want to run an app, you need to check that the app isn't already running.&#x20;

Code that works correctly no matter how many times you run it is called idempotent code. To make the Bash script from the previous section idempotent, you'd need to add many lines of code, including lots of if-statements. Most Ansible functions, on the other hand, are idempotent by default. For example, the web-server.yml Ansible role will install Apache only if it isn't installed already and will try start the Apache web server only if it isn't running already.&#x20;

#### Distribution

Ad hoc scripts are designed to run a single, local machine. Ansible and other configuration management tools are designed specifically for managing large numbers of remote servers, as shown in Figure 1-2.



![](<../../.gitbook/assets/Screen Shot 2022-10-28 at 7.26.01 pm.png>)

&#x20;

For example, to apply the web-server.yml role to five servers, you first create a file called hosts that contains the IP addresses of those servers:

```yaml
// Some code
[webservers]
11.11.11.11
11.11.11.12
11.11.11.13
```

Next, you define the following Ansible playbook:

```
// Some code
- hosts: webservers
  roles:
  - webserver
```

Finally, you execute the playbook as follows:&#x20;

```
// Some code
ansible-playbook playbook.yml
```



#### Server Templating Tools

An alternative to configuration management that has been growing in popularity recently are server templating tools such as Docker, Packer, and Vagrant. Instead of launching a bunch of servers and configuring them by running the same code on each one, the idea behind server templating tools is to create an image of a server that captures a fully self-contained "snapshot" of the operating system (OS), the software, the files, and all other relevant details. You can then use some other IaC tool to install that image on all of your servers, as shown in Figure 1-3.&#x20;

![](<../../.gitbook/assets/Screen Shot 2022-10-28 at 2.34.26 pm.png>)

#### Virtual Machines&#x20;

A virtual machine (VM) emulates an entire computer system, including the hardware. You run a hypervisor, such as VMWare, VirtualBox, or Parallels, to virtualize (i.e., simulate) the underlying CPU, memory, hard drive, and networking. The benefit of this is that any VM image that you run on top of the hypervisor can see only the virtualized hardware, so it's fully isolated from the host machine and any other VM images.&#x20;

#### Containers

A container emulates the user space of an OS. You run a container engine, such as Docker, CoreOS rkt, or cri-o, to create isolated process, memory, mount points, and networking. The benefit of this is that any container you run on top of the container engine can see only its own user space, so it's isolated from the host machine and other containers and will run exactly the same way in all environments (your computer, a QA server, a production server, etc). The drawback is that all the containers running on a single server share that server's OK kernel and hardware, so it's much more difficult to achieve the level of isolation and security you get with VM. However, because the kernel and hardware are shared, your containers can boot up in milliseconds and have virtually no CPU or memory overhead. You can define container images as code using tools such as Docker and CoreOS rkt. \
\
![](<../../.gitbook/assets/Screen Shot 2022-10-28 at 2.48.21 pm.png>)

For example, here is a Packer template called web-server.json that creates an Amazon Machine Image (AMI), which is a VM image that you can run on AWS:

```
// Some code
{
    "builders": [{
      "ami_name": "packer-example",
      "instance_type": "t2.micro",
      "region": "us-east-2",
      "type": "amazon-ebs",
      "source_ami": "ami-0c55b159cbfafe1f0",
      "ssh_username": "ubuntu"
   }],
   "provisioners": [{
     "type": "shell", 
     "inline": [
       "sudo apt-get update",
       "sudo apt-get install -y php apache2",
       "sudo git clone https://github.com/brikil/php-app.git /var/www/html/app"
     ],
     "environment_vers": [
       "DEBIAN_FRONTEND:noninteractive"
       ]
     }]
   }     
```

The code looks similar to the Bash script, but using a tool like Ansible offers a number o advantages:

####

### Orchestration Tools

Server templating tools are great for creating VMs and containers, but how do you actually manage them? For most real-world use cases, you'll nee a way to do the following:

* Deploy VMs and containers, making efficient use of you hardware.
* Roll out updates to an existing fleet of VMs and containers using strategies such as rolling deployment, blue-green deployment, and canary deployment.&#x20;
* Monitor the healthy of your VMs and containers and automatically replace unhealthy ones (auto healing).
* Scale the number of VMs and containers up or down in response to load (auto scaling).
* Distribute traffic across your VMs and containers (load balancing).
* Allow your VMs and containers to find and talk to one another over the network (service discovery).

Handling these tasks is the realm of orchestration tools such as Kubernetes, Marathon/Mesos, Amazon Elastic Container Service (Amazon ECS), Docker Swarm, and Nomad. For example, Kubernetes allows you to define how to manage your Docker containers as code. You first deploy a Kubernetes cluster, which is a group of servers that Kubernetes will manage and use to run your docker containers. Most major cloud providers have native support for deploying managed Kubernetes clusters, such as Amazon Elastic Container Service for Kubernetes (Amazon EKS), Google Kubernetes Engine (GKE), and Azure Kubernetes (AKS).&#x20;

Once you have a working cluster, you can define how to run your Docker container as code in a YAML file.&#x20;

```
// Some code
apiVersion: apps/v1
#Use a Deployment to deploy multiple replicas of your Docker
#container(s) and to declaratively roll out updates to them 
kind: Deployment

# Metadata about this Deployment, including its name
metadata:
name: example-app

#The specification that 
```

This file instructs Kubernetes to create a Deployment, which is a declarative way to define:

* One or more Docker containers to run together. This group of containers is called Pod. The Pod defined in the preceding code contains a single Docker container that runs Apache.&#x20;
* the settings for each Docker container in the Pod. The Pod in the preceding code configures Apache to listen on port 80.&#x20;
* How many copies (aka replicas) of the Pod to run in your cluster. The preceding code configures three replicas. Kubernetes automatically figures out where in your cluster to deploy each Pod, using a scheduling algorithm to pick the optimal servers in terms of high availability (e.g., try to run each Pod on a separate server so a single server crash doesn't take down your app), resources (e.g., pick servers that have available the ports, CPU, memory, and other resources required by your containers), performance, and so on. Kubernetes also constantly monitors the cluster to ensure that there are always three replicas running, automatically replacing any Pods that crash or stop responding.&#x20;
* How to deploy updates. When deploying a new version of the Docker container, the preceding code rolls out three new replicas, waits for them to be healthy, and then undeploys the three old replicas.&#x20;

That's a lot of power in just a few lines of YAML! You run kubectl apply -f example-app.yml to instruct Kubernetes to deploy your app. You can then make changes to the YAML file and run kubectl again to roll out the updates.&#x20;



### Provisioning Tools&#x20;

Whereas configuration management, server templating, and orchestration tools define the code that runs on each server, provisioning tools such as Terraform, CloudFormation, and OpenStack Heat are responsible for creating the server themselves. In fact, you can use provisioning tools to not only create servers, but also databases, caches, load balancers, queues, monitoring, subnet configurations, firewall settings, routing rules, secure sockets layer (SSL) certificates, and almost every other aspect of your infrastructure, as shown in Figure 1-5.&#x20;

![](<../../.gitbook/assets/Screen Shot 2022-10-28 at 9.40.23 pm.png>)

### The Benefits of IaC

* Deploy 200 times more frequently.
* Recover from failures 24 times faster&#x20;
* Lead times 2.555 times lower.&#x20;
* Self-service
* Speed and safety
* Documentation
* Version Control
* Validation
* Reuse
* Happiness



