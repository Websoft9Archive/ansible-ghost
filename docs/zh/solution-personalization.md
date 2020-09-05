# 个性化

## 菜单

Ghost 可以很方便的定义菜单栏：

1. 登录 Ghost，点击左侧菜单栏的【SETTING】>【Design】
  ![Ghost 代码插入](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setmenus-websoft9.png)

2. 设置所需的网址，点击【Save】保存后即可生效。

## 主题

Ghost 的主题是网站页面的主要个性化入口。系统默认提供了一个主题，同时也支持用户自己上传主题，实现界面个性化

1. 登录 Ghost，点击左侧菜单栏的【SETTING】>【Design】，下拉到主题设置区域

2. 先点击【Theme Marketplace】找到一款自己喜欢的主题，并下载主题的压缩文件（一般以.zip结尾）
  ![Ghost 设置主题](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setthemes-websoft9.png)

3. 再点击【Upload a theme】上传主题文件，并【Active】它后生效

上传的主题会保存到服务器：*/data/wwwroot/ghost/content/themes* 目录下，用户可以修改其中的文件，实现主题在代码层面的个性化定制与开发。

## 多语言

Ghost 的后台不支持中文，但是前台支持中文（需主题中有中文）。

1. 使用 SSH 或 SFTP 工具登录服务，进入到你的主题下 locales 目录

2. 正常情况下，你会看到很多 json 文件，这些就是主题的翻译文件

3. 查看 zh-hans.json 文件，你会看到中文简体的翻译，即此文件代表简体中文

4. 登录到 Ghost 后台，点击左侧菜单栏的【General】，展开【Publication Language】，设置其值为：zh-hans
  ![Ghost 设置语言](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setzhhans-websoft9.png)

5. 保存后即刻生效

## 代码嵌入

代码嵌入可以帮助你的 Ghost 网站插入第三方 JavaScript 代码，例如：百度统计、Google Analysis 等。这些代码一旦插入之后，就会针对每一个页面生效。

1. 登录 Ghost，点击左侧菜单栏的【SETTING】>【Code Injection】
  ![Ghost 代码插入](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-codeinjection-websoft9.png)

2. 将所需的代码拷贝到此处后，点击【Save】保存后即可生效。

## 订阅

Ghost 支持网站向客户以订阅的方式售卖文章，是知识付费创业者的生产力工具。

1. 登录 Ghost，点击左侧菜单栏的【SETTING】>【Labs 】

2. 分别对 Enable members, Connect to Stripe, Subscription pricing 等项进行设置
  ![Ghost 代码插入](https://libs.websoft9.com/Websoft9/DocsPicture/en/ghost/ghost-setsubs-websoft9.png)