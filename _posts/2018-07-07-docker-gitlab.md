---
title: Docker 之 GitLab 局域网代码托管
date: 2018-07-07 16:22:06
categories:
- Docker
tags:
- docker
- gitlab
---

&lt;架构探险之路> Docker搭建微服务自动部署平台，让我们来了解下基于Docker的gitlab局域网代码托管吧！

* * *

# Docker 之 GitLab 局域网代码托管

## 部署

-   拉取镜像

    docker pull gitlab/gitlab-ce

-   本地域名DNS映射配置

    sudo vi /etc/hosts
    添加 127.0.0.1 gitlab.yiyuery.com

-   运行

    docker run -d -m 1024m -h gitlab.yiyuery.com -p 22:22 -p 80:80 -v ~/gitlab/etc:/etc/gitlab -v ~/gitlab/log:/var/log/gitlab -v ~/gitlab/opt:/var/opt/gitlab --name gitlab --restart=always gitlab/gitlab-ce

`此处需注意关闭其他占用80端口的进程`

    域名的映射默认使用的是80端口

-   git 操作

    创建gitlab工程

![输入图片说明](https://images.gitee.com/uploads/images/2018/0708/100245_fe2789c0_912956.png "屏幕截图.png")

  参考上图完成推送代码到远端[gitlab仓库]

![输入图片说明](https://images.gitee.com/uploads/images/2018/0708/152004_e20c3a06_912956.png "屏幕截图.png")



## 更多

> 扫码关注“架构探险之道”，回复`文章名称`获取更多源码和文章资源

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190403222309957.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzI4NjkwNDE3,size_16,color_FFFFFF,t_70)

> 知识星球(扫码加入获取源码和文章资源链接)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190403222322267.jpeg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzI4NjkwNDE3,size_16,color_FFFFFF,t_70)
