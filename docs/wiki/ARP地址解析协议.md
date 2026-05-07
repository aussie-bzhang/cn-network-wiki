---
title: ARP地址解析协议
tags: [网络层, ARP, 地址解析]
aliases: [Address Resolution Protocol, 地址解析协议]
source: 谢希仁《计算机网络》第8版 §4.2.4
wiki_type: concept
---

# ARP（地址解析协议）

## 作用

ARP解决的问题：**已知目的主机的IP地址，如何找到其MAC地址**，以便在同一局域网内封装以太网帧。

## 工作流程

```
主机A想向同网段主机B（IP: 209.0.0.6）发包：

1. A查自己的ARP缓存（ARP Table）
   → 若有B的MAC地址，直接使用

2. 若无，A广播ARP请求（目的MAC: FF-FF-FF-FF-FF-FF）：
   "谁是 209.0.0.6？我是 A（IP: x.x.x.x, MAC: aa:bb:cc:dd:ee:ff）"

3. 同网段所有主机收到广播，只有B回应：
   B单播回复ARP应答给A："我是209.0.0.6，MAC是 xx:xx:xx:xx:xx:xx"

4. A将B的 IP→MAC 映射存入ARP缓存（有生存期，约几分钟）
```

## ARP报文格式

ARP报文直接封装在以太网帧中（Type字段 = 0x0806）：

```
硬件类型(2B) | 协议类型(2B) | 硬件长度(1B) | 协议长度(1B) | 操作码(2B)
发送方MAC(6B) | 发送方IP(4B) | 目的MAC(6B) | 目的IP(4B)
```

操作码：1=ARP请求，2=ARP回答，3=RARP请求，4=RARP回答

## 跨网络通信中的ARP

> **关键认识**：跨路由器通信时，主机不会去找最终目的主机的MAC，而是找**默认网关（路由器接口）的MAC**。

```
主机A（192.168.1.10）→ 路由器（192.168.1.1）→ ... → 目的主机B
         ARP找路由器192.168.1.1的MAC↗
```

每跳路由器都会重新做ARP，找下一跳的MAC地址。

## 代理ARP（Proxy ARP）

路由器可以代替目的主机回答ARP请求，使不同子网的主机认为对方在同一子网。

## ARP欺骗（ARP Spoofing）

ARP协议无认证机制，攻击者可发送虚假ARP回答，将流量重定向：
- 中间人攻击（Man-in-the-Middle）
- DoS攻击（将网关MAC改为不存在的地址）

防御：静态ARP绑定、DAI（Dynamic ARP Inspection）。

## RARP（逆地址解析）

已知MAC地址，求IP地址。已被**DHCP**替代。

## 参见

- [[04-网络层]] — IP协议体系
- [[IP地址与CIDR]] — IP地址结构
- [[以太网与MAC地址]] — MAC地址格式
- [[06-应用层]] — DHCP替代RARP的方案
