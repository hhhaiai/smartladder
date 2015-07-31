Chromium-dev Ubuntu PPA源

简介

PPA源
ppa:a-v-shkop/chromium-dev

主页
https://launchpad.net/~a-v-shkop/+archive/chromium-dev

推荐原因
官方已经停止提供PPA源，目前找到的能提供较新版本Chromium的源貌似就只有这个了。

详细教程

PPA是什么？
PPA即Personal Package Archive（私人软件包档案）。那么PPA源即提供PPA的地方，通过为apt（Advanced Package Tool）或者软件中心等类似工具添加PPA源，即可长期检查更新你想要安装的软件。不过PPA源的内容很可能是没有得到监管和认证的，因此请慎重选择可靠的PPA源，并且要自行承担相关风险。

如何通过apt自动添加该PPA源并更新Chromium？
打开terminal，执行以下语句，假如遇到提示请选择YES或Y：
sudo add-apt-repository ppa:a-v-shkop/chromium-dev
sudo apt-get update
sudo apt-get install chromium-browser
如何手动为软件中心添加该PPA源？
在sources.list文件（或许在/etc/apt/能找到）最后加上以下两句：
deb http://ppa.launchpad.net/a-v-shkop/chromium-dev/ubuntu quantal main
deb-src http://ppa.launchpad.net/a-v-shkop/chromium-dev/ubuntu quantal main

其中的「quantal」为Ubuntu发行版称号，可根据实际情况改为lucid、maverick、natty、oneiric、precise等，不清楚的可到简介的主页那里查看支持的版本。