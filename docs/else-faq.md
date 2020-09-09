# FAQ

#### What's the difference between Post and Page in the Ghost system?

Post means the article. A blog is a post. While the meaning of page differs. The home page, introduction about the company on the website can be called page.

In the ghost system, every new page needs to have a corresponding template file in the theme to match it.

#### Does Ghost enable me to modify the default theme Casper?

No, you're only able to modify the self-uploaded theme.

#### Can I reset password of Ghost by command?

No.

#### If there is no domain name, can I deploy Ghost?

Yes, visit Ghost by *http://Internet IP:8161*

#### How to set up domain access？

First resolve the domain, then connect your Cloud Server to [bind the domain](/solution-more.md)

#### What is the password for the database root user?

Find the password stored in the server related file: `/credentials/password.txt`

#### Is there a web-base GUI database management tool?

Yes, phpMyAdmin is included. Visit by *http://Internet IP:9090*

#### How to ban outside access to phpMyAdmin?

 Close TCP:9090 port on Inbound of Security Group Rule.

 #### Can I change the directory of Ghost?

 Yes. Modify the persistence directory of the marshal file in Ghost container: */data/wwwroot/ghost/docker-compose.yml*

#### How to change the permissions of filesystem?

Change owner(group) or permissions as below:

```shell
chown -R apache.apache /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a series of software to the server in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared on the server.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference. All refer to cloud servers. They are the different terminology used by different manufacturers.
