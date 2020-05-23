
# Connecting to a AWS Instance in a private subnet using a Bastion host

## Introduction

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