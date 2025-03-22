---
title: mkdocs-install
date: 2025-03-19 21:00
author: haromeng
tags:
  - mkdocs
status: true
---

## 配置环境

### 安装python

进入python官网下载python，在安装的过程中要选择**add python 3.x to PATH**

输入`python --version`查看Python是否安装成功

### 安装pip

输入以下指令将python的包管理器更新至最新版

```bash
pip install --upgrade pip
```

### 安装mkdocs

使用pip安装mkdocs:

```bash
pip install mkdocs
```

检测mkdocs是否安装成功:

```bash
mkdocs --version
```


## 启动

生成mkdocs工作目录:

```bash
mkdocs new mkdocs-project
```

启动服务:

```bash
mdkcos serve
```

服务启动后便可以通过`127.0.0.1:8000`访问

