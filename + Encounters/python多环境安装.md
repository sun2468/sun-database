---
FileName: python多环境安装
Other: 
 - 其他
title: python多环境安装
type: null
uid: 20221021203144
vikaLink: https://vika.cn/workbench/dstpaAfExTHBNUNusm/viwvRoe0VMYoJ/recUQG8Acmkwb
tags: 
 - python
 - 多环境
aliases: 
 - 多环境安装
recordID: recLdbNejZg7f
---

# python多环境安装

```
# 创建新环境，<环境名称>, python 版本
conda create -n py310 python=3.10
# 删除环境
conda remove -n py310d --all
# 进入、激活环境
conda activate py310
# 退出环境
conda deactivate
# 查看所有虚拟环境及当前环境
conda info -e
```