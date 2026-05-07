---
title: TCP三次握手
tags: [TCP, 运输层, 连接管理]
aliases: [Three-Way Handshake, 三次握手]
source: 谢希仁《计算机网络》第8版 §5.7
wiki_type: concept
---

# TCP三次握手

TCP建立连接需要三次报文交换（三次握手），确保双方都具备收发能力，并同步初始序列号（ISN）。

## 流程

```
状态:     CLOSED                    LISTEN
          
步骤1:    ──── SYN(seq=x) ────────→
状态:     SYN_SENT                  SYN_RCVD

步骤2:    ←─── SYN+ACK(seq=y,ack=x+1) ────
状态:     ESTABLISHED               SYN_RCVD

步骤3:    ──── ACK(ack=y+1) ────────→
状态:     ESTABLISHED               ESTABLISHED
```

## 为什么需要三次而不是两次？

**关键原因**：防止旧的、失效的连接请求到达服务器，造成错误的连接建立。

场景：客户端发出SYN1（因网络延迟滞留），后来又发出SYN2并完成连接后关闭。SYN1此时到达服务器，若只需两次握手，服务器直接进入ESTABLISHED并等待数据，浪费资源。

三次握手中，服务器回复SYN1的SYN+ACK后，客户端**不会回应ACK**（因为知道这是旧连接），服务器超时后放弃。

## 初始序列号（ISN）

- 每次建立连接ISN不同（基于时钟），防止旧报文被误接收
- 现代实现用随机ISN加防重放

## SYN洪泛攻击

攻击者发大量SYN但不回ACK，使服务器消耗半连接资源。

防御：**SYN Cookie** — 服务器不分配资源，将状态编码到ISN，ACK到来时验证。

## 参见

- [[05-运输层]] — TCP连接管理完整介绍
- [[05-运输层|TCP四次挥手]] — 连接关闭过程
- [[TCP拥塞控制]] — 连接建立后的流量控制
