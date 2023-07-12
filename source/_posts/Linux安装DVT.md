---
title: Linux安装DVT
date: 2023-07-12 14:48:19
categories: 
- 环境搭建
tags: 
- Linux
- EDA
---
1. 下载解压
2. 免安装，直接复制 dvt_eclipse 到安装路径，我在 usr/ 下面新建了 app dir
```bash
cp ./dvt_eclipse /usr/app
```

3. 复制 license 到 dvt_eclipse
```bash
cd license_dir
cp ./dvt.lic /usr/app/dvt_eclipse/licenses
```
4. 设置环境变量
```bash
export DVT_HOME=/usr/app/dvt_eclipse
export DVT_LICENSE_FILE=$DVT_HOME/licenses/dvt.lic
export DVT_HOME=/usr/app/dvt_eclipse
export PATH=$DVT_HOME/bin/:$PATH
alias dvt="dvt.sh &"
```