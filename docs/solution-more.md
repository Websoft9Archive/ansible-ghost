# More

Each of the following solutions has been proved to be effective and we hope it can give you help.

## Configuration 

Ghost official offers many configurations. Please refer to [Tutorials](https://ghost.org/tutorials/) and [FAQ](https://ghost.org/faq/).

## Binding Domain

When there is only one website on the server, you can access the website without binding domain. While considering the server security and subsequent maintenance, it would better to **Bind Domain**.

Taking one website as an example, steps for binding domain are as follows:

1. ensure that domain name resolution has taken effect;
2. use SFTP to connect your Cloud server, modify the domain name into yours in the [Nginx vhost configuration file](/stack-components.md#nginx); (This is the necessary step for using domain.)
   ```
    listen 80;
    server_name ghost.yourdomain.com;
   ```

3. use SFTP to connect the server, modify the URL domain into yours in [Ghost configuration file](/stack-components.md#ghost);
   ```
   {
   "url": "http://ghost.yourdomain.com",
   "server": {
      "port": 2368,
      "host": "0.0.0.0"
   },
   ```
4. run the related commands. Above settings work after restarting the service.
   ```
   sudo systemctl restart nginx
   cd /data/wwwroot/ghost && sudo docker-compose up -d && sudo docker restart ghost
   ```

## Resetting Password

There are two main measures to reset password.

### Changing password

Take the steps below:

1. log in the Ghost backend, open 【Manage】>【Staff】 and find the user account, of which you want to change password;
  ![Ghost Password Change](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-modifypw001-websoft9.png)

2. start to change the password.
  ![Ghost Password Change](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-modifypw002-websoft9.png)

### Forgot Password

Try to retrieve your password through e-mail when forgot it.

Follow the steps below:

1. complete [SMTP setting](/solution-smtp.md);

2. open tha login page of Ghost, and click 【Forgot】to retrieve the password.
  ![Ghost Password Reminder](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-forgetpw-websoft9.png)
