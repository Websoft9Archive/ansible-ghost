# Personalization

## Menu

It's convenient to design menu in Ghost. Just take the following steps:

1. Login in Ghost, and click【SETTING】>【Design】in the left of menu.
  ![Ghost Menu Setting](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setmenus-websoft9.png)

2. Design as you like and click【Save】.

## Theme

Theme is the main tool to personalize the interface. There is a default theme. You can also upload themes by taking the following steps:

1. Login in Ghost, click【SETTING】>【Design】 and then pull down the page to find the theme setting.

2. Click【Theme Marketplace】, find the theme you want and download the compressed file for the theme, such as a zip file.
  ![Ghost Theme Setting](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setthemes-websoft9.png)

3. Click【Upload a theme】and【Active】
  Theme uploaded is stored in the directory */data/wwwroot/ghost/content/themes* on the server. You can modify the file included to make theme personalization at code level.

## Languages

Default language is English and you can add translation files to your theme for any language.
Take the following steps:

1. Use SSH or SFTP to login in, and find the directory, locales in themes folder.

2. View json files to find your translation files.
![Ghost language setting](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-listalllanguages-websoft9.png)

3. Log in the Ghost backend, click 【General】 and add the name of the translation file to 【Publication Language】
![Ghost Language Setting](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setzhhans-websoft9.png)

## Code Injection

Use code injection to insert third-party JavaScript code to Ghost website, such as Google analysis, etc.  
Once inserted, the code works on each page.

1. Login in Ghost and click【SETTING】>【Code Injection】in the left menu.
![Ghost Code Injection](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-codeinjection-websoft9.png)

2. Copy the code needed and click 【Save】.

## Subscription

Ghost supports selling articles by subscription, which encourages entrepreneurs who offer knowledge as business.

1. Login in Ghost and click【SETTING】>【Labs 】in the left menu.

2. Set Enable members, Connect to Stripe, Subscription pricing and more.
  ![Ghost Subscription](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setsubs-websoft9.png)  