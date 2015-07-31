#使用说明
下载程序  链接: http://pan.baidu.com/s/1i37jR9N 密码: 3hr7  按照自己的系统下载

1：运行程序

> Windows:打开根目录下的shadowsocks.exe


按要求修改我给你的服务器配置 编辑config.json


> "server":"127.0.0.1",   这里填写服务器的ip或者地址

> "server\_port":8080,   这里填写服务器端口

> "local\_address":"127.0.0.1",本地localhost地址一般不用改

> "local\_port":1080,     这里填写本地端口

> "password":"barfoo!",    这里填写密码

> "timeout":600,

> "method":"aes-256-cfb"     这里是加密方式


Mac OS X/Linux用户建议使用python（2.7）版的

如果想使用 table 之外的加密方法，要先安装 M2Crypto.

Ubuntu:

apt-get install python-m2crypto
Debian:

apt-get install libssl-dev swig
pip install M2Crypto
openSUSE:

zypper in python-m2crypto
其它系统:

apt-get install openssl-dev swig
pip install M2Crypto
注意，在有些系统上其中一些加密方法可能不可用。

按照以上配置填写后
执行python local.py即可



2:设置浏览器

设置浏览器代理,这一步就和使用SSH代理一样,FireFox下设置!Foxyproxy,!Chrome下设置Proxy

SwitchySharp扩展就可以了,设置代理为127.0.0.1:本地端口,默认的是127.0.0.1:1080,代理类型为socks5代理,这个一定不能弄错!




添加完毕之后记得设置它为默认代理。

Chrome---Proxy SwitchySharp  [Chrome商店安装](https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm?hl=zh-CN)  [安装方法](http://lovejiani.com/crx/#install)  [.bak备份地址](http://ippotsuko.com/so.bak)

设置如下:

进入扩展选项  导入/导出  从文件恢复 打开Proxy SwitchySharp压缩包内解压过的
.bak文件即可

![https://lh4.googleusercontent.com/-zGLJ6u1Sp5Q/UfefsFxsejI/AAAAAAAAAIc/z7jM-Yu8HRI/w928-h507-no/QQ%25E6%2588%25AA%25E5%259B%25BE20130730191226.png](https://lh4.googleusercontent.com/-zGLJ6u1Sp5Q/UfefsFxsejI/AAAAAAAAAIc/z7jM-Yu8HRI/w928-h507-no/QQ%25E6%2588%25AA%25E5%259B%25BE20130730191226.png)

![https://lh6.googleusercontent.com/-F9tKjViW3Sg/UfefsB1MAUI/AAAAAAAAAIY/njLkM2pNmAY/w904-h642-no/QQ%25E6%2588%25AA%25E5%259B%25BE20130730191211.png](https://lh6.googleusercontent.com/-F9tKjViW3Sg/UfefsB1MAUI/AAAAAAAAAIY/njLkM2pNmAY/w904-h642-no/QQ%25E6%2588%25AA%25E5%259B%25BE20130730191211.png)



Firefox---FoxyProxy [Firefox商店地址](https://addons.mozilla.org/zh-cn/firefox/addon/foxyproxy-standard/)
上面两个被walled 可以点右边的[度娘盘](http://pan.baidu.com/s/1c0pHjqw) 下载完成后 拖拽至浏览器 按提示安装即可

设置参考 http://ippotsuko.com/blog/foxyproxy-basic-setting/
shadowsocks把本地代理socks5   127.0.0.1:1080即可


---

Android  iOS 用户下载app   http://pan.baidu.com/s/1gd9l4T9 密码: rbm9  按照自己的系统下载
填写需要的信息即可

一切正常的话你就又在墙外了,enjoy it!

购买本服务不会使用可以gmail求助我 我会给你扣扣远程