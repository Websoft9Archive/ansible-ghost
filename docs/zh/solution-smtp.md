# SMTP

大量用户实践反馈，使用**第三方 SMTP 服务发送邮件**是一种最稳定可靠的方式。  

请勿在服务器上安装sendmail等邮件系统，因为邮件系统的路由配置受制与域名、防火墙、路由等多种因素制约，非常不稳定，且不易维护、诊断故障很困难。  

Ghost 以[Nodemailer](https://github.com/nodemailer) 作为邮件发送的模块，支持 Gmail, QQ, SendGrid 等[二十多种](https://github.com/nodemailer/nodemailer/tree/0.7/#well-known-services-for-smtp)邮箱服务。

下面以**QQ邮箱**为例，提供设置 Ghost 发邮件的步骤：

1. 在网易邮箱管理控制台获取 SMTP 相关参数
   ```
   SMTP host: smtp.qq.com
   SMTP port: 465 or 994 for SSL-encrypted email
   SMTP Authentication: must be checked
   SMTP Encryption: must SSL
   SMTP username: 45745412@qq.com
   SMTP password: #wwBJ8    //此密码不是邮箱密码，是需要通过 QQ 邮箱后台设置去获取的授权码
   ```
2. 修改 Ghost 配置文件 mail 相关配置段。特别注意的是 "from" 与 "user" 必须一致
   ```
      "mail": {
         "transport": "SMTP",
         "from": "45745412@qq.com",
         "options": {
            "service": "QQ",
            "auth": {
               "user": "45745412@qq.com",
               "pass": "#wwBJ8"
            }
         }
   },

   ```
3. 重启 Ghost 容器
   ```
   cd /data/wwwroot/ghost && docker-compose up -d
   ```
4. 登录 Ghost 后台，打开：【Manage】>【Staff】，通过【Invite People】 测试邮箱可用性

更多邮箱设置（QQ邮箱，阿里云邮箱，Gmail，Hotmail等）以及无法发送邮件等故障之诊断，请参考由Websoft9提供的 [SMTP 专题指南](https://support.websoft9.com/docs/faq/zh/tech-smtp.html)