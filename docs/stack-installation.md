# Initial Installation

If you have completed the Ghost deployment, just take the following steps to start a quick use.

## Preparation

1. Get the **Internet IP** on your Cloud Console.

2. Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:8161** is allowed.

3. Make a domain resolution on your Cloud Console if you want to use domain for Ghost.

## Ghost Installation Wizard

1. Use local Chrome or Firefox to access the URL *http://domain* or *http://Internet IP*.  
2. Enter the frontend.
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-bootpage-websoft9.png)

3. Access *http://domain/ghost* or *http://Internet IP/ghost* to enter the backend.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-register001-websoft9.png)

4. Create your account with the email address as username. Don't set a too simple password.  
   ![]( https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-register002-websoft9.png )

5. Use SFTP to connect your Cloud server, and modify the domain name into yours in the [Nginx vhost configuration file](/stack-components.md#nginx). (This is the necessary step for using domain.)
   ```
    listen 80;
    server_name ghost.yourdomain.com;
   ```

6. Use SFTP to connect the server. Modify the URL domain address into yours in [Ghost configuration file](/stack-components.md#ghost).
   ```
   {
   "url": "http://ghost.yourdomain.com",
   "server": {
      "port": 2368,
      "host": "0.0.0.0"
   },
   ```
7. Run the related commands. Above settings work after restarting the service.
   ```
   sudo systemctl restart nginx
   cd /data/wwwroot/ghost && sudo docker-compose up -d && sudo docker restart ghost
   ```
   
> More about how to use Ghost, please refer to official [Ghost Documentation](https://docs.ghost.org/docs).

## Q&A

#### I can't visit Ghost when connecting IP address in browser.

Your TCP:15672 of Security Group Rules is not allowed, so there is no response from Chrome or Firefox.

#### How to deploy ghost in this kind of deployment scheme?

Use docker to install ghost, and the database is stored in MySQL server.