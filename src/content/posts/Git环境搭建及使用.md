---
title: Git环境搭建与使用
published: 2026-07-05
updated: 2026-07-05
description: Git环境搭建及其使用操作。
tags: [开发环境, Git]
category: 开发环境
author: wanghu
image: ./images/blog_1.avif
---

# Git安装
Linux / WSL 下安装 git 指令：

```shell
sudo apt update
sudo apt upgrade
sudo apt install git
```

windows 下安装 git，根据自己电脑架构选择，下载 git 软件，并运行按照提示安装即可

[https://git-scm.com/install/windows](https://git-scm.com/install/windows)

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783239248825-b58bb94e-7c8b-4b93-b575-a844d2225941.png)

# Git环境配置
## 基本配置
Linux / WSL 下直接在终端中配置，windows下可以进入右键进入到 Git Bash中进行配置，如图所示

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783239431966-3c4ca198-9237-453f-b1da-c82efebf3d7b.png)

```shell
# 配置用户名邮箱
git config --global user.name "Your Name"
git config --global user.email "your.email@xxx.com"

# 行尾处理（避免跨平台换行问题）
git config --global core.autocrlf input

# 忽略文件权限变化（适用于 WSL）
git config --global core.filemode false

# 默认分支命名为 main
git config --global init.defaultBranch main

# 启用彩色输出
git config --global color.ui auto

# 将 /data 加入安全目录（避免 detached HEAD 警告）
git config --global --add safe.directory /data
```

## SSH远程配置
配置SSH远程连接 github

1. 安装 ssh，默认情况下 win10、win11中 ssh 是直接可以运行的，WSL / Ubuntu下安装指令

```shell
sudo apt install openssh-server openssh-client
```

2. 查看是否安装成功，如下图安装成功后会显示 ssh 相关指令

```shell
ssh
```

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783239787616-eb4986c3-ed62-4310-bcd4-348cb07de30b.png)

3. ssh生成公钥和私钥

```shell
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

生成过程中直接回车即可，不需要设置相关密码

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783239963282-717dbfb7-7404-417c-9ab1-95a08532c991.png)

4. 将公钥配置到 github 网站中

复制公钥

```shell
cat ~/.ssh/id_rsa.pub
```

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783240050157-ef59d9ea-7a08-4acc-ac20-7ea0a0e5804b.png)

设置到 github 中

登录到github后，点击 Settings 进入到设置

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783240093629-02060407-7783-4f00-87bd-ff2b64e36c83.png)

点击 SSH and GPG keys，并点击New SSH key

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783240171497-4a3d2548-da96-4b29-a8d2-9b6db24d4c94.png)

将复制的公钥填入到 Key 中，并点击Add SSH key即可

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783240238295-0d97d2a3-5c18-4010-893b-5fbbcd0e64e1.png)



5. 后续下载 github 中项目即可通过 ssh 方式进行下载

例如

![](https://cdn.nlark.com/yuque/0/2026/png/47806823/1783240342250-d1e68c09-b435-4318-bb1a-e97cd61a325a.png)

```shell
git clone git@github.com:remzi-arpacidusseau/ostep-homework.git
```



# Git 基本使用
正在更新中......

