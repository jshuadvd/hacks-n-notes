# EC2

> Elastic Computing

- comes with **VPC** (Virtual Private Computing)
- you can pass variables to your EC2 instance through *tag instances* config 

## Step 3 config instance

- in **User data:** add this first line in the script with `#! /bin/bash -ex ``` so it will execute as bash
- Pass vars through **Tag Instance**

## ssh

`ssh -i ~/dev-ec2.pem 107.23.204.220 -l ec2-user`

- the IP is the Public IP from EC2
- the *ec2-user* is your username for that EC2

## Create groups

```bash
sudo groupadd www  # creates group with name 'www'
sudo usermod -a -G www ec2-user # adds user 'ec2-user' to group 'www'

groups # shows to which groups you belong to

# gives permisions to group 'www' to use the '/var/www' directory
sudo chown -R root:www /var/www/ 
sudo chmod 2775 /var/www

```