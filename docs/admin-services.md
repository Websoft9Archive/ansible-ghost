# Start or Stop the Services

These commands you must know when you using the Ghost of Websoft9

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
sudo systemctl start redis
sudo systemctl stop redis
sudo systemctl restart redis
sudo systemctl status redis
```
