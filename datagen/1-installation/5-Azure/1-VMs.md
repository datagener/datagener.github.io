---
layout: default
title: Virtual machine
parent: Azure
grand_parent: Installation
nav_order: 1
has_children: false
---

# Virtual Machine

## Provision

In Azure > Virtual Machines >   and choose these settings:

- _Avaibility Options:_ Not required
- _Image:_ Ubuntu Server 24_04
- _Size :_ Standard_B1s
- _Disks:_ OS Disk Size of 30GB & disk type of Standard HDD

_Important: You must select an already azure ssh key or provide a public ssh key during creation_
_Important: You must have a network security group applied to your VM, allowing connections from your IP as TCP to port **4242**_

_Note: It is possible to use machines with better power (cpu/memory especially)_
_Note: It is possible to use other OS, as long as Java 17 can be installed, this is just an example_


## Installation

Then ssh to it.

**1.** Install Java : 
 
```shell
sudo apt update
sudo apt install -y openjdk-17-jre
```

**2.** Download & extract Datagen: 

```shell
 wget https://datagen-repo.s3.eu-west-3.amazonaws.com/1.0.0/standalone/datagen-standalone-files.tar.gz 
 tar -xvzf datagen-standalone-files.tar.gz
 cd datagen_standalone-1.0.0/
 ```

**3.** Launch it:

```shell
./launch.sh \
  --min-mem=512M \
  --max-mem=1G \
  --log-dir=/tmp/datagen/ \
  --load-default-models=false
```

## Access

Access UI using: http as protocol, the full hostname of PUBLIC IP and port 4242
as an example: ``http://20.61.59.19:4242/``

Use _admin/admin_ as user/password to connect and start to generate data:

  <img src="images/welcome_screen.png" width="700">


## Custom Configuration

Later to launch it in background process, add option: `--launch-with-nohup=true`, for example:
  
```shell
./launch.sh \
  --min-mem=512M \
  --max-mem=1G \
  --log-dir=/tmp/datagen/\
  --load-default-models=false \
  --launch-with-nohup=true
```