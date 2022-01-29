---
title: "Git Cheatsheet"
date: 2022-01-29T19:58:37+08:00
draft: true
---


1. remove git submodule but keep files
``` shell
mv subfolder subfolder_tmp
git submodule deinit subfolder
git rm --cached subfolder
mv subfolder_tmp subfolder
git add subfolder
```
