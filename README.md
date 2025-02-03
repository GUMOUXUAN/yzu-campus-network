# Better-YZU-Campus-Network
### 本项目为扬州大学校园网食用指南（也许同样适用于情况类似的友校）（目前正在施工中）
作为个人的折腾经验，希望可以帮的上正在阅读本文的各位

话又说回来，会使用github的人真的用的上这种小白写的东西吗……算了，就当是个人记录了

如果本文有任何疏漏可以给譞 [发送邮件](mailto:GMX@daylily.onmicrosoft.com?subject=顾老师我一直是您的粉丝啊)
## NaN-在一切开始之前

由于各种原因，作者办理了一张中国电信的校园卡，每月提供200分钟的通话以及约60GB的流量，还有若干会员，资费为49元（前6个月每月返20元话费），并且可以不限量的使用校园网（包括校内无线网络及以太网）而无需缴纳每月（最高）30元的网络使用费用（虽然按量计费，但是只要同时持有多台设备，用到30元的封顶费用几乎无法避免）

扬州大学使用的是锐捷的校园网认证系统，和大部分校园网一样，使用者需要在认证网页上输入自己的校园网账号密码（统一身份认证系统账号），并选择网络服务提供商，之后连接网络。这就导致很多不支持H5的老旧设备（kindle等），以及根本无法进行网页认证操作的联网电子设备（homepod等）无法正常使用。有的人说，自然可以选择使用移动WiFi——这可以很方便的在各种网购平台上买到，还有人说，真要用的时候拿手机或者电脑开热点也不是不行。但是遗憾的是截至到写稿时，作者还在使用一台有些古旧的iPhone XR，老iPhone差强人意的信号以及续航决定了无法使用“手机开热点”的方案，而便宜的移动WiFi糟糕的质量和连接速率以及好用的移动WiFi并不低廉的价格和并不低廉的价格。况且YZU的校园网在不那么繁忙的时候几乎可以跑到接近千兆的速度，比移动WiFi好多了……总之作者只花了0.001秒就放弃了这个方案  

~~再者某个家伙很喜欢把大量的电视剧和番剧下载到本地观赏，如果用移动WiFi的流量疑似有些奢侈了~~

再再者，作者实际上持有许多电（dian）子（zi）设（la）备（ji），而校园网有设备在线数量的限制，并不能满足这一系列设备的上网需求

总之无论如何，通过某些成本低廉的方案使得这一系列设备可以连接上校园网似乎才是一个不错的选择，也是这一系列工作的初衷

## 00-最初的方案

首先咱有一个非常好的消息，那就是YZU的校园网不限制设备开热点，所以如果阁下恰好有一台电脑且平时不会把它带出宿舍，那么您可以选择将网线一端插入您电脑的rj45网口，另一端插入您宿舍的网口（它通常和宿舍的五孔墙插并排放置），之后您可以打开电脑的浏览器完成网络认证或者访问 [扬州大学信息化建设与管理处](https://xxhc.yzu.edu.cn/info/1082/9044.htm"锐捷客户端下载")下载锐捷客户端，使用统一身份认证系统账号登录

之后您就可以在控制中心打开设备的移动热点并将其他设备连接到电脑的热点了喵

需要注意的是，如果阁下使用的是台式机，可能没有配备无线网卡，自然也无法开启移动热点。（当然如果您购买的是华硕等品牌的高端主板那当我没说）此时您可以选择购买张无线网卡，本文不提供具体的购买建议 ~~（但出于各种原因作者并不是很推荐本方案）~~

***
*小知识：MAC地址（英语：Media Access Control Address），直译为媒体访问控制地址，也称为局域网地址（LAN Address），以太网地址（Ethernet Address）或物理地址（Physical Address），它是一个用来确认网络设备位置的地址。在OSI模型中，第三层网络层负责IP地址，第二层数据链接层则负责MAC地址。MAC地址用于在网络中唯一标示一个网卡，一台设备若有一或多个网卡，则每个网卡都需要并会有一个唯一的MAC地址。*
<p align="right">————摘自wikipedia<p>

好的这是废话，和下文几乎没有关系。因为咱其实没有弄明白为什么方案可行，喵是杂鱼。但无论如何，一个事实是：YZU的校园网……让路由器克隆一台已经完成认证的设备的MAC地址……可以让所有连接到路由器的设备上网了。

所以在最开始，咱使用的方案是去海鲜（xian）市场（yu）购买一台二手（或者三四五六七八手）的路由器，配置方面几乎没有要求，不过出于使用舒适度的考虑，建议还是选购千兆的版本————毕竟就算选那种300M、500M的老东西也不会便宜到哪里去，而使用体验却会差上不少。出于狭隘的外观方面的考量，咱选择了一台中兴和运营商合作的中兴小方糖（Z503）。由于是运营商淘汰下来的，所以只花了28元包邮拿到（包含路由器主机，12V1A电源适配器一个，千兆网线1m）

*20250203修改：阿譞过年从老家顺回来一台华为 ws5200v4 1200M路由器，不过这家伙用的是凌霄的处理器显然不能刷openwrt或者梅林什么的，不过单纯作为一个硬路由还是优于中兴z503，而且还多一个lan口。天线折叠起来也还算美观。以及还有一些奇怪的用途（见图1）
当然这是后话。*

将路由器连接上电源，WAN口插入网线并将另一端插在宿舍墙壁上的网口上，使用另一根网线连接路由器的LAN口和电脑的rj45网口，打开电脑浏览器，依照路由器底部标签访问路由器管理后台（通常为192.182.1.1）。快速配置之后，在上网选项里勾选“克隆MAC地址”，选择连接到路由的唯一一台设备（也就是这台电脑）。之后您只需要使用这台电脑完成校园网的认证，其余连接到路由器的设备都可以直接连接互联网了。

**需要注意的是，使用该方案时，被克隆MAC地址的设备需要连接路由器网络，如果该设备又单独连接了校园网，可能会被踢下线或者被ban。**

**众所周知，校园网有时会将设备踢下线，需要重新登录。此时您只需要按照正常流程使用被克隆MAC地址的设备登录校园网就好**

## 01-校园网自动登录脚本
*“主播主播，你的MAC克隆方法确实很好，可是每次掉线都要手动重新登录还是太麻烦了，有没有更加简单强势的方法”*

*“有的亲爱的，有的，这么好用的方法当然不止一个喵ヾ(•ω•`)o”*

这就是接下来要讲的，也是阿譞的最新科研成果——一个运行在宿舍内固定设备上的脚本

本脚本设计之初是为了长期运行在宿舍内使用黑苹果的小主机上，并使用硬路由克隆小主机的MAC地址，进而达成让宿舍内其他无法通过正常方式连接校园网的设备联网的目的

理论上您如果使用macbook或者mac、macmini等运行正版macos的设备同样可以参考本项目

如果您打算使用搭载了openwrt或其他系统的软路由，请视情况参考本项目

**注意：本项目提供且仅提供一个代替手动登录的方法，并非绕过、破解等行为**

**免责声明：请确定您的学校允许（或默许）此行为，作者对于此造成的任何连带后果不承担任何责任**

以及宿舍内的小主机是一台NEC第八代小主机（即联想M720Q日版换皮版本），使用第八代英特尔® 酷睿™ i5 处理器，运行MACOS 14.5系统，基本算得上是完美黑苹果（大概）

之后有时间可以展开说一说就是了

~~阿譞是碎碎念领域大神~~

**免责声明2：作者显然并非计科专业，未经过系统学习，如有问题还请谅解，阿里嘎多**
***
