# FAQ

#### Ghost 支持中文吗？

Ghost 的后台不支持中文，但是前台支持中文（需主题中有中文）

#### Ghost 系统中的 Post 与 Page 有什么区别？

Post 是文章的意思，每一篇博客文章即一个 Post；Page 是页面的意思，网站中的首页，公司介绍等都可称之为 Page。  

在 Ghost 系统中，每一个新建的 Page，都需要在主题中有对应的模板文件与之匹配。

#### Ghost 有哪些用户角色？

参考官方文档 [Managing your team in Ghost](https://ghost.org/help/managing-your-team/)

#### Ghost 是否支持对默认主题 casper 进行修改？

不支持，只可以修改自上传的主题。

#### 是否可以通过命令行修改Ghost后台密码？

不可以

#### 如果没有域名是否可以部署 Ghost？

可以，访问`http://服务器公网IP` 即可

#### 设置域名访问？

首先要解析域名，然后登录服务完成[域名绑定操作](/zh/solution-more.md#域名绑定)

#### 数据库 root 用户对应的密码是多少？

密码存放在服务器相关文件中：`/credentials/password.txt`

#### 是否有可视化的数据库管理工具？

有，内置phpMyAdmin，访问地址：*http://服务器公网IP:9090*

#### 如何禁止外界访问phpMyAdmin？

云控制台安全组中关闭 9090 端口即可

#### 是否可以修改Ghost目录路径？

可以，通过修改 Ghost 容器编排文件： */data/wwwroot/ghost/docker-compose.yml* 中的持久化目录实现

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R root.root /data/wwwroot/ghost
# 读写执行权限
find /data/wwwroot/ghost -type d -exec chmod 750 {} \;
find /data/wwwroot/ghost -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
