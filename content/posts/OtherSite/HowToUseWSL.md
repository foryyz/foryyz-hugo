---
title: 'wsl的基础使用说明'
date: 2024-06-21T00:59:24+08:00
draft: false
---

> Author - yyz
>
> Create Time - 2024/06/21
>
> **Last Update Time - 2024/06/21**

# WSL2

## 1 基础语法

- 查看 `wsl --list`
- 卸载 `wsl --unregister SystemName`
- 关机 `wsl --shutdown`



# Ubuntu On WSL 机器学习配置

## 0 基本设置

安装后在Linux系统中使用 `nvidia-smi` 查看是否连接到物理机Nvidia驱动
更新软件列表 `sudo apt-get update`
安装必备的工具包 `sudo apt-get install build-essential`

## 1 安装CUDA Toolkit

下载地址：[CUDA Toolkit 12.5 Downloads | NVIDIA Developer](https://developer.nvidia.com/cuda-downloads)

选项如下：Linux → x86_64 → WSL_Ubuntu → 2.0 → runfile(local)

按操作执行命令：

```bash
wget https://developer.download.nvidia.com/compute/cuda/12.5.0/local_installers/cuda_12.5.0_555.42.02_linux.run
sudo sh cuda_12.5.0_555.42.02_linux.run
```

1. 选择 accept
2. 选择 install
3. 添加环境变量

```bash
export PATH="/usr/local/cuda-12.5/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-12.5/lib64:$LD_LIBRARY_PATH"
```

检验是否安装成功：`nvcc -V`



> [【2024】Windows 11 安装WSL2并搭建深度学习环境（Docker，Pytorch）_win11 安装wsl2-CSDN博客](https://blog.csdn.net/m0_63070489/article/details/135602337)
