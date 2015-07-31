#Windows 用户用文本编辑器打开hosts(c:\system32\drivers\etc\hosts)文件，将以下内容复制进去，保存即可（hosts 文件没有后缀）

也可以以管理员身份直接运行 notepad
"%SystemRoot%\system32\drivers\etc\hosts" 进行
编辑

#Linux 用户在终端中执行 sudo gedit /etc/hosts 即可开始编辑

#关闭某个IPv6的转发请在那一行的最前面添加#号，启用请去除最前面#号，每行中间的#号是为了区分地址
和注释，不用理睬


Hosts文件位置
Windows          C:\WINDOWS\system32\drivers\etc\hosts
Linux/Mac OS X   /etc/hosts


建议使用DNS 8.8.8.8/8.8.4.4   (By Google Public DNS) 114.114.114.114/114.114.115.115  (By 114DNS)



---

**Windows系统出现的问题：**

**提示：没有权限**

**解决方法:**

1.找到Hosts文件（ipv6用户请下载把盘内ipv6hosts），将Hosts文件复制到桌面。 （Windows系统Hosts文件路径为：C:\WINDOWS\system32\drivers\etc\hosts）

2.用记事本打开，浏览器打开https://smartladder.googlecode.com/svn/trunk/hosts
Ctrl+A 全选Ctrl+C复制再回到记事本中Ctrl+V 粘贴

3.将修改好的Hosts文件再复制回Hosts文件目录，提示是否覆盖时选择覆盖即可。

通过这个方式可以解决提示无权修改Hosts文件，以后需要修改Hosts时就不再需要再复制到桌面了，因为文件属性已经修改，以后只需要在Hosts目录下修改即可


---

安卓修改Hosts的方法
先通过各种方法让Android手机获取Root权限，之后运行Root Explorer管理器，进入可写状态，找到/system/etc/hosts的文件，将其权限修改为可写。

打开Terminal Emulator，输入su，进入root模式，输入 vi /system/etc/hosts 命令，按i进入编辑模式，之后将用户电脑上的hosts文件内容也输入进去。


---

iOS修改hosts的方法
iOS：需要越狱，iFile→/etc下找到hosts文件→点击选择文本编辑器方式打开→按照电脑上的改法修改hosts即可。