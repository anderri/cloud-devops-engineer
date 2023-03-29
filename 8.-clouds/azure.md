# Azure



### 1 - Creating and Configuring a Network Load Balancer in AWS&#x20;

Instance A

```
#!/bin/bash

yum update -y && yum -y install httpd && systemctl enable httpd && systemctl start httpd

usermod -a -G apache ec2-user 
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
echo "Request Handled by: Web-A" >> /var/www/html/index.html
```

Instance B

```
#!/bin/bash

yum update -y && yum -y install httpd && systemctl enable httpd && systemctl start httpd

usermod -a -G apache ec2-user 
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
echo "Request Handled by: Web-B" >> /var/www/html/index.html
```

Test the NLB&#x20;

```
while true; do curl <LOAD BALANCER DNS NAME>; done
```
