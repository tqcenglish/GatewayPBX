+++
title = 'FXS 与 FreePBX'
date = 2024-01-19T12:01:40+08:00
+++

## FreePBX
[FreePBX](https://www.freepbx.org/) 是一个基于 Asterisk 的 PBX. 基于 ISO镜像虚拟机安装方式进行测试.
在此测试 G 系列 FXS网关与 Asterisk 的兼容性.


## 创建分机
成功安装 PBX 环境后第一步在 PBX 创建分机, 如下图.
![](/GatewayPBX/img/freepbx/freepbx_add_pjsip_exten.png)
这里我们使用分机 1019, 1021.
FreePBX 的 sip 协议包含两种, 在全局设置中选择 chan_pjsip. 默认可能只开启了 UDP 监听, 如下图开启 TCP 监听.
![](/GatewayPBX/img/freepbx/freepbx_set_tcp_udp.png)

## 网关注册
### 配置 VOIPServer
FXS 网关完成基本的网络/时间配置后, 第一步就是创建编辑对应的 PBX 服务器信息. 如下图.
![](/GatewayPBX/img/freepbx/freepbx_edit_voipserver.png)
通常端口为 5060, 具体以 PBX 端开放监听的地址/端口为准.

### 端口配置分机
FXS 需要为每个端口配置分机, 然后在端口上连接电话线到模拟话机即可.
![](/GatewayPBX/img/freepbx/freepbx_edit_port.png)

## 拨打测试
模拟话机 1019 拨打 1021, 在状态页面能看见通话中的标识.
![](/GatewayPBX/img/freepbx/freepbx_call_status.png)

能正常的呼入/呼入,即与 freepbx 联合使用配置成功完成.