---
description: Tool for building and managing virtual machine environments
---

# Vagrant

### Boxes Respository

[https://app.vagrantup.com/boxes/search](https://app.vagrantup.com/boxes/search)\


### Main Commands

**Create a folder to save your VM**

{% code title="Example" %}
```
mkdir VM
```
{% endcode %}

****

**Create a Vagrant file**&#x20;

{% code title="Centos" %}
```
vagrant init centos/7 
```
{% endcode %}

{% code title="WindowsServer2012r2" %}
```
vagrant init win-2012r2-standard-amd64-nocm
```
{% endcode %}

**Start VM**

```
vagrant up
```



&#x20; Other commands: destroy, connect, halt (shutdown).&#x20;





{% embed url="https://www.youtube.com/watch?v=VRzjkUJz-9U" %}

