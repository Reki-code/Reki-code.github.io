---
title: "为libreoffice添加字体"
date: 2020-12-03T12:42:14+08:00
draft: false
tags: [linux, LibreOffice]
---

[跳过废话](#解决方案)

## Linux 安装字体

通常安装字体可以通过自带的包管理系统安装，也可以手动安装。

### 手动安装字体

在系统范围内（对所有用户有效）安装字体，可以将字体文件移动到 `/usr/share/fonts/`目录。这些文件需要对每个用户而言都是可读的，使用`chmod`设置合理的权限（文件至少为`0444`, 目录至少为`0555`）。

为单个用户安装字体，使用`$XDG_CONFIG_HOME/fontconfig/fonts.conf` 如果` XDG_CONFIG_HOME`没有设置则使用`$HOME/.config/fontconfig/fonts.conf`目录（`$HOME/.fonts`有可能工作，不过已经过时了[^fonts.conf]）

最后使用`fc-list : file | grep "字体文件名"`验证安装。

## 缺陷

安装中易宋体之后，某些网址直接调用该字体导致字体显示效果不理想。最终选择移除系统中的中易宋体文件。 但是实验报告又要求使用中易宋体。

## 解决方案

LibreOffice 支持单应用添加字体。

1. 在用户配置目录[^userprofile]`$HOME/.config/libreoffice/4/user`（LibreOffice 4 之后的版本）下新建`fonts`文件夹。
2. 将需要的字体文件复制到`fonts`目录里。
3. 打开 LibreOffice 就可以看到相应的字体。 ![LibreOffice with SimSum](/posts/img/LibreOfficeSimSun.png)

[^fonts.conf]: [fonts.conf is deprecated?](https://www.linuxquestions.org/questions/slackware-14/fonts-conf-is-deprecated-4175488781/)
[^userprofile]: [LibreOffice 用户配置](https://wiki.documentfoundation.org/UserProfile/zh-hans#.E9.BB.98.E8.AE.A4.E4.BD.8D.E7.BD.AE)
