---
layout: default
title: EC2 AMI Construction
grand_parent: Installation
parent: AWS
nav_order: 3
has_children: false
---


# EC-2: AMI Construction


```shell
sudo yum -y install java-17-amazon-corretto

sudo useradd datagen
sudo usermod datagen -G wheel

sudo mkdir -p /var/log/datagen/
sudo mkdir -p /home/datagen/
sudo chown datagen:datagen /var/log/datagen/
sudo chmod 755 /var/log/datagen/
sudo chown datagen:datagen /home/datagen/
sudo chmod 755 /home/datagen/

sudo su - datagen

wget https://datagen-repo.s3.eu-west-3.amazonaws.com/1.0.0/standalone/datagen-standalone-files.tar.gz 
tar -xvzf datagen-standalone-files.tar.gz
cd datagen_standalone-1.0.0/

echo '
./launch.sh \
  --min-mem=512M \
  --max-mem=1G \
  --log-dir=/tmp/datagen/ \
  --load-default-models=false
' > start.sh
chmod +x start.sh
./start.sh
```



