# EC2

> Elastic Computing

- comes with **VPC** (Virtual Private Computing)
- you can pass variables to your EC2 instance through *tag instances* config 

## Key-value

- **EC2** requires a key-value file with extension *.pem* to authenticate.
- download the *.pem* file to your computer and change the permissions so it is only readable by you `chmod 0400 ~/file.pem`


## Step 3 config instance

- in **User data:** add this first line in the script with `#! /bin/bash -ex ``` so it will execute as bash
- Pass vars through **Tag Instance**

## ssh

`ssh -i <pem file path> -l <user>` user for EC2 is ubuntu
eg.

`ssh -i ~/dev-ec2.pem 107.23.204.220 -l ubuntu`

- the IP is the Public IP from EC2
- the *ec2-user* is your username for that EC2

## Create groups

```sh
sudo groupadd www  # creates group with name 'www'
sudo usermod -a -G www ec2-user # adds user 'ec2-user' to group 'www'

groups # shows to which groups you belong to

# gives permisions to group 'www' to use the '/var/www' directory
sudo chown -R root:www /var/www/ 
sudo chmod 2775 /var/www

```

## Storage

- encrypt sensitive data
- use IAM to be more protected

### Block Storage
- use **EBS** Block Storage for data you want to persist after the session expires
- Standard vs IOPS (Input-Output)
- IOPS is more expensive 
- You can create Snapshots and saved them in **EBS** (only adds incremental deltas to memory, to make storage more efficient)


## AMI
> Amazon Machine Image

- packaged env + settings to launch **EC2** instances
- this is a feature inside **EC2**


## Bootstrapping

> to create an **EC2** instance

- start services, update files, update dependencies
- register with load balancer
- run scripts & tools (cheff/puppet) or use OpsWorks (Cheff)
- access to instance meta-data using HTTP GET
- Cloud-Init to bootstrap

