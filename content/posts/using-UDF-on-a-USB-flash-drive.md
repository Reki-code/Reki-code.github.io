---
title: "关于我在新 u 盘上使用 UDF 文件系统这件事"
date: 2020-09-26T15:35:45+08:00
draft: false
tags: ["udf"]
---

# UDF 是什么
>（Universal Disk Format，简称UDF）是一个使用在光学存储媒体的文件系统的规格。它实行了ISO/IEC 13346标准（亦称为ECMA-167）。它亦是用作取代ISO 9660，现时已经广泛地用于可写光学存储媒体上。UDF是由光学存储技术协会（Optical Storage Technology Association，OSTA）开发并维护的。

从名字上来看，UDF 主要是用于光学存储设备的文件系统，但是它也可以用在任何可移动存储介质上，而且还有着不少的好处。
- 三大主流桌面操作系统 Windows[^xp_support]、Mac、Linux 都能够正常读写 UDF 文件系统。
- 开放标准，常用文件系统 FAT、NTFS 都属于微软。
- 为信息交换而生的文件系统

# 如何格式化
使用 [format-udf](https://github.com/JElchison/format-udf) 脚本，快速格式化块设备（硬盘和 u 盘）。该脚本能为你提供最大的兼容性。但是该脚本只能运行在 Mac 和 Linux 上。

# 最后一点小问题
如果你在 Windows 上隐藏了一个文件，那么你可能发现该文件在 Linux 下也不可见，熟悉 Linux 系统的你可能会使用`ls -a`命令查看隐藏的文件，但是文件依然不可见。

这时候你需要添加挂载参数`unhide`[^unhide]来查看那些被 Windows 隐藏起来的文件。

[^xp_support]: Windows XP 默认情况下只能读取，不能写入。[文件系统的对比 -- 支持的操作系统](https://en.wikipedia.org/wiki/Comparison_of_file_systems#OS_support).
[^unhide]: [UDF file system -- The Linux Kernel documentation](https://www.kernel.org/doc/html/latest/filesystems/udf.html)

