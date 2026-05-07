---
title: Computer Networks LLM Wiki
tags: [MOC, homepage, computer-networks]
wiki_type: moc
textbook: "Xie Xiren, Computer Networks, 8th ed. (2021)"
course: "Computer Networks Technology — NingboTech University"
---

# Computer Networks LLM Wiki

> **LLM Wiki — Karpathy Paradigm**  
> One concept, one entry. Relationships expressed as `[[wikilinks]]`.  
> Structured, navigable, iteratively maintainable.

This wiki was automatically distilled from **1,590 lecture slides** across
nine chapters of *Computer Networks* (8th ed.) by Xie Xiren,
with course materials generously provided by
**Associate Professor Yang Xingguang (杨星光)**.

---

## Chapter Map

| Chapter | Topic | Slides |
|---------|-------|--------|
| [[01-概述]] | Overview: Internet architecture, layered protocols, delay model | 149 |
| [[02-物理层]] | Physical Layer: Nyquist/Shannon, multiplexing | 85 |
| [[03-数据链路层]] | Data Link Layer: Ethernet, CSMA/CD, switches, VLAN | 151 |
| [[04-网络层]] | Network Layer: IP, subnetting, routing, ARP | 339 |
| [[05-运输层]] | Transport Layer: TCP/UDP, congestion control | 196 |
| [[06-应用层]] | Application Layer: DNS, HTTP, email, DHCP, SNMP, P2P | 280 |
| [[07-网络安全]] | Network Security: cryptography, TLS, IPSec, firewall | 120 |
| [[08-音视频服务]] | Multimedia Networking: RTP, VoIP, SIP, QoS | 108 |
| [[09-无线网络]] | Wireless & Mobile: WiFi, LTE, Mobile IP | 162 |

---

## Concept Index

### Transmission Mechanisms
[[分组交换]] · [[CSMA_CD|CSMA/CD]] · [[CSMA_CA|CSMA/CA]] · [[CRC循环冗余校验]]

### Addressing & Routing
[[IP地址与CIDR]] · [[子网划分]] · [[ARP地址解析协议]] · [[DNS解析流程]]

### Transport Layer
[[TCP三次握手]] · [[TCP拥塞控制]] · [[UDP协议]]

### Physical Layer
[[奈奎斯特定理与香农定理]] · [[CDMA码分复用]] · [[时延模型]]

### Security
[[TLS握手]] · [[OSI七层模型与TCP_IP]]

### Link Layer
[[以太网与MAC地址]]

### Mobile Networks
[[LTE网络架构]]

---

## Graph Legend (Obsidian Ctrl+G)

| Colour | Meaning |
|--------|---------|
| 🟦 Blue large node | Chapter entry page |
| 🟠 Orange node | Atomic concept entry |
| 🟩 Green node | This MOC root |
| ⬜ Grey stub | Referenced but not yet created |

---

## LLM Wiki Maintenance Principles

1. **Atomicity** — one concept per page, ≤ 200 lines for concept entries
2. **Link-driven** — all mentioned concepts marked with `[[]]`
3. **Source-traceable** — every entry has a `source:` frontmatter field
4. **Version-controlled** — Git history records every update
5. **LLM-iterable** — any entry can be handed to an LLM to extend

---

## Acknowledgements

Course slides and examination materials were kindly provided by
**Associate Professor Yang Xingguang (杨星光老师)**,
NingboTech University.
His generous contribution of high-quality teaching resources
is the foundation of this knowledge base.

---

*Generated: May 2026 · Textbook: Xie Xiren 8th ed. · Tool: Python + python-pptx + Claude*
