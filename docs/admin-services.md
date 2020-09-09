# Start or Stop the Services

These commands are required when you use the Ghost of Websoft9. 

### Ghost

```shell
sudo docker stop ghost
sudo docker start ghost
sudo docker restart ghost

# you can use the following CMD to manage Ghost container
sudo docker exec -it ghost /bin/bash
```

### Nginx

```shell
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### phpMyAdmin

```shell
sudo docker stop phpmyadmin
sudo docker start phpmyadmin
sudo docker restart phpmyadmin
```