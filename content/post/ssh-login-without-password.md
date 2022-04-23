---
title: "SSH Login Without Password"
date: 2022-04-23T09:29:46+08:00
draft: false
tags:
- ubuntu
- ssh
---

## Generate key
```console
ssh-keygen -t ed25519 [-C "your_email@example.com"]
```

## Upload public key to target PC
two methods, upload via `ssh-copy-id` or manually

### Method 1 - ssh-copy-id
```console
ssh-copy-id remote_username@server_ip_address
```

### Method 2 - manually
```console
cat ~/.ssh/id_rsa.pub | ssh remote_username@server_ip_address "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"
``` 

## Update ssh server config
1. remote to ssh server
1. open `/etc/ssh/sshd_config` and modify as follow
   ```text
   PasswordAuthentication no
   ChallengeResponseAuthentication no
   UsePAM no
   ```

## Restart 
restart PC or run follow command
```console
sudo systemctl restart ssh
```