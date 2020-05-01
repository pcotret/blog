---
weight: 1
title: "Marp to PDF"
date: 2020-01-01T00:00:00+08:00
lastmod: 2020-01-01T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["marp"]
categories: ["tech-misc"]

lightgallery: true

toc:
  auto: false
---

Here is a way to convert Marp slides in PDF with emojis:
```bash
npx @marp-team/marp-cli main.md -o output.pdf --allow-local-files
```
- https://github.com/marp-team/marp-cli
- `nodejs` must be installed
