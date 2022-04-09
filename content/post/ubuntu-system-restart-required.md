---
title: "Ubuntu - System Restart Required"
date: 2022-04-09T18:30:57+08:00
draft: false
tags:
- ubuntu
---
## TLDR
To check update that caused system restart
```console
cat /var/run/reboot-required.pkgs
```

To check changelog about the update
```console
xargs apt-get changelog < /var/run/reboot-required.pkgs
```


### reference
https://linuxhandbook.com/system-restart-required-ubuntu/