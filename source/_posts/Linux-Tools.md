---
title: Linux 工具使用记录
date: 2019-12-02 16:15:03
tags:
   - SSH
   - jq
categories:
   - Linux
toc: true
---
## Linux 环境下常用工具
> 记录 linux 日常使用工具

<!-- more -->

### 安装 shell 脚本 json 转换工具 jq
- 添加epel源
```bash
wget http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
rpm -ivh epel-release-latest-7.noarch.rpm
yum repolist
```

- 查看下jq包是否存在
```bash
yum list jq
```

- 安装 jq
```bash
yum install jq
```

### ssh免密码登录配置
serverA  ->  serverB
- 在 serverA 上生成密钥对： `ssh-keygen -t rsa`
默认目录：~/.ssh 目录下生成密钥对

- 将公钥上传到serverB：`ssh-copy-id root@192.168.0.24`
输入密码后，即可查看 ~/.ssh/authorized_keys 是否有 serverA 的公钥文件内容；
