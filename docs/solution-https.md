# SSL/HTTPS

Before setting, you have to complete [binding domain](/solution-more.md) and make sure you can access Ghost by HTTP.

Ghost deployment package includes the pre-installed and pre-configured SSL module of Web server and open Certificate Authority **[Let's Encrypt](https://letsencrypt.org/)**. Hence, except for the vhost configuration file, it doesn't need modifications to any other files in Nginx when setting HTTPS.

## Quick Start

### Automatic Deployment

If you want to use a free certificate, just run the one command `sudo certbot` on your instance to start automatic request to certificate and HTTPS deployment.

```
sudo certbot
```

### Manual deployment

If you have applied for a certificate, complete the HTTPS configuration in just three steps:

1. upload your certificate, and file of certificate chain, and secret key to the directory: */data/cert*;

2. open the vhost configuration file: */etc/nginx/conf.d/default.conf* 

3. insert the **HTTPS template** into *server{  }*.
   ``` text
   #-----HTTPS template start------------
   listen 443 ssl; 
   ssl_certificate /data/cert/xxx.crt;
   ssl_certificate_key /data/cert/xxx.key;
   ssl_trusted_certificate /data/cert/chain.pem;
   ssl_session_timeout 5m;
   ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
   ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:HIGH:!aNULL:!MD5:!RC4:!DHE;
   ssl_prefer_server_ciphers on;
   #-----HTTPS template end------------
   ```
4. [restart Nginx service](/admin-services.md).

## Special Guide

If failed to set HTTPS by taking the above steps, view the [HTTPS Special Guide](https://support.websoft9.com/docs/faq/tech-https.html#nginx) provided by Websoft9. 

The special guide includes solutions about configuring HTTPS pre-conditions, HTTPS configuration segment templates, precautions, detailed steps, troubleshooting and so on.
