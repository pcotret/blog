---
weight: 1
title: "Static page for conference deadlines"
date: 2024-04-17T00:00:00+08:00
lastmod: 2024-04-17T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["backup"]
categories: ["tech-misc"]

lightgallery: true

toc:
  auto: false
---

How to sync files between a Google Drive and a local directory: https://linovox.com/how-to-sync-google-drive-on-linux/

```bash
# From Google to local
rclone sync google: /path/to/local/directory
# From local to Google
rclone sync /path/to/local/directory google:
```