---
author: "Pascal Cotret"
date: 2019-08-03
title: Convert an SVG to PNG in commande line using Inkscape (on Windows)
---

Change export-height if you want a bigger image 

```batch
@echo off
for %%f in (%*) do (
    echo %%~f
    "C:\Program Files\Inkscape\inkscape.exe" ^
      -z ^
      --export-background-opacity=0 ^
      --export-height=48 ^
      --export-png="%%~dpnf.png" ^
      --file="%%~f"

)
```