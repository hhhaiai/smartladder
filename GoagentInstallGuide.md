# goagent GAE平台部署教程 #

## 一、申请Google App Engine并创建appid ##
  1. 申请注册一个Google App Engine账号[https://appengine.google.com](https://appengine.google.com)。没有Gmail账号先注册一个， 用你的Gmaill账号登录。![http://ww3.sinaimg.cn/large/786e2887tw1e4thu7y0pgj20hs0atgn9.jpg](http://ww3.sinaimg.cn/large/786e2887tw1e4thu7y0pgj20hs0atgn9.jpg)
  1. 登录之后，自动转向Application注册页面，如下图：![http://ww1.sinaimg.cn/large/786e2887tw1e4thu8o1tuj20hs067mxn.jpg](http://ww1.sinaimg.cn/large/786e2887tw1e4thu8o1tuj20hs067mxn.jpg)
  1. 接下来的页面，输入你的手机号码，需要注意的是，手机号码前面要+86 格式如：+86 13888888888。![http://ww2.sinaimg.cn/large/786e2887tw1e4thubjc3yj20hs07dmxw.jpg](http://ww2.sinaimg.cn/large/786e2887tw1e4thubjc3yj20hs07dmxw.jpg)
    * 然后等待收取手机短信，收到短信后（一串数字号码）填入下图表单，点send提交.（有的手机收不到信息，解决办法：[详细教程](http://ishare.cn.ms/archives/2162) 到[https://appengine.google.com/waitlist/sms\_issues](https://appengine.google.com/waitlist/sms_issues) 提交该情况，一个工作日就能收到谷歌提示Google App Engine成功开通）。![http://ww1.sinaimg.cn/large/786e2887tw1e4thucmsi5j20hc0743z5.jpg](http://ww1.sinaimg.cn/large/786e2887tw1e4thucmsi5j20hc0743z5.jpg)
  1. 提交完成之后，GAE账号即被激活，然后就可以创建新的应用程序了。转入“My Applications”页面，点击“Create an Application”新建应用![http://ww3.sinaimg.cn/large/786e2887tw1e4thug3zu2j20hs07tzku.jpg](http://ww3.sinaimg.cn/large/786e2887tw1e4thug3zu2j20hs07tzku.jpg)
    * 一个Gmail账户最多可以创建十个GAE应用。这里我们只创建一个应用就可以了。进入下一步，填写新应用的必要信息，如下图：![http://ww2.sinaimg.cn/large/786e2887tw1e2s3t7k4v9j.jpg?craete-app.png](http://ww2.sinaimg.cn/large/786e2887tw1e2s3t7k4v9j.jpg?craete-app.png)
    * 在上图中第一处添加一个应用名称，如abc555,验证一下是否可用，如果显示“Yes”那么abc555就是你的Appid（记住这个id），而abc555.appspot.com就是你的应用服务器地址了。第二个空可随便填，点击提交按钮，如果能看到下图这个页面，就说明你成功创建了一个新的应用,你也可以点击应用名称，进入控制面板进行管理。   ![http://ww4.sinaimg.cn/large/786e2887tw1e4thubz37cj20go049t8w.jpg](http://ww4.sinaimg.cn/large/786e2887tw1e4thubz37cj20go049t8w.jpg)
    * 如果你要建立多次appid，只需要从步骤4开始再弄一遍就行了。
## 二、下载goagent并上传至Google App Engine ##
  1. 下载goagent并解压，[https://code.google.com/p/goagent/](https://code.google.com/p/goagent/)
  1. 上传
    * Windows用户：双击server文件夹下的upload.bat，输入你上步创建的appid（同时上传多appid在appid之间用 | 隔开,一次只能上传同一个gmail帐号下的appid）填完按回车。根据提示填你的Gmail邮箱，填完按回车。根据提示填你的邮箱密码(注意：如果开启了两步验证，密码应为[16位的应用程序专用密码](https://accounts.google.com/b/0/IssuedAuthSubTokens)而非gmail密码），填完按回车。
    * Linux/Mac用户上传方法：在server目录下执行,[<<更多内容>>](https://code.google.com/p/goagent/wiki/GoAgent_Linux)
```
python uploader.zip
```
> > > ![http://ww4.sinaimg.cn/large/786e2887jw1e3bnmeg954j.jpg?goagent2.1.5-1.jpg](http://ww4.sinaimg.cn/large/786e2887jw1e3bnmeg954j.jpg?goagent2.1.5-1.jpg)
      * 如遇到getaddrinfo failed，error10054，Error 10061 目标计算机积极拒绝等错误而不能上传，可以先运行goagent.exe(要先修改appid)并把IE代理设置为127.0.0.1：8087再运行uploader.bat
      * 要使用IPv6上传或者上传遇到11004错误可以[按照此贴进行修改](https://code.google.com/p/goagent/issues/detail?id=7856#c3)或者下载这个已经修改好的[uploader.zip](https://code.google.com/p/goagent/downloads/detail?name=uploader.zip&can=2&q=)文件覆盖原uploader.zip文件
      * 上传成功就会看图下图界面![http://ww1.sinaimg.cn/large/786e2887jw1e3bnmhap9wj.jpg?uploaded.png](http://ww1.sinaimg.cn/large/786e2887jw1e3bnmhap9wj.jpg?uploaded.png)
  1. 上传成功后把local\proxy.ini中的appid = goagent中的goagent 改成你已经上传的应用的appid (用windows的记事本也可以）
    * 多appid用|隔开，如：appid1|appid2|appid3
```
[gae]
appid = appid1|appid2|appid3
```

## 三、运行客户端 ##
  1. Windows用户运行local文件夹中的goagent.exe   ﹡Linux/Mac用户运行 proxy.py
    * 设置浏览器或其他需要代理的程序代理地址为127.0.0.1:8087
    * 注意：使用过程中要一直运行goagent.exe/proxy.py
    * 代理地址127.0.0.1:8087；如需使用PAC，设置pac地址为http://127.0.0.1:8086/proxy.pac；也可以配合SwitchySharp/AutoProxy等浏览器扩展（SwitchySharp用户可从local文件夹中的SwitchyOptions.bak文件导入配置）[pac是什么？](http://zh.wikipedia.org/wiki/%E4%BB%A3%E7%90%86%E8%87%AA%E5%8A%A8%E9%85%8D%E7%BD%AE)
  1. 导入证书
    * IE/Chrome：使用管理员身份运行goagent.exe会自动向系统导入IE/Chrome的证书，你也可以双击local文件夹中的CA.crt安装证书（需要安装到“受信任的根证书颁发机构”）；
    * Firefox：需要单独导入证书，打开FireFox?->选项->高级->加密->查看证书-><font color='red'>证书机构</font>(必须是这项)->导入证书, 选择local\ca.crt, 勾选所有项，导入；
    * opera：导入证书方法：首选项→高级→安全性→管理证书→<font color='red'>证书颁发机构</font>(必须是这项)->导入->选择local\ca.crt文件->依次确认；

﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎
## 附：浏览器设置方法 ##
  1. ### 谷歌chrome配合Proxy  Switchy Sharp扩展 ###
    1. 安装扩展
      * 地址栏输入chrome://extensions/后按回车，打开扩展管理页，将local文件夹中的SwitchySharp-0.9-beta-[r48](https://code.google.com/p/smartladder/source/detail?r=48).crx拖拽到该页面之后点击确定即可安装，扩展也可以从chrome应用商店获得[https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm](https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm)
> > > > ![http://ww4.sinaimg.cn/large/786e2887tw1e3hhmzjy1zj.jpg?install_Proxy_Switchy_Sharp.png](http://ww4.sinaimg.cn/large/786e2887tw1e3hhmzjy1zj.jpg?install_Proxy_Switchy_Sharp.png)
    1. 导入设置
      * 点击 Proxy  SwitchySharp图标》选项》倒入/导出》![http://ww1.sinaimg.cn/large/786e2887jw1e2s44kpzqyj.jpg?bak.png](http://ww1.sinaimg.cn/large/786e2887jw1e2s44kpzqyj.jpg?bak.png)
      * 浏览到SwitchyOptions.bak，点击确定导入设置
      * 更新自动切换规则（先运行goagent浏览器代理设置为goagent再更新规则）
        * 在扩展设置页点击“切换规则”，点击“立即更新列表”，最后点击“保存”。![http://ww4.sinaimg.cn/large/786e2887tw1e2s3tcf8lij.jpg?getrules.png](http://ww4.sinaimg.cn/large/786e2887tw1e2s3tcf8lij.jpg?getrules.png)
      * 单击地址栏右侧Proxy  SwitchySharp图标即可进行模式选择
> > > > ![http://ww2.sinaimg.cn/large/786e2887tw1e2s3t6x2ivj.jpg?changemode.png](http://ww2.sinaimg.cn/large/786e2887tw1e2s3t6x2ivj.jpg?changemode.png)
        1. GoAgent模式  除匹配proxy.ini中sites的直连外，其他全部通过GAE
        1. GoAgent PAAS模式   全部通过PAAS
        1. GoAgent Socks5模式   全部通过Socks5（暂不可用）
        1. 自动切换模式 根据切换规则自动选择是否进行代理，自动选择使用何种代理
        * 遇到规则中没有的，可以使用扩展的“新建规则”按钮自行添加
        * 偶尔会出BUG，出现设置无误但出现错误130无法连接到代理服务器，可以将自己的设置导出之后卸载重装
  1. ### Firefox配合Foxy Proxy扩展 ###
    1. 安装扩展[https://addons.mozilla.org/zh-cn/firefox/addon/foxyproxy-standard/](https://addons.mozilla.org/zh-cn/firefox/addon/foxyproxy-standard/)
    1. 设置

> > > ![http://ww1.sinaimg.cn/large/786e2887tw1e2s3t8whfdj.jpg?foxyproxy.png](http://ww1.sinaimg.cn/large/786e2887tw1e2s3t8whfdj.jpg?foxyproxy.png)
      * 右击foxyporxy图标即可选择代理模式
> > > ![http://ww4.sinaimg.cn/large/786e2887tw1e2s3taih9wj.jpg?foxyproxy1.png](http://ww4.sinaimg.cn/large/786e2887tw1e2s3taih9wj.jpg?foxyproxy1.png)
    1. 添加代理规则订阅（可选）
      * 这里以添加gfwlist为例，你也可以自行添加其他规则订阅
> > > ![http://ww3.sinaimg.cn/large/786e2887jw1e3f79aksi6j.jpg](http://ww3.sinaimg.cn/large/786e2887jw1e3f79aksi6j.jpg)
> > > ![http://ww2.sinaimg.cn/large/786e2887jw1e3f7955znpj.jpg](http://ww2.sinaimg.cn/large/786e2887jw1e3f7955znpj.jpg)
> > > ![http://ww3.sinaimg.cn/large/786e2887jw1e3f797nabpj.jpg](http://ww3.sinaimg.cn/large/786e2887jw1e3f797nabpj.jpg)
> > > ![http://ww1.sinaimg.cn/large/786e2887jw1e3f79bigcuj.jpg](http://ww1.sinaimg.cn/large/786e2887jw1e3f79bigcuj.jpg)
      * 更多设置请自行探究
  1. ### Firefox配合Auto Proxy扩展（可能不兼容新版Firefox） ###
    1. 安装扩展[https://addons.mozilla.org/zh-cn/firefox/addon/autoproxy/](https://addons.mozilla.org/zh-cn/firefox/addon/autoproxy/)
    1. 设置
      1. 添加代理服务器
> > > > ![http://ww3.sinaimg.cn/large/786e2887tw1e2s3t49g0ej.jpg?autoproxyfirst.png](http://ww3.sinaimg.cn/large/786e2887tw1e2s3t49g0ej.jpg?autoproxyfirst.png)![http://ww1.sinaimg.cn/large/786e2887tw1e2s3t08ft0j.jpg?autoproxy1.png](http://ww1.sinaimg.cn/large/786e2887tw1e2s3t08ft0j.jpg?autoproxy1.png)![http://ww4.sinaimg.cn/large/786e2887tw1e2s3t0sibvj.jpg?autoproxy2.png](http://ww4.sinaimg.cn/large/786e2887tw1e2s3t0sibvj.jpg?autoproxy2.png)
      1. 添加规则订阅
> > > > ![http://ww3.sinaimg.cn/large/786e2887tw1e2s3t241zej.jpg?autoproxyaddrules1.png](http://ww3.sinaimg.cn/large/786e2887tw1e2s3t241zej.jpg?autoproxyaddrules1.png)![http://ww4.sinaimg.cn/large/786e2887tw1e2s3t380m4j.jpg?autoproxyaddrules2.png](http://ww4.sinaimg.cn/large/786e2887tw1e2s3t380m4j.jpg?autoproxyaddrules2.png)
      1. 选择自己需要的模式
> > > > ![http://ww1.sinaimg.cn/large/786e2887tw1e2s3szej8sj.jpg?autoproxy.png](http://ww1.sinaimg.cn/large/786e2887tw1e2s3szej8sj.jpg?autoproxy.png)
        1. 自动模式   根据规则自行选择是否使用代理
        1. 全局模式   全部使用代理
        1. 禁用代理   全部不使用代理
    1. 或者直接使用已安装好autoproxy的Firefox便携版本：[下载](https://code.google.com/p/wwqgtxx-goagent/downloads/detail?name=FirefoxPortable.7z&can=2&q=)
  1. ### opera浏览器设置 ###

> > 同IE一样样有两种方式可选，不过不会影响系统其他程序的联网
      1. 设置代理为127.0.0.1:8087，全部使用goagent代理
> > > > ![http://ww2.sinaimg.cn/large/786e2887tw1e2s3tl5ww7j.jpg?opera1.png](http://ww2.sinaimg.cn/large/786e2887tw1e2s3tl5ww7j.jpg?opera1.png)
        * 不使用时要将IE恢复无代理状态
      1. 使用PAC自动代理
> > > > ![http://ww4.sinaimg.cn/large/786e2887tw1e2s3tlvyqmj.jpg?opera-pac.png](http://ww4.sinaimg.cn/large/786e2887tw1e2s3tlvyqmj.jpg?opera-pac.png)
    * 如果你喜欢折腾的藕粉，也可以按照[这篇文章](http://www.a-shun.com/archives/21451.html)（比较复杂）自己做一个方便切换的按钮，[当然还有精简版的](http://www.ashun.com/archives/21451.html/comment-page-2#comment-41812)
  1. ### IE浏览器设置（不建议） ###
    * IE有两种方式，分别为全部使用goagent代理和是pac自动代理，很多软件都使用IE代理设置，可能影响部分软件的联网，「不建议设置IE代理」
    * 工具》Internet选项》连接，<font color='red'>局域网用户单击"局域网设置"。宽带用户选中自己正在使用的宽带连接之后单击"设置"，不要选“局域网设置”</font>
      * 由于没有宽带环境，这里以局域网用户为例，不为宽带环境做演示，除了名称不一样，设置项都相同
      1. 设置代理为127.0.0.1:8087，全部使用goagent代理（不建议）
> > > > ![http://ww4.sinaimg.cn/large/786e2887jw1e3ewkxcosfj.jpg?ie1.png](http://ww4.sinaimg.cn/large/786e2887jw1e3ewkxcosfj.jpg?ie1.png)
        * 不使用时要将IE恢复无代理状态
      1. 使用PAC自动代理
> > > > ![http://ww1.sinaimg.cn/large/786e2887jw1e3ewkyd12nj.jpg?ie2.png](http://ww1.sinaimg.cn/large/786e2887jw1e3ewkyd12nj.jpg?ie2.png)

﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎

## goagent适用环境 ##
  * 适用：浏览器，支持http代理的下载软件等
  * 不适用：游戏客户端等需要稳定网络的程序，QQ，tor（验证证书）。待添加。。。

## 关于软件更新 ##
  * 更新历史中带有[是]则需要重新上传，否则不用重新上传。注意：是否需要重新上传是相对于前一版的，若你之前版本与当前版本之间某一版或多版带有[是]仍然需要重新上传。
  * goagent每一版下载的都是全部文件，你可以选择覆盖原文件或者将新版放另一个文件夹，旧版你可以选择留存或者删除，修改新版proxy.ini中相关设置即可运行。如果旧版添加了开机启动，需要将旧开机启动删除。如果旧版已经在运行，需先将旧版关闭。
  * 如果之前版本没有ssl错误，使用新版出现ssl错误可以把原来的ca.cer、ca.key和certs文件夹内的文件覆盖当前的这些文件。或者将ca.cer、ca.key和certs文件夹内的文件全部删除，同时删除浏览器中所有goagent ca的证书，再重启goagent，会生成新证书，重启浏览器再导入新证书即可。浏览器证书中只能有一个goagent ca的证书。
﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎﹎
﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊﹊
# ﹡﹡﹡请勿到本页提交软件使用问题﹡﹡﹡ #
  * bug反馈等请到[issues](https://code.google.com/p/goagent/issues/list)页提交
  * 可以在本页提出有关本wiki的建议等，请勿提交无关内容