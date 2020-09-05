# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 配置

官方提供了很多配置方案，参考：[Tutorials](https://ghost.org/tutorials/) 和 [FAQ](https://ghost.org/faq/)

## 域名绑定

当服务器上只有一个网站时，不做域名绑定也可以访问网站。但从安全和维护考量，**域名绑定**不可省却。

以示例网站为例，域名绑定操作步骤如下：

1. 确保域名解析已经生效  
2. 使用 SFTP工具连接服务器，修改 [Nginx 虚拟主机](/zh/stack-components.md#nginx)配置文件，绑定域名（如果想采用域名，此步骤必做）
   ```
    listen 80;
    server_name ghost.yourdomain.com;
   ```

3. 使用 SFTP工具连接服务器，修改 [Ghost 配置文件](/zh/stack-components.md#ghost)中的 URL 域名地址（同上）
   ```
   {
   "url": "http://ghost.yourdomain.com",
   "server": {
      "port": 2368,
      "host": "0.0.0.0"
   },
   ```
4. 运行相关命令，重启以下服务后以上设置才生效
   ```
   sudo systemctl restart nginx
   cd /data/wwwroot/ghost && sudo docker-compose up -d && sudo docker restart ghost
   ```

## 重置密码

常用的 Ghost 重置密码相关的操作主要有修改密码和找回密码两种类型：

### 修改密码

1. 登录 Ghost 后台，依次打开：【Manage】>【Staff】，找到所需修改密码的账号对象
  ![Ghost 修改密码](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-modifypw001-websoft9.png)

2. 开始修改密码
  ![Ghost 修改密码](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-modifypw002-websoft9.png)

### 找回密码

如果用户忘记了密码，建议通过邮件的方式找回密码：

1. 完成 [SMTP 设置](/zh/solution-smtp.md)

2. 打开 Ghost 登录页面，点击【Forgot】开始通过邮件找回密码
  ![Ghost 找回密码](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-codeinjection-websoft9.png)