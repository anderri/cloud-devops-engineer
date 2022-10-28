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

#### Coding conventions

Ansible enforces a consistent, predictable strucuture, including documentation, file layout, clearly named parameters, secrets management, and so on. While every developer organizes their ad hoc scripts in a different way, most configuration management tools come with a set of conventions that makes it easier to navigate the code.&#x20;

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

