---
weight: 1
title: "Building Wireshark from source"
date: 2020-09-20T00:00:00+08:00
lastmod: 2020-09-20T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["wireshark","networks"]
categories: ["tech-networks"]

lightgallery: true

toc:
  auto: false
---

## Download and build
```bash
git clone https://gitlab.com/wireshark/wireshark
sudo wireshark/tools/./debian-setup.sh --install-qt5-deps (--install-optional)
cd wireshark
mkdir build
cd build
cmake .. -DUSE_qt6=OFF
make -j$(nproc)
sudo make install
```
