---
link: https://blog.csdn.net/weixin_40615155/article/details/108901854
title: Mac安装并运行 nginx
description: 小白，刚买的 Mac，在自己摸索着装环境和软件，遇到很多问题，简单记录一下1. 安装 brew/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"【报错】： Failed to connect to raw.githubusercontent.com port 443: Connection refused换个命令重新安装：/bin/zsh -c ".
keywords: mac运行nginx
author: Alice_hhu Csdn认证博客专家 Csdn认证企业博客 码龄4年 暂无认证
date: 2020-10-02T08:28:06.000Z
publisher: null
stats: paragraph=23 sentences=16, words=71
---
> 小白，刚买的 Mac，在自己摸索着装环境和软件，遇到很多问题，简单记录一下

## 1. 安装 brew

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

**【报错】：** Failed to connect to raw.githubusercontent.com port 443: Connection refused

**换个命令重新安装：**

```bash
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

（参考： _ [https://www.cnblogs.com/jiefangzhe/p/12929078.html](https://www.cnblogs.com/jiefangzhe/p/12929078.html)_）

**验证安装成功：**

```bash
brew -v
```

## 2. 安装 nginx

```bash
brew install nginx
```

**验证安装成功：**

```bash
nginx -v
```

## 3. 修改 nginx配置

**打开配置文件： `/usr/local/etc/nginx/nginx.conf`**
_（ps：使用命令行在 `/usr/local/etc/nginx/` 目录下 `open nginx.conf` 失败了，没有程序支持打开该类型文件）_
**快捷键 shift + command + g** 打开指定目录找到配置文件手动打开修改配置
**1. 定义需要转发的服务地址：**![](https://img-blog.csdnimg.cn/20201002161613502.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDYxNTE1NQ==,size_16,color_FFFFFF,t_70#pic_center)
**2. 配置请求转发：**![](https://img-blog.csdnimg.cn/20201002160855663.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDYxNTE1NQ==,size_16,color_FFFFFF,t_70#pic_center)

## <a name="4__nginx_36">;</a>  4. 运行 nginx

（本来在网上搜了一下有个 LaunchRocket，一时没运行起来，还没查出什么原因，先改用了命令行）
**1. 运行 nginx**

```bash
sudo nginx
```

**2. 重新加载 nginx**

```bash
sudo nginx -s reload
```

**3. 关闭 nginx**

```bash
sudo nginx -s stop
```

（参考[https://blog.csdn.net/weixin_45825077/article/details/107134300](https://blog.csdn.net/weixin_45825077/article/details/107134300)）
