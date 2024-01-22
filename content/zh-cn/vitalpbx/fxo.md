+++
title = 'FXO 与 VitalPBX'
date = 2024-01-21T14:01:40+08:00
+++

## VitalPBX
[VitalPBX](https://vitalpbx.com/) 是一个基于 Asterisk 的 PBX. 基于 ISO镜像虚拟机安装方式进行测试.
在此测试 G 系列 FXO 网关中继到 VitalPBX 的兼容性.

中继对接有账号认证模式和IP对接模式, 此处测试 IP 对接模式.

将 FXO 的电话线接口接入运营商提供的电话线上. 然后在 FXO 的新建中继(VitalPBX IP对接)注册.

## 创建中继
成功安装 PBX 环境后第一步在 PBX 创建中继(具体查看 VitalPBX 使用手册), 如下图.
![](/GatewayPBX/img/vitalpbx/vitalpbx_ip_trunk.png)
**这里采用 IP 注册模式**

配置呼入中继, 即寻找本机 1019 时通过呼入目的地转向 1019 分机.
![](/GatewayPBX/img/vitalpbx/vitalpbx_inbound.png)

## 网关注册
### 创建中继账号(分机号)
FXO 网关完成基本的网络/时间配置后, 根据**IP**创建中继信息. 如下图.
![](/GatewayPBX/img/vitalpbx/vital_trunk_edit.png)
通常端口为 5060, 具体以 PBX 端开放监听的地址/端口为准.
可以在 FXO 端查看到注册成功的信息.
![](/GatewayPBX/img/vitalpbx/vital_trunk_reg_ok.png)

### 端口配置中继和代拨号码
FXO 需要为每个端口配置中继, 当 FXO 线路电话呼入时,通过中继呼出. 当中继呼入时通过 FXO 线路呼出.
如下图选择中继并编辑代拨号码(即线路呼入时将拨打中继线路上的代拨号码).
![](/GatewayPBX/img/vitalpbx/vital_port_edit.png)
![](/GatewayPBX/img/vitalpbx/vital_port_edit_call_number.png)

这里的 1019 对应 VitalPBX 的呼入路由配置

## 拨打测试

能正常的呼入/呼入,即与 VitalPBX 联合使用配置成功完成.