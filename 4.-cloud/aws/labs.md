# Labs

### 1 - Creating and Configuring a Network Load Balancer in AWS&#x20;

###

###

### 2 - Troubleshooting Amazon EC2 Network Connectivity

![](<../../.gitbook/assets/Screen Shot 2022-11-21 at 9.23.54 am.png>)

Instance 3 is unable to access the Internet.\
\- Instance: Public IP Address: Missing \
\- Security Group: OK\
\- Subnet: OK\
\- NACLS: Subnet was associated with wrong private NACLS rules.  \
\- Route Table: Missing 0.0.0.0/0 -> IGW rule \
\- IGW: OK\
