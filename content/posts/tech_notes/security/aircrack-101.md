---
weight: 1
title: "Aircrack 101 - How to get the password of a WEP/WPA2 session captured in Wireshark"
date: 2020-01-01T00:00:00+08:00
lastmod: 2020-01-01T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["aircrack","security"]
categories: ["tech-security"]

lightgallery: true

toc:
  auto: false
---
## Prerequisites
- `sudo apt install aircrack-ng `
- Some wordlists/dictionaries. [Kali Linux](https://www.kali.org/) has already some of them.

## WiFi handshakes 101

Introduction from [@evilsocket](https://github.com/evilsocket)'s Pwnagotchi: [https://pwnagotchi.ai/intro/#wifi-handshakes-101](https://pwnagotchi.ai/intro/#wifi-handshakes-101)

## Dictionary-based attack

In order to test a PCAP with a given dictionary:

```bash
aircrack-ng -w <wordlist> <wireshark_file>
```

