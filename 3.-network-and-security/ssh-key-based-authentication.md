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

3\. Copy Server IP Address

```
Ip a
```

SSH Configuration

```
vi /etc/ssh/sshd_config
```

Port 22

#### CLIENT

Install SSH Client

```
sudo apt install openssh-client 
```

### Connecting to the SSH Server via user and password.

From client

```
ssh vagrant@192.168.1.9
```



### Connect to the SSH Server via Key Authentication

Create private and public key.

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

Copy the key value and past on the SSH-Server authorized\_keys of root user.

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
ssh -i id_rsa vagrant@192.168.1.9
```
{% endcode %}

Where:\
id\_rsa = private ssh-key file name\
vagrant = remote user&#x20;

{% embed url="https://www.youtube.com/watch?v=vpk_1gldOAE" %}
