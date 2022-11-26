# Labs

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




## 3 - Scaling EC2 Using SQS

SQS\
\- Name: Messages\
\- Type: Standard\
\- Encryption: Amazon SQS key (SSE-SQS)\
\
Auto Scaling Group\
\- Desired capacity: 1\
\- Minimum capacity: 1\
\- Maximum capacity: 4\
\
CloudWatch\
Scale-Out\
\- Metric: SQS -> Approximate NumberOfMessagesVisable\
\- Period: 1 minute\
\- Conditions: Static, Greater > 500 \
\
Scale-In\
\- Metric: SQS -> Approximate NumberOfMessagesVisable\
\- Period: 1 minute\
\- Conditions: Static, Lower > 500&#x20;

```python
#!/usr/bin/env python3

import argparse
import logging
import sys
import uuid
from time import sleep

import boto3
from botocore.exceptions import ClientError

parser = argparse.ArgumentParser()
parser.add_argument("--queue-name", "-q", default="Messages", help="SQS queue name")
parser.add_argument("--interval", "-i", default=0.1, help="timer interval", type=float)
parser.add_argument("--message", "-m", help="message to send")
parser.add_argument("--log", "-l", default="INFO", help="logging level")
args = parser.parse_args()

if args.log:
    logging.basicConfig(format="[%(levelname)s] %(message)s", level=args.log)
else:
    parser.print_help(sys.stderr)

sqs = boto3.client("sqs")

try:
    logging.info(f"Getting queue URL for queue: {args.queue_name}")
    response = sqs.get_queue_url(QueueName=args.queue_name)
except ClientError as e:
    logging.error(e)
    exit(1)

queue_url = response["QueueUrl"]

logging.info(f"Queue URL: {queue_url}")

while True:
    try:
        message = str(uuid.uuid4())
        logging.info("Sending message: " + message)
        response = sqs.send_message(QueueUrl=queue_url, MessageBody=message)
        logging.info("MessageId: " + response["MessageId"])
        sleep(args.interval)
    except ClientError as e:
        logging.error(e)
        exit(1)
```



## 4 - Auto-Scaling Experiment

Step 1: Install the "Stress" Linux tool ->&#x20;

```
brew install stress-ng
sudo apt-get install stress
```

Step 2:&#x20;





