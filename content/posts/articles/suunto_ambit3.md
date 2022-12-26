---
weight: 1
title: "Suunto Ambit and Linux"
date: 2022-03-18T00:00:00+08:00
lastmod: 2022-03-18T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["suunto","gps"]
categories: ["articles"]

lightgallery: true

toc:
  auto: false
---

> Just copying instructions from https://debian-facile.org/viewtopic.php?id=29025 in case this case falls down

Prerequisites :
- Wine staging: https://wiki.winehq.org/Download
- Winetricks: https://wiki.winehq.org/Winetricks
- Openambit: https://github.com/openambitproject/openambit

Watch with R/W for everyone:
```bash
sudo wget https://raw.githubusercontent.com/openambitproject/openambit/master/src/libambit/libambit.rules -O /etc/udev/rules.d/libambit.rules
sudo udevadm control --reload-rules && udevadm trigger
``` 

32-bit Wine prefix:
```bash
export WINEARCH="win32"
``` 

Install .NET 4.5.2:
```bash
winetricks dotnet452
``` 

Windows 7 mode:
```bash
winetricks win7
``` 

Disable SDL detection in Wine (otherwise, watch isn't detected):
```bash
wine reg add 'HKLM\System\CurrentControlSet\Services\WineBus' /v 'Enable SDL' /t REG_DWORD /d 0 /f
``` 

Download and install Suuntolink:
```bash
wget -P ~/.wine/drive_c/ https://suuntolink.static.movescount.com/Suuntolink_installer.exe
wine ~/.wine/drive_c/Suuntolink_installer.exe
``` 

In case of a bug, just restart Wine:
```bash
wineserver -k
```