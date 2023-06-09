# 什么是网站网址？

> 原文：<https://javascript.plainenglish.io/what-is-a-url-fc3581b87da1?source=collection_archive---------14----------------------->

## 解释网址示例方案及其强制组件

![](img/0126ea7ddc8315aef4947720975e91c8.png)

URL(统一资源定位符)是因特网上所需资源的所谓地址，由多个组件/部分组成。

让我们看看下面的网址

```
https://admin:pass@a.b.web.com:888/users/index.php?q=bob&role=2#info
```

该 URL 由以下部分组成:

1.  方案`https://`
2.  权威`admin:pass@`
3.  主持人`a.b.web.com`
4.  端口`888`
5.  路径`users/index.php`
6.  查询`q=bob&role=2`
7.  哈希`#info`

# 方案组件

备选命名:需要协议
:是
示例:`https://`

该方案指定 web 服务器将使用哪个应用程序(Windows/i0S/Android 上的应用程序)来打开 URL。

例如，使用方案`mailto://`打开一个 URL 将会打开您的 webmail 应用程序。

*   常见的例子:`https://`、`http://`、`ftp://`、`mailto://`、`file://`
*   自定义应用示例:`facetime://`、`slack://`、`steam://`
*   浏览器的具体例子:`about://`，`chrome://`
*   其他浏览器示例:`data://`、`javascript://`

# 权威成分

备选命名:HTTP 认证、凭证、授权
必需:否
示例:`admin:pass@`

对由`@` (at)符号指示的 web/app 资源的基本授权。
使用`:`(冒号)符号将登录`admin`与密码`pass`分开

在某些情况下，密码是可选的(例如`https://admin@example.com`)

# 主机组件

备选命名:需要主机名
:是
示例:`a.b.web.com`

主机由多个域名组成，用`.`(点)号分隔。
级别为> 2 的域名称为子域

1.  `a` -第四级域名(子域)
2.  `b` -三级域名(子域)
3.  `web` -二级域名(域名)
4.  `com` -顶级/一级域名(TLD)

主机可以是 IPv4(如`193.184.216.34` )
或 IPv6(如`[2a00:1450:400e:80a::200e]`)格式的 IP 地址

# 端口组件

必填:是
举例:`888`

端口组件表示我们指的是目标主机上的哪个服务器

`:`(冒号)符号表示端口组件的用法。`888`是端口号

服务器可以接受多个端口上的连接。例如，端口号`80`和`443`可由一台服务器使用:

*   `80` -端口号用于基本网络连接
*   `443` -端口号用于安全(TLS/SSL)网络连接

当网页有`https://`或`http://`方案时，省略端口`:443`或`:80`

# 道路连通区

要求:否
例如:`/users/index.php`

通常，路径组件表示服务器上目标文件的路径

*   `/` -根路径/文件夹。我们假设它叫做`htdocs`
*   `users`-`htdocs`文件夹内名为`users`的文件夹
*   `/index.php`-`users`文件夹内名为`index.php`的文件

在某些情况下，路径组件可以使用自定义映射/方案/重写规则。路径段可以链接到服务器上不同文件中的函数/方法:

*   `/users/list`-`users.php`文件中的功能`list`。
    *显示所有用户列表*
*   `/users/1/read` -在`users.php`文件中带有参数`ID`的函数`read`。
    *显示 ID = 1 的用户信息*
*   `/users/images`-`image-collection.php`文件中的功能`users`。
    *显示所有用户的图像*

# 查询组件

备选命名:查询字符串、搜索字符串、参数
必需:无
示例:`?q=bob&role=2`

查询组件总是以一个`?`(问题)符号开始。它由键值对组成。使用`=`(等于)符号将该值分配给一个键。
键值对使用`&`(与号)符号分隔。

1.  `?` -表示查询组件存在的开始符号
2.  `q`——第一把钥匙
3.  `=` -将第一个值分配给第一个键的符号
4.  `bob` -第一个值
5.  `&` -键和值对分隔符
6.  `role` -第二把钥匙
7.  `=` -将第二个值分配给第二个键的符号
8.  `2` -第二个值

该查询背后的逻辑示例:*获取所有名为* `*bob*` *且角色 ID 为* `*2*`的用户

# 哈希组件

备选命名:需要锚
:不需要
例如:`#info`

通常由客户端脚本语言使用，默认命名为`Javascript`
——浏览器将聚焦一个在`#`(哈希)符号后带有`id`的元素。
在我们的例子中，焦点将放在 ID 为`info`的元素上

*   `#` -表示哈希组件存在的起始符号
*   `info` -哈希组件的值

该散列背后的逻辑示例:*显示找到的用户的基本信息标签*

> 感谢阅读👍
> 
> 在推特上关注我—[twitter.com/therceman](http://twitter.com/therceman)

*更多内容请看*[***plain English . io***](http://plainenglish.io/)