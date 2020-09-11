# 更新升级

网站技术日新月异，**更新升级**是维护工作之一，长时间不升级的程序，就如长时间不维护的建筑物一样，会加速老化、功能逐渐缺失直至无法使用。  

这里注意更新与升级这两词的差异（[延伸阅读](https://support.websoft9.com/docs/faq/zh/tech-upgrade.html#更新-vs-升级)），例如：
- 操作系统打个补丁常称之为**更新**，Ubuntu16.04 变更为 Ubuntu18.04，称之为**升级**
- MySQL5.6.25-->MySQL5.6.30 常称之为**更新**，MySQL5.6->MySQL5.7 称之为**升级**

Ghost 完整的更新升级包括：系统级更新（操作系统和运行环境）和 Ghost 程序升级两种类型

## 系统级更新

运行一条更新命令，即可完成系统级（包含Ghost小版本更新）更新：

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y --skip-broken
```
> 本部署包已预配置一个用于自动更新的计划任务。如果希望去掉自动更新，请删除对应的Cron


## Ghost升级

不部署采用 Docker 安装 Ghost，官方提供的通过 Node.js 升级 Ghost 不适用。

请按照下面的流程完成升级：

1. 手工[备份 Ghost](/zh/solution-backup.md#程序手工备份)，一定要确保万无一失
2. 登录云服务器，分别运行下面的命令
   ```
   #停止并删除现有的 Ghost 容器
   sudo docker stop ghost && sudo docker rm ghost

   #删除本地 Ghost 镜像
   docker image rm ghost

   #重新运行容器
   cd /data/wwwroot/ghost && docker-compose up -d
   ```
3. 本地浏览器重新访问 Ghost，开始升级
