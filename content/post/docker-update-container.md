---
date: "2022-02-25T22:16:41+08:00"
draft: false
tags:
- docker
- portainer
title: Docker Update Container
---

# Upgrade container cmd
use portainer as example

```bash
sudo docker stop portainer
sudo docker rm portainer

#for docker ce
sudo docker pull cr.portainer.io/portainer/portainer-ce:latest
sudo docker run -d -p 8000:8000 -p 9000:9000 -p 9443:9443 \
    --name=portainer --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data \
    cr.portainer.io/portainer/portainer-ce:latest

#for docker ee
sudo docker pull cr.portainer.io/portainer/portainer-ee:latest
sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:latest
```
