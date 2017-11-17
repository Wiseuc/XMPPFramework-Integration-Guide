###XMPPJiCheng指南

----

原创不易，请多支持! --江海


GitHub：https://github.com/Wiseuc


CSDN： http://blog.csdn.net/wiseuc_jianghai

QQ：   744235238

Email：wiseuc_jianghai@163.com

欢迎👏志同道合的朋友们前来交流！


###资源

```
XMPPFramework ~> 3.7.0  :https://github.com/robbiehanson/XMPPFramework
CocoaAsyncSocket        :https://github.com/robbiehanson/CocoaAsyncSocket
KissXML                 :https://github.com/robbiehanson/KissXML
libidn
CocoaLumberjack         :https://github.com/CocoaLumberjack/CocoaLumberjack

```




###了解


XMPPFramework：

```
  - Authentication 授权登录类
  - Categories     系统分类工具（略）
  - Core           核心库（jid, message, iq, presence, stream, element…）
  - Extension      XMPPFramework工具类
  - Utillties      一般工具类（略）
```

XMPPFramework引用的第三方库Vendor：

```
  - libidn:          GNU Libidn 是一款通过IETF国际域名（IDN）实施字符串预处理、Punycode 和 IDNA规格定义的工具。
                     它用于国际化的字符串（如域名标签，用户名和密码），以增加字符串输入和字符串比较的工作
  - KissXML          KissXML就是一套XML操作工具类
  - CocoaLumberjack  Lumberjack（伐木工）XMPPFramework的日志打印工具类
  - GCDAsyncSocket   最核心文件，XMPPframework封装集成了scoket套接字

```



###集成配置

Library

1. 添加   libidn.a
2. 添加  libresolv.tbd
3. 添加  libxml2.tbd

Build Settings

1. Targets ->  Builds Settings -> Header Search Paths   添加  /usr/include/libxml2






###集成报错

```
由于XMPPFramework 3.7.0版本是适配swift的，所以在OC项目集成的时候会遇到很多问题

1. 不是通过库文件 或 CocoaPods导入的 不需要完整路径
例#import "XMPPFramework/XMPPRoomMessage.h" —》#import "XMPPRoomMessage.h"

2. swift方式导入改OC方式导入
例@import CocoaAsyncSocket; —》 #import "GCDAsyncSocket.h"  #import "GCDAsyncUdpSocket.h"

```

