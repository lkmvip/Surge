# 使用手册

### 简介

本项目最早是基于 [scomper/surge.conf](https://gist.github.com/scomper/915b04a974f9e11952babfd0bbb241a8) 定制修改而来，现已形成独有风格。

---
* [支持应用](#application)
	* Surge
	* Shadowrocket
	* Quantumult
* [可实现功能](#function)
* 导入方式
    * [URL](#url)
    * [Workflow](#workflow关注微信公众号墙洞说发送rule-即可获取最新-user-data--rule-ota)
    	* User Data
    	* Rule OTA
* [证书的安装及信任](#mitm)
* [Android SSR ACL](#android-ssr-acl)
* [浏览器广告](#browser-ad)
* [联系方式](#联系方式)
* [Q&A](#qa)
* [客户端](#客户端有r标示表示支持-ssr)
* [教程/说明](#教程--说明)
* [配置文件样例](#配置文件样例)
* [鸣谢](#鸣谢)
* [License](#license)

---

### Application

Configuration | Source
----|----
Surge | [@lhie1](https://t.me/lhie1)
Shadowrocket | [@lhie1](https://t.me/lhie1)
Quantumult | [@WatanabeMayu](https://t.me/WatanabeMayu)

---

### Function
* 自动代理 / 全局代理
* 解决本地 DNS 可能带来的干扰
* 解决谷歌跳转问题
* 可突破部分内网限制（公司、学校）
* 拦截常用应用程序的行为分析
* 拦截常用应用程序的数据统计
* 拦截常用应用程序的隐私跟踪
* 拦截各大购物网站的运营商劫持
* 拦截 Content Security Policy 劫持
* 屏蔽部分应用程序的启动广告
* 屏蔽部分运营商劫持网页弹出的流量统计
* 屏蔽部分运营商劫持网页弹出的漂浮球广告
* 屏蔽常用视频广告
* 屏蔽常用网站广告、其他流媒体网站广告
* 所有国内网站直线连接
* Apple 服务加速（App Store、Apple Music、Apple流媒体、iCloud备份、iCloud Drive、iTunes 等）
* 国外常用网站加速（Google/Youtube/Twitter/Facebook/instagram/wikipedia/Github 等）

---

### URL

````
Surge：https://raw.githubusercontent.com/lhie1/Surge/master/Surge.conf

Shadowrocket：https://raw.githubusercontent.com/lhie1/Surge/master/Shadowrocket.conf
````

---

### Workflow（关注微信公众号：墙洞说；发送“Rule” 即可获取最新 User Data + Rule OTA）

* [User Data](#user-data)
    * [自定义[Proxy]节点](#proxy)
    * 自动根据[Proxy]内容生成[Proxy Group]
    * 自定义添加[Rule]规则
    * 自定义添加[Host]规则
    * 自定义添加[URL Rewrite]规则
    * 自定义添加[SSID Setting]规则
    * 自定义添加 DNS
    * 自定义删除规则（All）
    * 运行时检查更新
    * 生成证书
    * [Widget 策略](#widget-策略)
* [Rule OTA](#rule-ota)
    * [Module](#module)
        * Ads
        * mitm
    * [Special_Proxy](#special_proxy)
        * Netflix
        * Spotify
        * MytvSUPER
        * LINE
    * 运行时检查更新并自动下载
    * 自动修复`module`模块地址
    * 更新规则
    * 生成规则
    * 提交自定义规则
    * [安装证书](#mitm)
    * [常见问题](#workflow_qa)

---

### User Data

#### Proxy

* ##### Surge / Shadowrocket：
````
Proxy_name = custom,host.com,1234,rc4-md5,password,http://omgib13x8.bkt.clouddn.com/SSEncrypt.module
````

* ##### Surge：
````
Managed_url
````

* ##### Shadowrocket：
````
Proxy_name
````


#### Widget 策略

![](https://raw.githubusercontent.com/lhie1/Surge/master/images/Widget.JPG)

### Rule OTA

#### Module
* ##### Ads
````
关闭此功能将不再屏蔽广告
````

* ##### MITM
````
关闭此功能可能会无法拦截部分广告
````
---

#### Special_Proxy
* ##### Netflix
````
开启此功能为`Netflix`单独选择一个专用节点
````

* ##### Spotify
````
开启此功能为`Spotify`单独选择一个专用节点
````

* ##### MytvSUPRE
````
开启此功能为`MytvSUPRE`单独选择一个专用节点
````

* ##### LINE
````
开启此功能为`LINE`单独选择一个专用节点
````
---

### MitM

简介：MitM（即 Man-in-the-middle attack，用于解密 HTTPS 的流量）

iOS：
````
iOS 9 以上的系统都需要在安装证书后到关于本机里信任证书才可使其证书有效。

1. 安装：
* Surge：配置 - 编辑配置 - HTTPS 解密 - 安装证书
* Shadowrocket：设置 - 证书 - 安装证书
* Quantumult：Settings - HTTPS - HTTPS Decryption

2. 信任：
设置 - 通用 - 关于本机 - 证书信任设置 - 信任
````

macOS：

![](https://raw.githubusercontent.com/lhie1/Surge/master/images/macOS_MitM.jpg)

---

### Workflow_Q&A

![](https://raw.githubusercontent.com/lhie1/Surge/master/images/Workflow_Q&A.JPG)

1. 网络连接失败，切换节点或者更换网络环境
2. 证书效验失败，[检查证书](#mitm)
3. 获取文件出错，更新 User Data
4. 脚本缺失，获取 Rule OTA

---

### 联系方式

微博：[lhie1](http://weibo.com/1748625493)

墙洞（规则讨论/交流）：[https://telegram.me/lhie1x](https://telegram.me/lhie1x)

规则更新通知（新特性/教程/说明）：[http://t.me/RuleNews](http://t.me/RuleNews)

购买翻墙服务：[https://墙洞.com](https://墙洞.com)（[了解详情](https://github.com/lhie1/tuClub/blob/master/README.md)）

长时间的维护和分享离不开大家的鼓励与支持，如果帮助到您，可以考虑捐赠，谢谢。

![](https://raw.githubusercontent.com/lhie1/Surge/master/images/Pay.jpeg)

---

### Android SSR ACL
项目主页：https://github.com/ACL4SSR/ACL4SSR

````
1. banAD.acl（默认代理）去广告+局域网直连+国内IP段直连+国内常用域名直连+国外代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/banAD.acl
	
2. gfwlist-banAD.acl（默认直连）去广告+局域网直连+国外gfwlist列表代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/gfwlist-banAD.acl
	 
3. onlybanAD.acl（默认代理）去广告+局域网直连+全局代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/onlybanAD.acl
	
4. fullgfwlist.acl（默认直连）国外gfwlist列表代理，没有去广告，没有白名单（原版SS可直接复制文件内容使用）
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/fullgfwlist.acl
	
5. backcn-banAD.acl（默认直连）去广告+国内IP段代理+国内常用域名代理+局域网直连+国外直连
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/backcn-banAD.acl
````
---

### Browser Ads
````
Adguard：https://adguard.com/en/welcome.html
````
---

### Q&A

#### Surge 开启共享模式
````
Surge 在增加了代理共享模式，只需要开启就能让 Wi-Fi 网络中的其他设备通过这台 iPhone 代理访问网络

到高级设置中开启 Allow Wi-Fi Access ，或者直接修改配置文件，添加一行参数 allow-wifi-access = true

其他 Wi-Fi 网络环境下的设备可以输入已经开启共享代理的 Surge 设备的 IP 地址和端口号，（技巧：Surge Log 中能看到开启后本机的 IP 地址和监听端口）将 IP 地址填写到需要共享设备的 Wi-Fi 信息的 HTTP 代理里即可
````

#### 🍃 Proxy & 🍂 Domestic & ☁️ Others & 🍎 Only
````
🍃 Proxy：管控国外的流量；🚀 Direct - 直连，不可访问外网；代理服务器 - 可访问外网

🍂 Domestic：管控国内的流量；🚀 Direct - 智能分流 (Pac)；🍃 Proxy - 全局代理

☁️ Others：掌控规则名单外的非国内 IP 的流量

🍎 Only： 管控苹果的流量；如果苹果某些服务直连困难，设其为代理，可能会改善一些问题：🍎 Only - 代理服务器

建议 ： 🍃 Proxy - 代理服务器；🍂 Domestic - 🚀 Direct ；☁️ Others - 🍃 Proxy ；🍎 Only - 🚀 Direct / 代理服务器
````

#### 🏃 Auto
````
测试结果仅供参考，无法检测出 VPS 的带宽

请不要使用 google.com 作为测试目标，有可能导致 proxy 服务器 ip 被加入黑名单，导致各种操作需要输入验证码
目标 URL 对所有的 policy 是基本公平的，所以请选择像 gstatic.com 这样的在全球都有节点的 URL 作为测试目标
作者建议：http://www.gstatic.com/generate_204
````

#### 广告屏蔽未生效
````
绝大多数广告在未开启 Surge/Shadowrocket 时已经缓存到本地，广告屏蔽非立即生效，一般清理缓存就可以，部分应用需要卸载重装。
````

#### 耗电
````
当开启此类应用之后，由于所有的网络通信都被此类软件接管，所以所有的网络通讯耗电（如 WiFi、4G）都被计算在了此类应用上，使得此类软件在电量统计中占比很高。
但实际上，开启此类应用对电量消耗不会有显著影响。
````

#### 规则数量会对耗电、内存、速度产生影响吗？
````
不会，此类应用每次加载规则时都会生成一棵搜索树，可以理解为对主机名从后往前的有限状态机 DFA，并不是逐行匹配，并且对每次的匹配结果还有个哈希缓存。换句话说，2000 行的规则和 50 行的规则均为同一量级的时间复杂度 O(1)。
````

#### Surge 2 提示激活过多设备
````
Surge 2的防盗版策略为单次购买后，在最近 180 天内，若已激活的设备数量超过 10 台，则将拒绝激活新设备（家庭共享将共享购买者账号的 10 次限制）。如特殊情况请发送邮件联系作者重制。
````

#### Surge 3 提示规则过多
````
由于我维护的规则大部分用于屏蔽广告，无法进行精简，如果介意可以在通过 Workflow 生成规则时将屏蔽广告功能关闭，如果不介意请到更多 - 警告信息，关闭警告即可。
````

#### MitM 是什么？
````
用于解密 HTTPS 流量（即 Man-in-the-middle attack 简称 MitM）。
````

#### 为什么需要开启 MitM 功能？
````
屏蔽部分广告（如：新浪微博的启动广告）需要解密其 HTTPS 流量才可获取广告请求并进行拦截。
````

#### 打开某些应用（如：知乎、即刻等）无法连接？
````
检查证书，请确保已经安装证书并信任。
````

#### 为什么Surge/Shadowrocket/Quantumult 测速差距这么大？
````
Surge 是从目标 policy 返回 http response header 数据包的时间

Shadowrocket 支持两种测速方式（ICMP/TCP），默认为 ICMP 模式（即 Ping），一般用来测试此服务器是否在线。

Quantumult 采用 SSH 测速模式（22 端口）

准确度：Surge -> Quantumult -> Shadowrocket
````

#### 为什么 Surge 无法屏蔽优酷广告？
````
优酷为了防止广告请求被拦截，强制不通过代理访问。其他同类应用使用的是 HTTP 首包识别，所以在 TUN 模式下也能识别到该请求。Surge 是完整的 HTTP Proxy Server，在 TUN 模式下不会进行 HTTP 解析尝试。所以不会识别到这个请求。但是其他同类应用使用的方式，在 HTTP 请求使用 Keep-Alive 时可能会出现问题，无法识别到后续的请求。
````

#### 三者之间到底有什么不同？
````
功能上面大同小异，基于规则皆可达到自动分流/广告屏蔽的效果。
````

#### MitM 会影响安全（购物/网银/隐私）或性能/速度吗？
````
MitM 仅仅对预设的 Hostname 名单（公开/开源）内的地址进行 HTTPS 流量解密，不会造成安全问题，也几乎不会对性能/速度造成影响。
MitM：https://zh.wikipedia.org/wiki/中间人攻击
Surge MitM：https://medium.com/@Blankwonder/surge-mitm-5281d8ace79d
````

#### 使用规则会影响免流（如：大王卡）吗？
````
我的规则默认为自动分流（国内直连/国外代理），只要自己不对规则进行改动或改动代理模式是不会影响免流效果的。
````

#### 如何获取最新 Workflow 脚本？
````
关注微信公众号：墙洞说，发送“规则”即可获取 Workflow 脚本地址，使用 Safari 打开其链接 Get 即可。
````
---

#### 客户端（有“R”标示表示支持 SSR）：
````
• iOS

Surge：https://appsto.re/cn/D0Q_9.i

Shadowrocket (R)：https://appsto.re/cn/UDjM3.i

Quantumult（R）：https://itunes.apple.com/us/app/quantumult/id1252015438?mt=8
        
• Android

ShadowsocksR (R)：http://omgib13x8.bkt.clouddn.com/ssr-android.apk

Postern (R)：http://www.tunnel-workshop.com

• macOS

ShadowsocksX：http://omgib13x8.bkt.clouddn.com/ss-mac.zip

ShadowsocksX-R (R)：http://omgib13x8.bkt.clouddn.com/ssr-mac.dmg
        
Flora：https://github.com/huacnlee/flora-kit

Specht Lite：https://github.com/zhuhaow/SpechtLite/releases
        
Surge：http://nssurge.com

• Windows

Shadowsocks：http://omgib13x8.bkt.clouddn.com/ss-win.zip
    
ShadowsocksR (R)：http://omgib13x8.bkt.clouddn.com/ssr-win.7z

• 路由器固件

老毛子：http://www.right.com.cn/forum/thread-161324-1-1.html

梅林：http://koolshare.cn/thread-133873-1-1.html
````

---

#### 教程 / 说明：
````
Surge for iOS：https://medium.com/@scomper/surge-配置文件-a1533c10e80b
    
Surge for macOS：https://medium.com/@scomper/让人耳目一新的-surge-mac-2-0-bb7cf735b1b8
    
Shadowrocket for iOS：http://matrix.sspai.com/p/c113cba0
    
SSR for Windows：https://ocvpn.wordpress.com/2016/10/15/shadowsocksr-for-windows设置教程
    
SSR for Android：https://yhyy135.github.io/how-to-use-ssr-android/
````

---
#### 配置文件样例
````
# Surge Config Example (Chinese)
# Version 2.0

[General]
# 日志等级: warning, notify, info, verbose (默认值: notify)
loglevel = notify
# 跳过某个域名或者 IP 段，这些目标主机将不会由 Surge Proxy 处理。(在 macOS 
# 版本中，如果启用了 Set as System Proxy,  那么这些值会被写入到系统网络代理
# 设置中.)
skip-proxy = 127.0.0.1, 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12, 100.64.0.0/10, localhost, *.local
# 强制使用特定的 DNS 服务器
dns-server = 8.8.8.8, 8.8.4.4
# 允许外部控制器访问 Surge， 如 Surge-CLI。
external-controller-access = apassword@127.0.0.1:8888

# 以下参数仅供 iOS 版本使用
# 将系统相关请求交给 Surge TUN 处理，并自动追加规则 
# "IP-CIDR,17.0.0.0/8,DIRECT,no-resolve"
bypass-system = true
# 将特定 IP 段跳过 Surge TUN，详见 Manual
bypass-tun = 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12
# 是否启动完整的 IPv6 支持 (默认值: false)
ipv6 = false

# 以下参数仅供 macOS 版本使用
# 监听地址 (默认值: 127.0.0.1)
interface = 0.0.0.0
# HTTP 服务端口 (默认值: 6152)
port = 6152
# SOCKS5 监听地址 (默认值: 127.0.0.1)
socks-interface = 0.0.0.0
# SOCKS5 服务端口 (默认值: 6153)
socks-port = 6153

# 该段定义可用的代理策略
# 针对所有类型代理的选项:
#   interface: 可选 (默认值: null)
#   强制使用特定的出口地址或网络设备 (仅 macOS 版可用)
#   例如: ProxyHTTP = http, 1.2.3.4, 443, username, password, interface = en2
#        en1 = direct, interface = en1
# 针对启用了 TLS 的代理的选项:
#   skip-common-name-verify: "true" 或 "false" (默认值: false)
#   如果启动该选择, Surge 不会校验证书名是否符合.
[Proxy]
ProxyHTTP = http, 1.2.3.4, 443, username, password, skip-common-name-verify=false
ProxyHTTPS = http, 1.2.3.4, 443, username, password, tls=true // 等价于 "https, 1.2.3.4, 443, username, password"
ProxySOCKS5 = socks5, 1.2.3.4, 443, username, password
ProxySOCKS5TLS = socks5, 1.2.3.4, 443, username, password, tls=true

# 该段定义可用的策略组
# 一个策略组可以包括多个子策略. 
# 子策略可以是一个代理策略，或者另一个策略组，或者是一个内置策略 (DIRECT 或 REJECT).
# 有 3 种策略组类型: "select", "url-test" 和 "ssid"
# select: 具体哪个子策略将被使用，由用户界面上进行选择。
# url-test: 具体哪个子策略将被使用，通过测试到具体 URL 的访问速度选择
#   参数:
#   url: 必填
#   测试时用到的目标 URL.
#   interval: 可选, 秒 (默认值: 600s)
#   指定在多长时间后，上次的测试结果将被抛弃。
#   tolerance: 可选, 毫秒 (默认值: 100ms)
#   只有当新的优选线路，比原优选线路的响应时间，大于该值的时候，才会触发线路变更。
#   timeout: 可选, 秒 (默认值: 5s)
#   如果某策略在该时间后依然没有完成，放弃该策略。
# ssid: 具体哪个子策略将被使用，根据 Wi-FI 的 SSID 决定
#   参数:
#   default: 必填
#   默认策略。
#   cellular: 可选
#   在数据网络下的策略。 若不填，那么默认策略将被使用。
[Proxy Group]
SelectGroup = select, ProxyHTTP, ProxyHTTPS, DIRECT, REJECT
AutoTestGroup = url-test, ProxySOCKS5, ProxySOCKS5TLS, url = http://www.google.com/generate_204
SSIDGroup = ssid, default = ProxyHTTP, cellular = ProxyHTTP, SSIDName = ProxySOCKS5

# 该段定义请求处理规则
# 一个规则有三个基础部分:
#          类型,          值,            策略
# 比如:     DOMAIN-SUFFIX,apple.com,     DIRECT
#          IP-CIDR,      192.168.0.0/16,ProxyA
# 有 3 种基于域名的规则: "DOMAIN", "DOMAIN-SUFFIX" 和 "DOMAIN-KEYWORD"
#   参数:
#   force-remote-dns: 可选 (默认值: false)
#   如果某请求被该规则匹配, 且策略不是DIRECT. 那么 DNS 查询将永远在远端代理服务
#   器执行, 即使该请求由 Surge TUN 处理. 
#   更多信息请参见手册.
# 有 2 种基于 IP 的规则: "IP-CIDR" and "GEOIP".
# 如果是一个使用域名进行访问的请求，那么 Surge 将进行 DNS 查询以确认是否应该被
# 该规则匹配. 若 DNS 查询失败，将放弃规则匹配过程并直接给出错误。
#   OPTIONS:
#   no-resolve: 可选 (默认值: false)
#   如果是一个使用域名进行访问的请求，跳过该条规则，不触发 DNS 查询。
[Rule]
DOMAIN-SUFFIX,appldnld.apple.com,DIRECT
DOMAIN-SUFFIX,adcdownload.apple.com,DIRECT
DOMAIN-SUFFIX,swcdn.apple.com,DIRECT
DOMAIN-SUFFIX,phobos.apple.com,DIRECT

DOMAIN-KEYWORD,google,ProxyHTTP,force-remote-dns
DOMAIN-KEYWORD,facebook,SelectGroup
DOMAIN-KEYWORD,blogspot,AutoTestGroup
DOMAIN-KEYWORD,youtube,SSIDGroup

DOMAIN-SUFFIX,apple.com,ProxyHTTPS
DOMAIN-SUFFIX,ad.com,REJECT

IP-CIDR,192.168.0.0/16,DIRECT,no-resolve
IP-CIDR,10.0.0.0/8,DIRECT
IP-CIDR,172.16.0.0/12,DIRECT
IP-CIDR,127.0.0.0/8,DIRECT

GEOIP,CN,DIRECT
FINAL,ProxyHTTP

# 该段定义本地 DNS 记录
# 该功能等同于 /etc/hosts，加上了泛解析和别名支持。
[Host]
abc.com = 1.2.3.4
*.dev = 6.7.8.9
foo.com = bar.com
bar.com = server:8.8.8.8
computer = server:system

# 该段定义针对 HTTP 请求的 URL 重定向规则
# 有两种重定向方式: "header" 和 "302"
# 
# Header 模式
# Surge 会修改发出的 http header，必要时还会修改 Host 字段。客户端将
# 感知不到这个重定向过程. 不支持重定向到一个 HTTPS 的地址。
# 
# 302 模式
# Surge 直接简单的返回一个 302 重定向回应。
[URL Rewrite]
^http://www.google.cn http://www.google.com header
^http://yachen.com https://yach.me 302

# 该段仅在 iOS 版本下生效。 
# 你可以为某些特定的 WiFi 网络设置设置参数
# 参数:
# suspend: "true" 或 "false"
# 在该网络下 Surge 将暂停工作。 请注意，如果你在该网络下直接启动 Surge，那么 
# Surge 依然会工作。只有当从其他网络切换到该网络时，Surge 才会暂停。
[SSID Setting]
"SSID Here" suspend=true

# 详细使用方法请参见使用手册: http://manual.nssurge.com/mitm.html
[MITM]
enable = true
# Surge 仅会对在此定义的主机名进行 HTTPS 解密，允许使用 * 通配符。
# 某些应用会使用加强的安全策略，仅允许特定的服务器证书或者 CA。启动 MitM 可能
# 导致这些应用出现问题。
hostname = *google.com
ca-p12 = MIIJtQ.........
ca-passphrase = password
````
---
        
### 鸣谢
* [@Eval](https://twitter.com/OAuth4)
* [@Scomper](https://medium.com/@scomper)
* [@Neurogram](http://www.taguage.com/user?id=181456)
* @suisr9255
* [@Hackl0us](https://github.com/Hackl0us)
* [@unknownTokyo](https://t.me/unknownTokyo)
* [@Jacky Y](https://t.me/WatanabeMayu)

---

### License
* 可以拷贝、转发，但是必须提供原作者信息，同时也不能将本项目用于商业用途。

