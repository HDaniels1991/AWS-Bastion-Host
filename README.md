
# Connecting to a AWS Instance in a private subnet using a Bastion host

## Introduction

This repo contains the required infrastructure to connect to an AWS Instance in a private subnet over a bastion host.

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