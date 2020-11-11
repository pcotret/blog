---
weight: 1
title: "Image processing"
date: 2020-01-01T00:00:00+08:00
lastmod: 2020-01-01T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["scripts"]
categories: ["tech-misc"]

lightgallery: true

toc:
  auto: false
---

## Convert an SVG to PNG in commande line using Inkscape (on Windows)
Change export-height if you want a bigger image:

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

## Resize an image with Inkscape
```powershell
for %%f in (*.png) do convert.exe %%f -resize 384x384 -background black -gravity center -extent 384x384 %%f
```

## Convert a Dia diagram in EPS then PDF
```bash
#!/bin/bash
filename=$(basename -- $1)
extension="${filename##*.}"
filename="${filename%.*}"
echo $filename
dia -e $filename.eps -t eps $1
epstopdf --outfile=$filename.pdf $filename.eps
```
