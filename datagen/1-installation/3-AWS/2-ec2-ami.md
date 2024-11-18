---
layout: default
title: EC2 AMI
grand_parent: Installation
parent: AWS
nav_order: 2
has_children: false
---


# EC-2: Based on AMI

## Provision

**This is one is using free-tier, hence free machines on AWS but with limited resources**

In AWS > EC 2 > Launch Instance and choose these settings:

- _AMI:_ ami-0292f0db07da061b6
- _Size:_ t2.micro
- _Key Pair:_ Yours
- _Security Group:_ Allowing ssh from your IP
- _Volume:_ 30GB

_Note: If you have no access to that AMI, please email frisch@cloudera.com_

_Important: Once launched, add in security groups the following port: **4242** as Custom TCP to your IP_

_Note: It is possible to use non-free-tier machines with better power (cpu/memory especially)_


## Installation

Then ssh to it (using its public name and _ec2-user_) and follow these steps:

```shell
sudo su - datagen
cd datagen_standalone-1.0.0/
/start.sh
```



