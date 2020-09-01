# Ghost Notes

组件名称：Ghost  
安装文档：https://ghost.org/docs/setup/  
配置文档：https://ghost.org/docs/setup/  
支持平台： Debian家族 | RHEL家族 | Windows | Docker  

## 概要

Ghost 从业务上说它是一个支持售卖（订阅）的博客系统，从技术架构上讲它是一个前端与后端分离的内容管理系统。100%开源，运行速度非常快。

## 环境要求

* 程序语言：Node 
* 应用服务器：Nginx
* 数据库：MySQL or SQLite
* 依赖组件：无
* 服务器配置：最低1核1
* 其他：

## 安装说明

为了避免 Node 包管理在全局上的混乱特性，建议采用 Docker 安装 Ghost。MySQL数据库安装在宿主机上，供 Ghost 容器调用。  

安装的要点集中在 docker-compose.yml 文件  

## 账号密码

### 数据库密码

自行设置

### 后台账号

* 登录地址：http://url/ghost
* 账号密码：自行注册设置

## 常见问题

#### Ghost 镜像是官方提供的吗？

不是，是 Docker-Hub 提供的
