傻瓜式教程《如何使用 Clash 翻墙》，本文发布于 https://github.com/Sha1rholder/Clash-against-GFW 并不定期更新，随意转载

由于一些 Clash 的 GUI 实现（Clash for Windows、Clash for Android）以及内核删库跑路，本文在 Release 处放了这些软件的下载链接

# 订阅机场

先找个机场，具体选择什么机场请由周围朋友推荐。机场是黑产，跑路风险极大，因此绝对不要包年买。普通用户没有能力了解机场的稳定性和速度，建议同时至少保持订阅两家机场一家主力一家备用。对于主力机场，经常上外网看视频的用户按包月买，不经常看视频的用户买 100 GB 左右不限时的流量包即可；备用机场只需要买一个不限时流量包就行

![机场1](resources/机场1.png)  
购买机场后，请在官网复制订阅链接，稍后会用到

# Windows

## 安装 Clash for Windows

Clash for Windows（简称 CFW）已经删库跑路，请使用以下链接下载 CFW 或 CFW 汉化版

CFW 英文原版：https://github.com/Sha1rholder/Clash-against-GFW/releases/download/Clash/Clash.for.Windows.v0.20.39.setup.exe  
CFW 汉化版：https://github.com/Sha1rholder/Clash-against-GFW/releases/download/Clash/Clash.for.Windows.v0.20.39.Chinese.setup.exe  
（如果下载卡住请关闭下载器用浏览器自带下载引擎下载）

如果无法下载，可以参考 Tips [我上不了 GitHub](#我上不了-github)

## 配置 Clash

将订阅的配置文件链接粘贴进 URL 栏，下载配置文件。下载完成后点击刚下载好的配置文件切换过去（左边会变绿）  
![CFW subscribe](resources/cfwsub.png)

开启模式图标，查看状态栏是否出现一个字母，如果在状态栏找不到可以点击右状态栏左侧向上的小箭头找（蓝色代表未开启系统代理）  
![clashwin5](resources/clashwin5.png)  
![clashwin6](resources/clashwin6.png)

进行延迟检测，选择合适的代理模式和节点，一般来说有 Auto 就用 Auto 即可。节点的名称通常具有其物理地址的含义，例如 `HK` 代表香港节点，`US` 代表美国节点；绿色数字代表延迟，越低越好，红色 Timeout 代表与该节点通讯异常，不建议选择  
![clashwin4](resources/clashwin4.png)

开启系统代理，检查托盘图标是否变成黄色（黄色代表已开启系统代理）  
![clashwin3](resources/clashwin3.png)  
![clashwin7](resources/clashwin7.png)

打开浏览器，访问 https://www.google.com 检查是否成功科学上网  
![clashwin8](resources/clashwin8.png)

**Enjoy your free time!**

# Android

## 安装 Clash for Android

Clash for Android（简称 CFA）已经删库跑路，请使用以下链接下载 CFW（目前只有英文版）

CFA 英文原版：https://github.com/Sha1rholder/Clash-against-GFW/releases/download/Clash/Clash.for.Android.v3.0.3.premium.apk

如果无法下载，可以参考 Tips [我上不了 GitHub](#我上不了-github) 从电脑上下载所需 .apk 文件后发送给手机安装

## 导入配置文件

## 配置 Clash

激活 GlaDOS 配置文件并开启代理  
![clashand2](resources/clashand2.jpg)  
![clashand3](resources/clashand3.jpg)  
![clashand4](resources/clashand4.jpg)

测速并选择合适的代理模式和节点  
![clashand5](resources/clashand5.jpg)  
![clashand6](resources/clashand6.jpg)

（可选）添加 Clash 到 Android 小组件，更方便开关  
![clashand7](resources/clashand7.jpg)

# Tips

## 我上不了 GitHub

GitHub 的服务器在境外，国内访问有时不稳定，可以使用 Watt Toolkit（原名 Steam++）加速 GitHub 等服务

在官网 https://steampp.net/ 下载 Watt Toolkit。该软件完全免费且开源，可以放心使用  
![watt1](resources/watt1.png)

推荐从微软商店下载，国内可用且稳定自动更新  
![watt2](resources/watt2.png)

将软件语言改为中文（开启加速功能的必要条件！）  
![watt3](resources/watt3.png)

全选加速服务，关闭 GitHub Api（加速 GitHub Api 可能与 GitHub Copilot 等服务冲突）并开始加速  
![watt4](resources/watt4.png)

出现“加速已启动成功”即可  
![watt5](resources/watt5.png)

## Clash 中代理模式的区别

Clash 中有四种代理模式：全局代理、规则代理、直连和脚本，它们各有区别和优劣  
![clashproxy](resources/clashproxy.png)

- 全局代理：所有流量都通过代理服务器。对流量消耗较大，可能无法使用部分国内服务
- 规则代理：根据规则选择性地通过代理服务器。基本可以理解为“只有外网流量走代理”，对流量消耗较小，基本可以常开。偶尔出现规则之外的情况，可以使用外部规则转换器如 ZJU-Rule 等优化代理规则或开启全局代理
- 直连：所有流量都不通过代理服务器。通常等效于关闭系统代理
- 脚本：你不需要了解这个

## Windows 突然无法上网

如果你发现电脑联网但无法访问任何网站，可以尝试打开 Clash，开启系统代理再退出 Clash。该问题可能是由于上一次 Clash 未正常退出导致 DNS 故障，开启系统代理后 Clash 会自动修复 DNS。如果仍未能修复，尝试以管理员身份启动 cmd，输入 `netsh winsock reset` 回车 `ipconfig /flushdns` 回车，重启电脑。如果还未能修复请百度修复 DNS 或联系您的网络管理员（我没开玩笑）  
![wintips1](resources/wintips1.png)  
![wintips2](resources/wintips2.png)

## 无法使用 ChatGPT、Netflix 等特定服务

代理节点质量较差，无法突破 ip 封锁。尝试更换节点或更换、自建机场。使用 ChatGPT 的详细教程可以参考 https://github.com/Sha1rholder/use-ChatGPT-in-GFW
