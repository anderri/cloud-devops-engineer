# Networking

## Networking Refresher

#### Physical Layout of AZs and Regions



#### VPC concept and how to create



#### Create private and public subnets



#### What a NAT and what "Disable Source/Destination Checks" means

{% embed url="https://www.youtube.com/watch?v=FTUV0t6JaDA" %}

#### Route table and routing terminology (default routes, local routes)



#### IPv4 Addressing and Subnet Mask Notation (/16, /24, ect)

{% embed url="https://www.youtube.com/watch?v=s_Ntt6eTn94" %}

192.168.1.0

Ip Address consists of two ports

* Network address
* Host address

255.255..255.0 \
\
A subnet mask reveals how many bits is the IP address are used for the network by masking the network portion of the IP address. \
\
![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.17.53 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.19.32 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.20.54 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.21.49 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.31.22 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.34.44 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.35.37 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 5.03.03 pm.png>)

#### Intermediate Networking Terminology (MAC address, port, gateway vs router)



NAT - Network Address Translation\
Router - Router between networks\
NAT Gateway (Private Subnet to Public Subnet) \
Internet Gateway (VPC to the Internet)&#x20;



![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.52.05 pm.png>)



![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.58.32 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-09 at 4.59.20 pm.png>)



### On-Premise Network to VPC Connectivity

#### AWS Managed VPN

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.06.37 am.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.08.25 am.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.08.58 am.png>)

#### AWS Direct Connect&#x20;

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.09.19 am.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.10.47 am.png>)

#### AWS Direct Connect + VPN

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.11.30 am.png>)

#### AWS VPN CloudHub

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.12.46 am.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.13.37 am.png>)

#### Software VPN

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.13.56 am.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.14.32 am.png>)

#### Transit VPC

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.14.51 am.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.15.36 am.png>)



### VPC to VPC Connectivity

#### VPC Peering 🌟

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.22.07 am.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.23.39 am.png>)

#### Software VPN

#### Software to AWS Managed VPN

#### AWS Managed VPN

#### AWS Direct Connect

#### AWS PrivateLink 🌟

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.24.00 am.png>)

#### VPC Endpoints

![](<../../../.gitbook/assets/Screen Shot 2022-11-11 at 11.25.30 am.png>)



### Internet Gateways&#x20;

#### Internet Gateway



#### Egress-Only Internet Gateway



#### NAT Instance



#### NAT Gateway

![](<../../../.gitbook/assets/Screen Shot 2022-11-14 at 3.17.04 pm.png>)



### Routing&#x20;

#### Routing Tables

![](<../../../.gitbook/assets/Screen Shot 2022-11-14 at 4.30.49 pm.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 9.50.29 am.png>)

#### BGP Weithting

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 9.56.53 am.png>)

### Enhanced Networking

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 9.58.09 am.png>)

#### Placement Groups

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 9.59.30 am.png>)

#### ![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 10.54.04 am.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.47.14 pm.png>)



### Route 53

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.49.14 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.50.56 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.51.25 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.51.37 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.52.33 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.53.53 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.54.17 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.55.04 pm.png>)



![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.56.12 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.56.53 pm.png>)



### CloudFront&#x20;

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 7.58.40 pm.png>)





### Elastic Load Balancer

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.03.02 pm.png>)



![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.04.52 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.06.06 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.07.18 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.07.49 pm.png>)



![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.08.14 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.09.05 pm.png>)



### Exam Tips

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.09.58 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.10.58 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.11.41 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.12.17 pm.png>)

![](<../../../.gitbook/assets/Screen Shot 2022-11-15 at 8.14.01 pm.png>)



## LABS

### Creating and Configuring a Network Load Balancer in AWS&#x20;

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



### Troubleshooting Amazon EC2 Network Connectivity

![](<../../../.gitbook/assets/Screen Shot 2022-11-21 at 9.23.54 am.png>)

Instance 3 is unable to access the Internet.\
\- Instance: Public IP Address: Missing \
\- Security Group: OK\
\- Subnet: OK\
\- NACLS: Subnet was associated with wrong private NACLS rules.  \
\- Route Table: Missing 0.0.0.0/0 -> IGW rule \
\- IGW: OK\








