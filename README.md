# MUCE V3 Package 说明文档
## 1.简介
如果需要添加一个新的 log，那么请先确认 log 的类型，这部分请阅读 EventPackage 部分，再确认要看这条 log 所需的筛选条件是否已经存在，这部分请阅读 CommonPackage 部分，如果没有，请确认所需的筛选条件属于哪个 ExtraPackage。

## 2.log事件分类
### 2.1 点击事件
包含的筛选条件：  
[CommonPackage](#CommonPackage) common  
[EventPackage](#EventPackage) event  
┗[ClickEvent](#ClickEvent) click_event  
[ExtraPackage](#ExtraPackage) extra
### 2.2 展示事件
包含的筛选条件：  
[CommonPackage](#CommonPackage) common  
[EventPackage](#EventPackage) event  
┗[ShowEvent](#ShowEvent) show_event  
[ExtraPackage](#ExtraPackage) extra
### 2.3 应用活跃事件
包含的筛选条件：  
[CommonPackage](#CommonPackage) common  
[EventPackage](#EventPackage) event  
┗[ApplicationActiveEvent](#ApplicationActiveEvent) active_event  
[ExtraPackage](#ExtraPackage) extra  
┗[DevicePackage](#DevicePackage) device_package
### 2.4 应用启动事件
包含的筛选条件：  
[CommonPackage](#CommonPackage) common  
[EventPackage](#EventPackage) event  
┗[ApplicationStartEvent](#ApplicationStartEvent) start_event  
[ExtraPackage](#ExtraPackage) extra  
┗[DevicePackage](#DevicePackage) device_package
### 2.5 应用崩溃事件
包含的筛选条件：  
[CommonPackage](#CommonPackage) common  
[EventPackage](#EventPackage) event  
┗[ApplicationCrashEvent](#ApplicationCrashEvent) crash_event  
[ExtraPackage](#ExtraPackage) extra  
┗[DevicePackage](#DevicePackage) device_package
### 2.6 任务事件
包含的筛选条件：  
[CommonPackage](#CommonPackage) common  
[EventPackage](#EventPackage) event  
┗[TaskEvent](#TaskEvent) crash_event  
[ExtraPackage](#ExtraPackage) extra  

## 3.<a name="CommonPackage"/>CommonPackage
用于记录通用 log 信息，所有的 log 都会带有这些筛选条件  
CommonPackage common  
┃ID信息  
┣[IdPackage](#IdPackage) id_package  
┃客户端信息  
┣[ClientPackage](#ClientPackage) client_package  
┃时间信息  
┣[TimePackage](#TimePackage) time_package  
┃网络状况信息  
┣[NetworkPackage](#NetworkPackage) network_package  
┃注册账号信息  
┣[AccountPackage](#AccountPackage) account_package  
┃启动来源信息  
┗[LaunchSourcePackage](#LaunchSourcePackage) launch_source_package  
### 3.1 <a name="IdPackage"/>IdPackage
用于记录ID信息  
IdPackage id_package  
┃major id，如果是移动设备id=udid,如果是pc设备id=pcid  
┣string id  
┃移动设备的 id  
┣string udid  
┃PC 的 id  
┗string pcid  
### 3.2 <a name="ClientPackage"/>ClientPackage
用于记录客户端基本信息  
ClientPackage client_package  
┃产品类型  
┣[Product](#Product) product  
┃设备平台  
┣[Platform](#Platform) platform  
┃首次安装时渠道号  
┣string first_source  
┃产品当前的渠道号  
┣string last_source  
┃此时设备上的产品渠道来自 PC 的渠道号  
┣string windows_source  
┃产品的版本名,如: 4.6.1  
┣string version_name  
┃产品的版本号  
┣int32 version_code  
┃客户端的语言版本(如 thai 表示泰语版本)  
┣string locale  
┃客户端选择的语言  
┣[Language](#Language) language  
┃内部版本号  
┣int32 internal_version_code  
┃客户端第一次安装的时间(使用Unix timestamp)  
┗int64 create_date  

><a name="Product"></a>Product  
产品类型  
WINDOWS（windows产品）  
ANDROID（p4）  
USB_CONNECTION（usb连接引擎）  
GAME_SDK（游戏sdk）  
MARIO_SDK（mario sdk）  
IOS（IOS版）  
ADS（广告）

><a name="Platform"></a>Platform  
设备平台  
ANDROID  
ANDROID_TABLET  
IPHONE  
IPAD  
PC  

><a name="Language"></a>Language  
语言  
SIMPLE_CHINESE（简体中文）  
ENGLISH（英文）  
THAI（泰文）  

## 4.<a name="EventPackage"/>EventPackage
### 4.1 <a name="ClickEvent"/>ClickEvent
用于记录点击事件的 log  
包含的筛选信息如下：  
点击的控件的log  
[ViewLogPackage](#ViewLogPackage) click  
上一次点击的控件的log  
[ViewLogPackage](#ViewLogPackage) refer_click  
上一个页面最后点击的控件的log  
[ViewLogPackage](#ViewLogPackage) from_click
### 4.2 <a name="ShowEvent"/>ShowEvent
用于记录展示事件的 log  
包含的筛选信息如下：  
展示的控件的log  
[ViewLogPackage](#ViewLogPackage) view  
上一个页面的log  
[ViewLogPackage](#ViewLogPackage) from_page  
上一次点击的控件的log  
[ViewLogPackage](#ViewLogPackage) refer_click  
上一个页面最后点击的控件的log  
[ViewLogPackage](#ViewLogPackage) from_click
### 4.3 <a name="ApplicationActiveEvent"/>ApplicationActiveEvent
用于记录应用活跃的 log  
不包含任何筛选条件
### 4.4 <a name="ApplicationStartEvent"/>ApplicationStartEvent
用于记录应用启动的 log
### 4.5 <a name="ApplicationCrashEvent"/>ApplicationCrashEvent
用于记录应用崩溃的 log
### 4.6 <a name="TaskEvent"/>TaskEvent
用于记录任务事件的 log
### 4.7 <a name="ViewLogPackage"/>ViewLogPackage
用于记录控件的 log  

## <a name="ExtraPackage"/>5.ExtraPackage
