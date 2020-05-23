
# Connecting to a AWS Instance in a private subnet using a Bastion host

## Introduction

This repo contains the required infrastructure to connect to an AWS Instance in a private subnet over a bastion host.

## Quick Start

To get started clone the repo:

```git clone https://github.com/HDaniels1991/AWS-Bastion-Host.git```

The repo requires you to have an AWS profile called: personal. It is possible to change the profile name in the variables.tf file.

The next step is to generate the SSH keys. In the terraform directory create another directory called keys and create your keys with the following command:

```
# create the keys
ssh-keygen -f mykeypair
 
# add the keys to the keychain
ssh-add -K mykeypair  
```

## SSH Config File

```
Host bastion-instance
   HostName <Bastion Public IP>
   User ubuntu

Host private-instance
   HostName <Private IP>
   User ubuntu
   ProxyCommand ssh -q -W %h:%p bastion-instance
```

## Author:
Harry Daniels