---
title: "Synology Hyperdrive to Edu Onedrive"
date: 2022-06-06T11:11:02+08:00
draft: false
tags:
- Synology
- Hyperdrive
- Onedrive
---

Synology hyperdrive don't support business onedrive. This is a quick reference for using docker to setup a HTTP proxy for login onedrive

1. docker
   ```console
   docker run --name sharepoint-proxy -d -p 3000:3000 -e PROXY_TARGET=https://example-my.sharepoint.net/ --restart always skleeschulte/basic-to-sharepoint-auth-http-proxy:v0.0.1
   ```
2. setup webdav in hyperdrive
   ```text
   server: http://localhost:3000/personal/<username>/Documents
   username: username@domain.com
   ```

## Reference
 https://github.com/skleeschulte/basic-to-sharepoint-auth-http-proxy

