# Update & Upgrade

Updates and upgrades are the tasks for system maintenance. Like buildings without maintenance for a long time, programs without upgrading will age faster, lose functionality until they are unavailable.

Get to know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
For example:
- Patching the operating system is **Updating**, while Ubuntu16.04 turns to Ubuntu18.04 means **Upgrading**
- MySQL5.6.25 to MySQL5.6.30 means **Updating**, while MySQL5.6 to MySQL5.7 means **Upgrading**

Ghost maintenance includes the following two tasks:

- System updating(Operating System and Running Environment) 
- Ghost upgrading

## System Updating

Run a command to complete the system updating:

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y --skip-broken
```
> This deployment package pre-configures a scheduled task for automatic updating. If you want to remove the automatic updating, please delete the corresponding Cron

## Ghost Upgrade

As Ghost official notes, to upgrade Ghost by upgrading node. Yet, this way does not apply when using Docker to install Ghost without deployment.

Hence, take the following steps to upgrade Ghost:

1. Make a [manual backup](/solution-backup.md#). Ensure the backup is successful.
2. Log in the Cloud Server and run the following commands.
   ```
   #Stop and delete the current Ghost container
   sudo docker stop ghost && sudo docker rm ghost

   #Delete the local Ghost image
   docker image rm ghost

   #Restart container
   cd /data/wwwroot/ghost && docker-compose up -d
   ```
3. Use local browser to visit Ghost and start upgrading.


