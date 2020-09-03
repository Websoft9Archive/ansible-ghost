# 初始化安装

在云服务器上部署 Ghost 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 若想用域名访问 Ghost，请先到 **域名控制台** 完成一个域名解析

## Ghost 安装向导

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://域名* 或 *http://Internet IP*, 进入前台界面
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-bootpage-websoft9.png)

2. 访问网址：*http://域名/ghost* 或 *http://Internet IP/ghost*, 进入后台
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-register001-websoft9.png)

3. 开始创建管理员账号，以邮箱地址为用户名，密码不要设置过于简单  
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-register002-websoft9.png)

4. 使用 SFTP工具连接服务器，修改 [Nginx 虚拟主机](/zh/stack-components.md#nginx)配置文件，绑定域名（如果想采用域名，此步骤必做）
   ```
    listen 80;
    server_name ghost.yourdomain.com;
   ```

5. 使用 SFTP工具连接服务器，修改 [Ghost 容器编排文件](/zh/stack-components.md#ghost)中的 URL 域名地址（同上）
   ```
   {
   "url": "http://ghost.yourdomain.com",
   "server": {
      "port": 2368,
      "host": "0.0.0.0"
   },
   ```
7. 运行相关命令，重启以下服务后以上设置才生效
   ```
   sudo systemctl restart nginx
   cd /data/wwwroot/ghost && sudo docker-compose up -d && sudo docker restart ghost
   ```

> 需要了解更多 Ghost 的使用，请参考官方文档：[Ghost Documentation](https://docs.ghost.org/docs)

## 常见问题

#### 浏览器打开IP地址，无法访问 Ghost（白屏没有结果）？

您的服务器对应的安全组 80 端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### 本部署方案是采用什么方式部署 Ghost？

采用 Docker 安装 Ghost，数据库存放在服务器的 MySQL 中