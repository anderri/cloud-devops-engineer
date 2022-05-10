---
description: Tool for building and managing virtual machine environments
---

# Vagrant

### Boxes Respository

[https://app.vagrantup.com/boxes/search](https://app.vagrantup.com/boxes/search)\\

### Install Vagrant

```
brew install vagrant
```

###

### Main Commands

**Create a folder to save your VM**

{% code title="Example" %}
```
mkdir VM
```
{% endcode %}

***

**Create a Vagrant file**

{% code title="Centos" %}
```
vagrant init centos/7 
```
{% endcode %}

{% code title="WindowsServer2012r2" %}
```
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
