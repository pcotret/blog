---
weight: 1
title: "Xilinx settings in `~/.bashrc`"
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
Just because I'm too lazy to rewrite the few lines needed to get Vivado running.

## Requirements

- Xilinx tools are installed in `/opt/Xilinx`
- You have write rights in this repository. Otherwise, just run a `chown -R on /opt/Xilinx`
- For this note, I assume you have the 2018.2 version installed on a 64-bit OS.
- Your license file is `/opt/Xilinx/Xilinx.lic`

These lines have to be added at the end of your `~/.bashrc` file

```bash
source /opt/Xilinx/Vivado/2018.2/settings64.sh # To be completed
```



