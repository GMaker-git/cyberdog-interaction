# <center>connector</center>
## 许可证（License）
```
Copyright (c) 2023 Beijing Xiaomi Mobile Software Co., Ltd. All rights reserved.

Licensed under the Apache License, Version 2.0 (the 'License');
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an 'AS IS' BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
## <font color=Blue size=4> 目录 </font>
* [1. 修订](#1-修订)
* [2. 概述](#2-概述)
* [3. 设计](#3-设计)
    * [3.1. 功能设计](#31-功能设计)
    * [3.2. 模块设计](#32-模块设计)
---
## 1. 修订

<center>

项目|软件版本|协议版本|修订日期|修订人员|备注
:--:|:--|:--|:--:|:--:|:--:
快连|V1.1.0.0|V1.0.0.0|2023-02-06|尚子涵|无

</center>

## 2. 概述
仿生机器人快速连接网络及目标设备（下文简称快连）场景主要有以下特性：
1. 仿生机器人处于WiFi环境中；
    * WiFi可以是第三方路由的WiFi；
    * WiFi也可以是APP所在设备外放的热点。
2. App所在设备已连接上目标WiFi；
3. App发起的使得仿生机器人连接目标WiFi；
4. 仿生机器人连接目标WiFi成功后再连接目标APP所在设备；
5. 最终实现快速和目标WiFi及设备建立连接。

## 3. 设计
### 3.1. 功能设计

<center>

![](./doc/image/cn_connector.png)

</center>

如上图所示，快连功能主要有两个：
1. 配网功能：通过长按touch来实现开关；
2. 自动连接：通过系统自带的重连机制实现。

#### 3.2 模块设计

<center>

![](./doc/image/cn_connector_module.svg)

</center>

如上图所示，仿生机器人快速连接网络及目标设备架构组成及各组成部分主要功能如下：
1. touch：提供机器人头部触摸信号。
2. led：提供展示机器人头部及身体上灯效功能。
3. audio：提供机器人语音播报功能。
4. camera：提供视野内图像数据。
5. QRreader：提供二维码识别功能。
6. WiFi：提供 linux 系统的目标WiFi连接功能。
7. App：提供 携带WiFi信息的 二维码生成功能。
