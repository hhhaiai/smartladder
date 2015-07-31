## 常见问题 FAQ ##
警告：**请勿到本页提交新问题，要提问请去[issues](https://code.google.com/p/goagent/issues/list)**
  1. goagent是什么？
    * goagent是使用Python编写的网络软件，可以运行在Windows/Mac/Linux/[Android](http://code.google.com/p/gaeproxy)/[iTouch/iPhone/iPad](https://code.google.com/p/goagent/wiki/GoAgent_IOS)/[webOS](https://code.google.com/p/goagent/wiki/GoAgent_webOS)/[OpenWRT](https://code.google.com/p/goagent/wiki/GoAgent_OpenWRT)/[Maemo](https://code.google.com/p/goagent/wiki/GoAgent_Maemo)上。
  1. <font color='red'>是否每次更新都要重新上传？</font>
    * <font color='red'>更新历史中带有[是]则需要重新上传，否则不用重新上传。注意：是否需要重新上传是相对于前一版的，若你之前版本与当前版本之间某一版或多版带有[是]仍然需要重新上传。</font>
  1. 遇到FAQ没有解决问题怎么办?
    * 首先请更新客户端和服务端到最新版(见首页)，如果还有问题的话请到https://code.google.com/p/goagent/issues/list 提出issue。提issue前建议先搜索下看是否是重复的问题，请尽量描述问题产生的原因，配置情况，网络情况等，这样有助于重现问题并解决。虽然我们可能顾不上回答，但是我们保证每个issue都会看的并尝试解决的。
  1. 用goagent访问twitter,自动跳转为mobile.twitter并返回403 Forbidden。
    * 检查查自己的id是不是以android开头或者apple,iphone啥的开头的了，参见 [Issue 7634](https://code.google.com/p/smartladder/issues/detail?id=7634)
  1. google reader提示404错误？
    * 使用[https://www.google.com/reader ]访问.
  1. 在 Linux/Mac 下如何安装 gevent?
    * [Ubuntu系统下安装gevent及pyopenssl](https://code.google.com/p/goagent/wiki/InstallGeventAndPyopensslOnUbuntu)
    * 在shell命令执行如下语句(注意需要安装 gcc 或 xcode): `curl -k -L http://git.io/A8j55Q|sh`
  1. youtube不能上传以及看直播？
    * 请看[issue 2668](https://code.google.com/p/goagent/issues/detail?id=2868).
  1. 提示Error code 502错误怎么办？
    * 401: Unauthorized 一般是你处于内网环境中，需要设置proxy.ini里面的proxy段落
    * 404: Not Found 一般是proxy.ini里面appid没有填对，或者服务端没有部署成功。
    * 503: Service Unavailable 一般是流量用完了，请更换appid
  1. uploader上传失败？
    * 400: --- begin server output --- 到https://appengine.google.com删除旧的，新建一个新的appid再上传。
    * 404: Not Found 对应的appid没有创建或者appid与Gmail账户不对应。
    * 10060 连接服务器超时，建议挂VPN后再上传
    * 10054 连接被重置，建议挂VPN后再上传
    * 10061 目标计算机积极拒绝 挂VPN或者运行goagent后把IE代理设置为127.0.0.1：8087
  1. 听说goagent保密性比较弱，如何加强？
    * 下载最新版的客户端，编辑proxy.ini的[google\_cn](google_cn.md) [google\_hk](google_hk.md)域，mode=https即可.速度也相应变慢，呵呵。
  1. 最新版在哪下载？如何在旧版本上更新新版本？
    * 还是直接到首页下载，那个链接永远是最新版。旧版本不用管，直接编辑新版的proxy.ini里面的appid即可。
  1. 我是Mac/Linux用户怎么办？
    * 上传完服务端并设置好proxy.ini之后，在终端直接运行python proxy.py即可。需要Python版本2.6以上。Mac用户可以尝试 [GoAgent Mac GUI](https://goagent.googlecode.com/files/GoAgentMac.dmg) 或者[GoAgentX](https://github.com/ohdarling/GoAgentX)
  1. Linux/Mac如何上传服务端？
    * 在server目录下运行"python uploader.zip"(没有引号)，如果要上传python服务端的话，在server目录下运行"uploaddir=python python uploader.zip"(没有引号) 或者尝试[GoAgentX](https://github.com/ohdarling/GoAgentX)
  1. 支持多个appid做负载平衡吗？
    * 目前goagent最新版是支持的，在proxy.ini中的`[gae]`项目下这样配置即可appid=id1|id2|id3
  1. 配置多appid有什么用？
    * 最新版的GAE服务端已经是python27，所以多appid现在只是起到增加流量配额的作用。提高并发的作用已经被GAE内置的功能取代了。
  1. GAE在2011-09-01推出了新版的收费计划，如何规避？
    * 使用goagent 1.6以上版本的服务端。
  1. 如何使用php模式？
    1. 申请一个免费的php空间，然后通过在线代码编辑器或者ftp客户端把index.php上传到你申请到php网站的根目录。假设为http://goagent.php.com/index.php
    1. 访问你的index.php地址，比如http://goagent.php.com/fetch.php，如果没有问题的话，说明部署成功。
    1. 编辑proxy.ini`[paas]`项目, enable=1和fetchserver=你的index.php地址，重启goagent.exe即可。
    1. 图文教程请见http://ishare.cn.ms/archives/552
  1. 如何设为系统服务（开机自启动）？
    * 双击addto-startup.vbs即可。
  1. goagent支持IPv6网络吗？
    * 支持的。profile=google\_ipv6即可。
  1. 为什么goagent第一次运行需要管理员权限？
    * 因为goagent会尝试调用certmgr.exe向系统导入IE/Chrome的证书，这需要管理员权限。
  1. Firefox怎么不能登陆twitter/facebook等网站, Firefox如何导入证书?
    * 打开FireFox->选项->高级->加密->查看证书->证书机构->导入证书, 选择local\ca.crt, 勾选所有项，导入。
  1. Chrome下如何使用goagent?
    * Chrome可以安装switchysharp插件，然后导入这个设置https://goagent.googlecode.com/files/SwitchyOptions.bak.
  1. 需要装Python或者Google Appenginge SDK后才能用goagent吗？
    * 完全不用，goagent是绿色软件哦。
  1. goagent原理是什么？
    * goagent是GAE应用，原理可以参考这个图![http://cms4g-proxy.googlecode.com/svn/wiki/res/%E4%BB%A3%E7%90%86%E7%A4%BA%E6%84%8F%E5%9B%BE.png](http://cms4g-proxy.googlecode.com/svn/wiki/res/%E4%BB%A3%E7%90%86%E7%A4%BA%E6%84%8F%E5%9B%BE.png)
  1. 支持gfwlist么？
    * 这个问题考虑过，但是还是放弃了。goagent需要保持简单快速，支持gfwlist请使用autoproxy/switchysharp。
  1. 如何防止goagent被匿名使用(盗用)？
    * 目前goagent最新版是支持的，注意:本功能不会影响网速，请放心使用。
      * golang版本(目前暂时没有该版本可用)：server\golang\fetch.go中const段落开头修改`Password = "123456"`，重新上传fetch.go,然后在proxy.ini中的[gae](gae.md)项目下这样配置即可password = 123456，即可。
      * python版本：先在server\python\wsgi.py和wsgi\_old.py文件中开头修改`__password__ = '123456'`，重新上传wsgi.py,然后在proxy.ini中的[gae](gae.md)项目下这样配置即可password = 123456，即可。
  1. 怎样设置不显示气泡提示？
    * 用reshack/exescope等资源编辑工具把气泡提示字符串清空即可。
  1. 如何删除appengine.google.com上老的appid？
    * 可以的，请看[issue 1501](https://code.google.com/p/goagent/issues/detail?id=1501)
  1. 如何得到goagent的源代码？
    * goagent的代码和程序是一起的，源代码就是运行程序。
  1. MultiplexConnection Cannot hosts错误？
    * 看起来你的ISP封锁了google.cn，请尝试profile=google\_hk这个选项，如果还不行，换PHP模式吧。
  1. 如何对goagent进行修改？
    * 客户端代码直接改local/proxy.py,改完重启goagent.exe即可；服务端改server/wsgi.py,改完用uploader.bat上传即可。
  1. 为什么要叫goagent，而不叫GoProxy？
    * 一开始叫GoProxy的，后来Hewig说软件名字带有proxy字样不祥，于是就改成了goagent。
  1. 使用goagent时其他网站能打开，唯独谷歌打不开？
    * goagent对大部分谷歌网站默认采取直接连接，将sites = 之后的URL地址清空即可
  1. 上传出现：'ascii' codec can't decode byte 0xca in position
    * 这是一般是因为在你windows注册表这个路径下有非ASCII的key：HKEY\_CLASSES\_ROOT\MIME\Database\Content Type， 你把非ASCII的KEY都删掉之后试试。
    * 解决方法：
      1. 在键盘上使用快捷键“win + R”打开运行对话框。
      1. 输入regedit再回车。
      1. 进入HKEY\_CLASSES\_ROOT\MIME\Database\Content Type 。
      1. 把非ASCII的KEY(即带中文的)都删掉。
      1. 再重新上传
  1. 上传遇到<urlopen error [11004](Errno.md) getaddrinfo failed>？
    * 这一般是因为你使用的IPv6的hosts或者你系统默认将appengine.google.com解析到了IPv6地址，可以暂时删除IPv6 hosts或者按照[7856#c3](https://code.google.com/p/goagent/issues/detail?id=7856#c3)修改uploader.zip，也可以下载这个[已经修改好的](https://code.google.com/p/goagent/downloads/detail?name=uploader.zip&can=2&q=)进行替换
    * 如果不是因为IPv6,检查系统hosts文件是否有错误，ping www.google.com看是否能ping通，可以将正确的谷歌IP地址加入hosts文件，也可以先修改proxy.ini里的appid后运行goagent，系统把代理设置为127.0.0.1：8087之后再上传
  1. talk.google.com 错误解决方法
    * GAE 只能作为 http (以及伪 https) 代理使用, Chrome 在启动时会用 https 代理去连接 talk.google.com:5222, 但所用的并非是 https 协议的, 走不了 "GAE 代理", 可以通过pac或者浏览器扩展中的代理选择功能让这个请求不走 GAE 从而避免出现错误.
  1. Windows 系统下，出现 ioerror:cannot watch more than 1024 sockets
    * 下载新版（>=2.1.15），并使用uvent.bat启动。
  1. 为什么使用goagent后访问google.com仍然跳转到google.com.hk?
    * 默认直接连接google.com。清空sites = 后面的内容即可(参见[ini参数解释](https://code.google.com/p/goagent/wiki/ConfigIntroduce))，以可以访问https://www.google.com/ncr
  1. Linux/Mac下删除ca.crt和ca.key后不能自动生成证书，导致浏览器出现ssl错误  [Issue 2593](https://code.google.com/p/smartladder/issues/detail?id=2593)
    * 安装PyOpenssl即可解决，[安装方法](https://code.google.com/p/goagent/wiki/GoAgent_Linux)
  1. 上传出现AttributeError: can't set attribute？或者看到下图错误
> > ![http://ww3.sinaimg.cn/large/786e2887tw1e4mjyueppqj20ix0c841v.jpg](http://ww3.sinaimg.cn/large/786e2887tw1e4mjyueppqj20ix0c841v.jpg)
> > ![http://ww4.sinaimg.cn/large/786e2887tw1e4esk116m0j20e300xwed.jpg](http://ww4.sinaimg.cn/large/786e2887tw1e4esk116m0j20e300xwed.jpg)
    * 密码错误，使用正确的邮箱密码或应用程序专用密码来上传，如果你开启了两步验证，那么密码就是两步验证的密码，或者到http://www.google.com/settings/security 取消两步验证之后再用邮箱的密码上传，如果还不行检查看看是否开启了ie或者其他浏览器的代理（全局代理），取消掉代理。获取应用程序专用密码方法（对于开启了两步验证的), 到https://accounts.google.com/b/0/IssuedAuthSubTokens 获取密码，当上传时询问密码就用这个密码。两步验证就是谷歌推出的进阶安全机制，给应用生成专属密码来访问你的账户，避免主密码被盗。
> > > ![http://ww2.sinaimg.cn/large/786e2887jw1e4eshzdsryj20i00akdgg.jpg](http://ww2.sinaimg.cn/large/786e2887jw1e4eshzdsryj20i00akdgg.jpg)
  1. GoAgent没有日志输出，浏览器提示服务器响应时间过长，或者是socket.gaierror: [10104](Errno.md) getaddrinfo failed
    * 确认浏览器代理设置没有问题，浏览器代理切换插件工作正常（Proxy SwitchySharp有时需要卸载重装才能正常）。
    * 重置winsock试试
      * 启动cmd 　　输入 netsh winsock reset 回车 　　然后重启电脑
  1. socket.error: [10048](Errno.md) 通常每个套接字地址(协议/网络地址/端口): ('127.0.0.1', 8087)?端口也可能为8086

> > ![http://ww2.sinaimg.cn/large/786e2887tw1e4ersbm99uj20it0cc41i.jpg](http://ww2.sinaimg.cn/large/786e2887tw1e4ersbm99uj20it0cc41i.jpg)
    * 原因：可能是goagent已经在运行或者被其他软件占用，比如搜狗浏览器开启全网加速会使用8087端口，比如旧版goagent加入开机启动没有删除、旧版已经在运行。
      * 解决办法：关闭旧版goagent或者其他占用该端口的软件再重启goagent即可。
  1. 出现
```
Error 

Over Quota
This application is temporarily over its serving quota. Please try again later.
```
    * 流量用完了，请更换appid

---

**请勿到本页提交新问题，要提问请去[issues](https://code.google.com/p/goagent/issues/list)**