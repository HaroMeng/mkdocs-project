---
title: callouts
date: 2025-03-20 08:38
author: haromeng
tags:
  - mkdocs
  - obsidian
status: true
---

## 安装插件

### 步骤1：安装 mkdocs-callouts 插件

1. **安装插件**：
    ```bash
    pip install mkdocs-callouts
    ```

2. **启用插件**：
    在 `mkdocs.yml` 配置文件中添加：
    ```yaml
    plugins:
      - search  # 确保保留默认搜索插件
      - callouts
    ```

## 调整主题样式

1. 安装Material主题：
    ```bash
    pip install mkdocs-material
    ```
2. 配置主题与Callou兼容：
    在`mkdocs.yml`中设置
    ```bash
    theme:
      name: material
      features:
        - content.code.copy  # 启用代码块复制按钮（可选）
    ```