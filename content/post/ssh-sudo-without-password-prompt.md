---
title: "SSH Sudo Without Password Prompt"
date: 2022-05-01T21:08:33+08:00
draft: false
tags:
- ubuntu
- ssh
---

Ubuntu can use sudo without password prompt. the below is the step to enable it.

1. open `/etc/sudoers` or create a file in `/etc/ sudoers.d/`
1. add a line 
   ```console
   user ALL=(ALL) NOPASSWD:ALL
   ```
1. done