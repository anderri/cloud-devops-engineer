# SSH Key-Based Authentication



### INSTALLATION

#### SSH SERVER

1. Check if the server is running

```
ss  -ln | grep 22 
```

2\. Install SSH Server

```
apt install openssh-server -y
```

3\. Copy Server IP Address&#x20;

```
Ip a
```

SSH Configuration&#x20;

```
vi /etc/ssh/sshd_config
```

Port 22



#### CLIENT

Install SSH Client

```
sudo apt install openssh-client 
```

### Connecting to the SSH Server via user and password.&#x20;

From client&#x20;

```
ssh user@ip -p 22
```

### Connect to the SSH Server via Key Authentication&#x20;

Create private and public key.&#x20;

{% code title="SSH-Client" %}
```
cd .ssh
ls
ssh-keygen  
ls -lh
```
{% endcode %}

Option 1 - Copy public key from SSH Client to SSH Server.

{% code title="SSH-Client" %}
```
ssh-copy-id user@ip 
```
{% endcode %}



Option 2 - Copy public key from SSH Client to SSH Server.

{% code title="SSH-Client" %}
```
cd .ssh
ls -l
cat id_ed25519.pub
```
{% endcode %}

Copy the key value and past on the SSH-Server authorized\_keys of root user.&#x20;

{% code title="SSH-Server" %}
```
cd ~ 
cd .ssh 
cat authorized_keys
```
{% endcode %}

Test Connection

{% code title="SSH-Client" %}
```
ssh root@ip 
```
{% endcode %}

{% embed url="https://www.youtube.com/watch?v=vpk_1gldOAE" %}
