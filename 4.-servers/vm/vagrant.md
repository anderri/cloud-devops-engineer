---
description: Tool for building and managing virtual machine environments
---

# Vagrant

### Install Vagrant

{% code title="MacOS+Brew" %}
```
brew install vagrant
```
{% endcode %}

### VM Repository

[https://app.vagrantup.com/boxes/search](https://app.vagrantup.com/boxes/search)\\



### Main Commands

**Create a folder to save y**

{% code title="Example" %}
```
mkdir ~/DocumentsVagrant/Centos
cd ..
mkdir ~/DocumentsVagrant/WindowsServer
```
{% endcode %}

**Create a Vagrant file**

{% code title="Centos" %}
```
cd ~/Documents/Vagrant/Centos
vagrant init centos/7 
```
{% endcode %}

{% code title="WindowsServer2012r2" %}
```
cd ~/DocumentsVagrant/WindowsServer
vagrant init gusztavvargadr/windows-server
```
{% endcode %}

**Start VM**

```
vagrant up
```

**Connect**

```
vagrant ssh
```

**Shutdown (Halt)**

```
vagrant halt
```

**Delete**

```
vagrant destroy
```



{% embed url="https://www.youtube.com/watch?v=VRzjkUJz-9U" %}
