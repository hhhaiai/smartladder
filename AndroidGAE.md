Goagent For Android     ( 未ROOT也可使用 只限于浏览网页)

1：手机上安装GAE Proxy

2:运行GAE Proxy

3:配置Go Agent代理

按照本图设置 密钥可以不输入

![https://lh3.googleusercontent.com/-HnsEsxJV64E/UGqYG-0m21I/AAAAAAAAAL8/pgOhk3pa6vI/s595/6d9bd6a5jw1dxgw6ggosxj.jpg](https://lh3.googleusercontent.com/-HnsEsxJV64E/UGqYG-0m21I/AAAAAAAAAL8/pgOhk3pa6vI/s595/6d9bd6a5jw1dxgw6ggosxj.jpg)

![https://lh4.googleusercontent.com/-3IKR1jy57n4/UGqYGzB_9rI/AAAAAAAAAL8/ghM8_UDjiQk/s595/6d9bd6a5jw1dxgw183hdnj.jpg](https://lh4.googleusercontent.com/-3IKR1jy57n4/UGqYGzB_9rI/AAAAAAAAAL8/ghM8_UDjiQk/s595/6d9bd6a5jw1dxgw183hdnj.jpg)

4 导入 GAEProxy CA(证书) [安卓2.X证书下载](http://code.google.com/p/smartladder/downloads/detail?name=cacerts.bks&can=2&q=#makechanges)

[安卓4.0+证书下载](http://code.google.com/p/smartladder/downloads/detail?name=CA.crt&can=2&q=#makechanges)
到 Android 系统

通用步骤

请确认手机已 ROOT，对于 HTC 的机型，还需确认处于 s-off 状态

1. 备份 /system/etc/security/cacerts.bks 文件

2. 下载 已修改好的根证书 并放于当前目录下，之后在命令行中执行：

使用 Root Explorer（或者es文件浏览器） 从 SD 卡复制到 /system/etc/security/ 目录。覆盖原文件

3. 重启手机后生效

4.0 及以上系统

1. 下载 原始根证书 置于 SD 卡根目录

2. 进入设置->安全->从SD卡安装证书


5  爪机一阵狂抖 您的梯子就搭成功了

ENJOY

（GAE Proxy是自带浏览器的，每次上外网先运行GAE Proxy选链接，浏览器就可选了，打开浏览器就直接上外网）