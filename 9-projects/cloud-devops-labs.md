# Cloud DevOps Labs

1. Create an architecture diagram on [https://app.diagrams.net/](https://app.diagrams.net/)
2.  Create the objects manually on the AWS console.\
    \- VPC \
    \- Subnets&#x20;

    <div align="left">

    <figure><img src="../.gitbook/assets/Screen Shot 2023-07-05 at 2.50.49 pm.png" alt="" width="403"><figcaption><p><a href="https://www.davidc.net/sites/default/subnets/subnets.html?network=10.1.0.0&#x26;mask=22&#x26;division=13.7230">https://www.davidc.net/sites/default/subnets/subnets.html?network=10.1.0.0&#x26;mask=22&#x26;division=13.7230</a></p></figcaption></figure>

    </div>

    \
    \- SG -> Create all sg, update sg rules to use sg as a source.\
    \- NACLS -> Create, edit inbound and outbound rules, associate w/ subnet.\
    \- IGW -> Create, Attach to VPC, \
    \- Route Table -> create 3, edit routes add igw to main, edit route add ngw to private.\
    \- Nat Gateway -> create, and update route table. \
    \
    \
    \
    \- EC2\
    Create an EC2 on a private subnet. \
    Error: Can't connect to the instance via console.\
    \- Attached AmazonSSMManagedInstanceCore role\
    \- Add RDP port on Nacls\
    \- \
    \
    \
    \
    \
    \- ALB\
    \






