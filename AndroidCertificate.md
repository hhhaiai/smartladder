导入 GAEProxy CA 到 Android 系统

通用步骤
请确认手机已 ROOT，对于 HTC 的机型，还需确认处于 s-off 状态

1. 备份 /system/etc/security/cacerts.bks 文件

2. 下载 已修改好的根证书 并放于当前目录下，之后在命令行中执行：

adb remount
adb push cacerts.bks /system/etc/security/
adb remount
或者使用 Root Explorer 从 SD 卡复制到 /system/etc/security/ 目录。

3. 重启手机后生效

4.0 及以上系统
1. 下载 原始根证书 置于 SD 卡根目录

2. 进入设置->安全->从SD卡安装证书