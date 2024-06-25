---
title: '饥荒联机版服务器搭建教程(Ubuntu22)'
date: 2024-06-25T22:45:11+08:00
draft: false
---

# Don't Starve Together

华为云 - Ubuntu22.04 - 2核4G 5M宽带

## 1 更新软件 安装依赖

```bash
sudo add-apt-repository multiverse
sudo dpkg --add-architecture i386

sudo apt update
sudo apt upgrade
sudo apt install libstdc++6 libgcc1 libcurl4-gnutls-dev:i386 lib32z1 lib32stdc++6

```

## 2 安装SteamCMD和饥荒联机版

```bash
mkdir ~/steamcmd
cd ~/steamcmd

wget https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz
tar -xvzf steamcmd_linux.tar.gz
./steamcmd.sh
#输入左侧出现“steam>”说明steamcmd启动成功

force_install_dir "../dontstarvetogether_dedicated_server"
login anonymous
app_update 343050 validate
#当执行完成后输入'quit'退出steam服务
quit
```



