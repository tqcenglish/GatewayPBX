+++
title = 'FXS 与 xswitch'
date = 2024-01-18T16:01:40+08:00
+++

## XSwitch
[XSwitch](https://xswitch.cn/) 是一个基于 FreeSwitch 的 PBX. 基于 docker 云部署的方式进行测试.
在此测试 G 系列 FXS网关与 FreeSwitch 的兼容性.


## 创建分机
成功安装 PBX 环境后第一步在 PBX 创建分机(具体查看 Xswitch 使用手册), 如下图.
![](/GatewayPBX/img/xswitch/extension.png)
**不要混淆名称和号码**, 这里我们使用分机 1019, 1020.


## 网关注册
### 配置 VOIPServer
FXS 网关完成基本的网络/时间配置后, 第一步就是创建编辑对应的 PBX 服务器信息. 如下图.
![](/GatewayPBX/img/xswitch/gateway_voipserver.png)
通常端口为 5060, 具体以 PBX 端开放监听的地址/端口为准.

### 端口配置分机
FXS 需要为每个端口配置分机, 然后在端口上连接电话线到模拟话机即可.
若注册成功将看到如下显示.
![](/GatewayPBX/img/xswitch/gateway_fxs-port.png)
在状态页面也可以查看注册状态.
![](/GatewayPBX/img/xswitch/gateway_dashboard_port.png)

## 拨打测试
模拟话机 1019 拨打 1020, 在状态页面能看见通话中的标识.
![](/GatewayPBX/img/xswitch/gateway_dashboard_call.png)

能正常的呼入/呼入,即与 XSwitch 联合使用配置成功完成.