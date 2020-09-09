# Initial Installation

If you have completed the Ghost deployment on Cloud Platform, just take the following steps to start use it quickly.

## Preparation

1. Get the **Internet IP** on your Cloud console.
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:8161 is allowed.
3. Make a domain resolution on your DNS Console if you want to use domain for Ghost

## Ghost Installation Wizard

1. Use local Chrome or Firefox to visit the URL *http://domain* or *http://Internet IP* and enter the front page.
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-bootpage-websoft9.png)

2.  Visit：*http://domain/ghost* 或 *http://Internet IP/ghost* to enter the backend.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-register001-websoft9.png)

3. Start to create an administrator account with the email address as the UserName. Do not set a excessively simple password.
   ![]( https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-register002-websoft9.png )

4. Use SFTP to connect your Cloud server, modify the domain name into yours in the [Nginx vhost configuration file](/stack-components.md#nginx). (This is the necessary step for using domain.)
   ```
    listen 80;
    server_name ghost.yourdomain.com;
   ```

5. Use SFTP to connect the server, modify the URL domain address into yours in [Ghost configuration file](/stack-components.md#ghost).
   ```
   {
   "url": "http://ghost.yourdomain.com",
   "server": {
      "port": 2368,
      "host": "0.0.0.0"
   },
   ```
6. Run the related commands. Above settings work after restarting the service.
   ```
   sudo systemctl restart nginx
   cd /data/wwwroot/ghost && sudo docker-compose up -d && sudo docker restart ghost
   ```
   
> More about how to use Ghost, please refer to official [Ghost Documentation](https://docs.ghost.org/docs)

## Q&A

#### I can't visit Ghost when connecting IP address in browser.

Your TCP:15672 of Security Group Rules is not allowed, so there no response from Chrome or Firefox

#### How to deploy ghost in this kind of deployment scheme?

Use docker to install ghost, and the database is stored in MySQL server.