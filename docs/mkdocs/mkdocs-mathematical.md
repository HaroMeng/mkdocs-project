---
title: mkdocs mathematical formula rendering
date: 2025-03-22 11:27
author: haromeng
tags:
  - mkdocs
  - 美化
status: true
---

## 安装插件

安装`pymdownx.arithmatex`插件：

```bash
pip install pymdown-extensions
```

## 配置mkdocs.yaml

启用`pymdownx.arithmatex`插件

```bash
markdown_extensions:
  - pymdownx.arithmatex:
      generic: true
      
extra_javascript:
  - https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js
  
```



## 检测是否安装成功

```bash
# 数学公式示例

这是一个行内公式：$E = mc^2$

这是一个块级公式：

$$
\int_{a}^{b} f(x) \, dx
$$
```



$$
\int_{a}^{b} f(x) \, dx
$$
