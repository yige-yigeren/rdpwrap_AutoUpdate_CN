# rdpwrap_AutoUpdate_CN

RDP Wrapper Autoupdate 中文汉化版（包含GitHub国内支持）

破解Windows RDP对于连接数量与不能同时在线的问题

## 本项目发行包中已内置了以下开源仓库的发行版
[RDPwrap](https://github.com/stascorp/rdpwrap/) v1.6.2；[RDPwarpAutoupdate](https://github.com/asmtron/rdpwrap)2022-01-01（有修改）

## 主要功能

破解Windows RDP（远程桌面连接）的相关限制，使其可多个用户同时在线

整合了RDPWarp与更新配置文件

Windows Vista及以上受RDPWarp支持，但本项目及RDPwarpAutoupdate部分内容仅做了Windows 10 x64及以上支持（理论兼容Windows 7）

## 修改

首先对于RDP Wrapper Autoupdate功能进行了汉化，以及整合到了一个安装包内，并内置提供了绕过GFW获取配置文件更新（GFW可能导致github部分内容获取不正常）的方法。（请注意RDPConf.exe并没有进行汉化，不会有人连Apply都不会点吧~~才不是我懒了~~）

主要方式分为使用FastGit国内镜像及~~直接修改hosts~~(暂时没写，因为仅适用于没有SNI阻断的情况)

如果你的地区可以稳定直连也可以选择不启用，Fastgit你觉得不好用也可以替换为你喜欢的Github镜像网站。反正你要确保更新源是有效的

另外对于原软件进行了功能添加和补全（比如主动请求管理员权限）

注意：本项目提供汉化支持，作者自己脑洞大开的又增加了一些功能和分块，仅提供这些方面的技术支持。

且因为手头上只有win10/win11的x64电脑，所以部分安装逻辑只支持win10及以后的
x64电脑（理论上兼容win7x64），需要x86支持可以提。

暂不对命令行参数进行汉化以确保兼容性

有功能性问题去原仓库提

## RDPwarp和自动更新

信息:

autopdater首先会尝试官方的rdpwrap.ini。如果正式的rdpwrapper .ini中不支持新的termsrv.dll（远程桌面连接所需dll，该dll可能因为更新而令旧版本失效）, autoupdater首先会尝试asmtron rdpwrapper .ini。autopdater还将使用其他贡献者的rdpwrap.ini文件。

你也可以自定义自己的rdpwarp更新源

### autoupdate.bat可用的参数:

-log =将显示输出重定向到文件autoupdate.log

-reset =清除subscription文件中所有已有订阅源并提供示例(new)

-taskadd =在计划任务程序中添加自启动

-taskremove =在计划任务程序中删除自启动