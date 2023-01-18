---
weight: 1
title: "Implementation settings for (very) simple Vivado projects"
date: 2020-01-01T00:00:00+08:00
lastmod: 2020-01-01T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["xilinx","settings"]
categories: ["tech-hardware"]

lightgallery: true

toc:
  auto: false
---
https://support.xilinx.com/s/article/58992?language=en_US

> [Place 30-415] IO Placement failed due to over utilization

Project Manager => Settings => Synthesis => More options. Add this flag:
```
-mode out_of_context
```



