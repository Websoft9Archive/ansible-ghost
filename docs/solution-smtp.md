# SMTP

Sending mail is a common feature for Ghost. With a large number of users' practice and feedback, only one way is recommended, that is, using the **third-party STMP service** to send the email.

> Do not try to install **Sendmail** or other Mail server software on your Cloud Server for sending mail, because it has great difficulty in maintenance and troubleshooting.

Ghost uses [Nodemailer](https://github.com/nodemailer) as a mail sending module and presents Gmail, QQ, SendGrid and[other services for smtp](https://github.com/nodemailer/nodemailer/tree/0.7/#well-known-services-for-smtp)

Taking using **SendGrid's SMTP Service** as an example to configure mail sending:

1. Log in SendGrid console, and prepare your SMTP settings as the following sample
   ```
   SMTP host: smtp.sendgrid.net
   SMTP port: 25 or 587 for unencrypted/TLS email, 465 for SSL-encrypted email
   SMTP Authentication: must be checked
   SMTP Encryption: must SSL
   SMTP username: websoft9smtp
   SMTP password: #fdfwwBJ8f    
   ```
2. Log in Ghost Console
3. Enter the SMTP settings
![Metabase SMTP](https://libs.websoft9.com/Websoft9/DocsPicture/en/metabase/metabase-smtp-websoft9.png)
4. Click the **Test Connection**, and you can get the feedback *"no errors were..."* if SMTP is successful.

More SMTP Service(Gmail, Hotmail, QQ mail, Yahoo mail, SendGrid and so on)  settings or Issues with SMTP, please refer to Websoft9's *[SMTP Guide](https://support.websoft9.com/docs/faq/tech-smtp.html)*
