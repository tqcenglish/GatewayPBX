+++
title = 'FXS 与 VitalPBX'
date = 2024-01-19T14:01:40+08:00
+++

## VitalPBX
[VitalPBX](https://vitalpbx.com/) 是一个基于 Asterisk 的 PBX. 基于 ISO镜像虚拟机安装方式进行测试.
在此测试 G 系列 FXS 网关与 Asterisk 的兼容性.


## 创建分机
成功安装 PBX 环境后第一步在 PBX 创建分机, 如下图.
![](/GatewayPBX/img/vitalpbx/vitalpbx_add_pjsip_exten.png)
这里我们使用分机 1019, 1021.
VitalPBX 的 sip 协议包含两种, 创建分机时选择 chan_pjsip. 

默认 VitalPBX 开启了 AVPF 与网关不兼容, 需要如下图关闭.
![](/GatewayPBX/img/vitalpbx/vitalpbx_avpf.png)

## 网关注册
### 配置 VOIPServer
FXS 网关完成基本的网络/时间配置后, 第一步就是创建编辑对应的 PBX 服务器信息. 如下图.
![](/GatewayPBX/img/vitalpbx/gateway_voipserver.png)
通常端口为 5060, 具体以 PBX 端开放监听的地址/端口为准.

### 端口配置分机
FXS 需要为每个端口配置分机, 然后在端口上连接电话线到模拟话机即可.
在网关设备页面能查看对应分机注册状态.
![](/GatewayPBX/img/vitalpbx/gateway_dashboard_status.png)
在 PBX 页面查看对应注册状态.
![](/GatewayPBX/img/vitalpbx/vitalpbx_reg_status.png)

## 拨打测试
模拟话机 1019 拨打 1021, 在状态页面能看见通话中的标识.能正常的呼入/呼入,即与 vitalpbx 联合使用配置成功完成.