# 8. Infrastructure as Code - IaC



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
