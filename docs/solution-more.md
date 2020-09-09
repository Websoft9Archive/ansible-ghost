# More

Each of the following solutions has been proven to be effective and we hope it can give you help.

## Configuration 

Ghost official offers many configurations. Please refer to[Tutorials](https://ghost.org/tutorials/) and [FAQ](https://ghost.org/faq/) 

## Domain Binding

When there is only one website on the server, you can visit the website without binding domain. While considering the server security and subsequent maintenance, the **Domain Binding** step cannot be omitted.

Taking one website as an example, steps for domain binding are as follows:

1. Ensure that domain name resolution has taken effect.
2. Use SFTP to connect your Cloud server, modify the domain name into yours in the [Nginx vhost configuration file](/stack-components.md#nginx). (This is the necessary step for using domain.)
   ```
    listen 80;
    server_name ghost.yourdomain.com;
   ```

3. Use SFTP to connect the server, modify the URL domain address into yours in [Ghost configuration file](/stack-components.md#ghost).
   ```
   {
   "url": "http://ghost.yourdomain.com",
   "server": {
      "port": 2368,
      "host": "0.0.0.0"
   },
   ```
4. Run the related commands. Above settings work after restarting the service.
   ```
   sudo systemctl restart nginx
   cd /data/wwwroot/ghost && sudo docker-compose up -d && sudo docker restart ghost
   ```

## Password Resetting

There are two main measures to reset password.

### Password Change

1. Log in the Ghost backend, open 【Manage】>【Staff】 and find the user account, of which you want to change password.
  ![Ghost Password Change](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-modifypw001-websoft9.png)

2. Start to change the password.
  ![Ghost Password Change](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-modifypw002-websoft9.png)

### Password Reminder

Try to retrieve your password through e-mail when forgetting it.

1. Complete [SMTP setting](/solution-smtp.md)

2. Open tha login page of Ghost, and click 【Forgot】to retrieve the password.
  ![Ghost Password Reminder](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-forgetpw-websoft9.png)
