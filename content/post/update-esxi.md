---
title: "Update ESXI via command"
date: 2022-03-23T21:03:42+08:00
draft: false
tags:
- esxi
- vmware
---

VMware ESXI can be updated via command line, here is a quick reference

1. download latest patch from vmware web site https://customerconnect.vmware.com/patch. ESXI patch should be cumulative, therefore, download the latest one
1. upload the patch to esxi datastore
1. enable esxi ssh via web management console
1. login esxi ssh `root@server-ip` and run below commend
   ```sh
    esxcli software vib update -d "/vmfs/volumes/datastore1//ESXi600-201605001.zip"
    
    reboot -f
   ```
1. done