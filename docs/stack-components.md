# Parameters

The Ghost deployment package contains a sequence of software (referred to as "components") required for Ghost to run. Below list the important information, such as the component name, installation directory path, configuration file path, port, version and etc.

## Path

### Ghost

Ghost installation directory: */data/wwwroot/ghost/content*  
Ghost configuration file: */data/wwwroot/ghost/config.production.json*  
Ghost Docker compose file: */data/wwwroot/ghost/docker-compose.yml*

### Nginx

Nginx vhost configuration file: */etc/nginx/conf.d/default.conf*    
Nginx main configuration file: */etc/nginx/nginx.conf*   
Nginx logs file: */var/log/nginx*  
Nginx rewrite rules directory: */etc/nginx/conf.d/rewrite* 

### MYSQL

MySQL installation directory: */usr/local/mysql*  
MySQL data directory: */data/mysql*  
MySQL configuration file: */etc/my.cnf*    

### phpMyAdmin

PhpMyAdmin is run in container, and the environment and ghost container is separated, which is stable and reliable.

Visit *http://Internet IP:9090*

### Docker

Docker root directory: */var/lib/docker*  
Docker image directory: */var/lib/docker/image*   
Docker daemon.json file: It is not created by default. If need it, create it in the directory */etc/docker* 


## Ports

Open or close ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** of your Cloud Server to decide whether the port can be accessed from Internet. You can run the cmd `netstat -tunlp` to check all related ports.  
The following are the ports you may use.

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| HTTP | 80 | Use HTTP to visit Ghost | Optional |
| HTTP | 443 | Use HTTP to visit Ghost | Optional |
| TCP | 9090 | web-base GUI database management tool, phpMyAdmin | Optional |
| TCP | 3306 | local database client to access database | Optional |


## Version

You can see the version on product pages at Marketplace. However, after being deployed to your server, the components will be updated automatically, resulting in a certain change in the version number. Therefore, run the command on the server to view the exact version numbers.

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Nginx  Version
nginx -V

# Node version
node -v

# Docker Version
docker -v

# MySQL  Version
mysql -V

# Node  Version
sudo docker exec -it ghost /bin/bash -c 'node -v'

# Ghost version
sudo docker exec -it ghost /bin/bash -c 'ls versions'
```
