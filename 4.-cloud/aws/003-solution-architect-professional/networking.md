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



####
