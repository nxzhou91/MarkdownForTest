# MUCE V3 Package 说明文档
## 1.简介
如果需要添加一个新的 log，那么请先确认 log 的类型，这部分请阅读 EventPackage 部分，再确认要看这条 log 所需的筛选条件是否已经存在，这部分请阅读 CommonPackage 部分，如果没有，请确认所需的筛选条件属于哪个 ExtraPackage。
## 2.EventPackage
### 2.1 ClickEvent
用于记录点击事件的 log</br>
包含的筛选信息如下：</br>
[ViewLogPackage](#ViewLogPackage) click</br>
[ViewLogPackage](#ViewLogPackage) refer_click</br>
[ViewLogPackage](#ViewLogPackage) from_click
### 2.2 ShowEvent
用于记录展示事件的 log
### 2.3 ApplicationActiveEvent
用于记录应用活跃的 log
### 2.4 ApplicationStartEvent
用于记录应用启动的 log
### 2.5 ApplicationCrashEvent
用于记录应用崩溃的 log
### 2.6 TaskEvent
用于记录任务事件的 log
### 2.7 使用到的数据类型
#### <a name="ViewLogPackage"/>ViewLogPackage
