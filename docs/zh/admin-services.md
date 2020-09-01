# 服务启停

使用由Websoft9提供的 Ghost 部署方案，可能需要用到的服务如下：

### Ghost

```shell
sudo systemctl start ghost-server
sudo systemctl stop ghost-server
sudo systemctl restart ghost-server
sudo systemctl status ghost-server

# you can use this debug mode if Ghost service can't run
ghost-server console
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### Redis

```shell
systemctl start redis
systemctl stop redis
systemctl restart redis
systemctl status redis
```
