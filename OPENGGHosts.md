不Google，毋宁死 – 实时生成的Google hosts文件
分类: 小小极客    标签: DNS, Google, hosts, 屏蔽, 网络, 防火墙     评论: 36人评论

hosts的优点
由于众所周知的原因，中国的Google用户过得很艰辛。为了更好地使用Google服务，不少用户不得不使用hosts把Google域名解析到固定的Google ip上。如我的前一篇日志《为何我们不能正常使用Google加密搜索》所述，hosts优先于DNS服务器，因而这种方法能在一定程度上帮助Google用户。

按照微软知识库里的说法，名称解析的顺序为：

1.客户端检查是否查询名称是其自身；

2.然后，客户端搜索本地 Hosts 文件、 $ IP 地址和名称存储在本地计算机上的列表；

3.查询域系统 (DNS) 服务器；

4.如果仍然不能解决名称，作为备份使用 NetBIOS 名称解析序列。

Google ip时常会变化，如果hosts中的ip过期，反而会使用户无法访问Google服务器，得不偿失。为此，我写了个php脚本实时解析Google ip并生成hosts文件，供各位使用。由于内容全部来自实时解析的DNS结果，所以这个hosts文件永不过期。


hosts的不足
但hosts不支持通配符，不可能包含Google的所有域名，而且会影响CDN的效果。把域名解析成正确的ip地址也并不能解决所有问题。一句话，hosts并非万能。

所以还是再次提醒各位Google用户：

1.及时更新操作系统和浏览器；（前些时候黑客入侵Diginotar并伪造证书，如果用户没有及时更新操作系统和浏览器，就有可能遭受中间人攻击）

2.尽量使用https加密。

如果在使用中遇到任何问题，欢迎跟帖反馈。

使用方法
下载后复制到C:\Windows\system32\drivers\etc\，覆盖掉原来的hosts文件即可。


Changelog
2011-09-26 oop重构，增加接口
2011-09-24 正式上线

本站文章除注明转载外，均为本站原创编译
转载请注明以下信息
文章转载自：鲁夫的爱 [http://opengg.me/ ](.md)
本文标题：不Google，毋宁死 – 实时生成的Google hosts文件
本文地址：http://opengg.me/613/generate-hosts-for-google/