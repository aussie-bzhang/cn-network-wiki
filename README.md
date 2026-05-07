# Computer Networks LLM Wiki

> **Xie Xiren · Computer Networks (8th ed.)** — Karpathy LLM Wiki style knowledge base  
> Automatically distilled from 1,590 lecture slides across 9 chapters.  
> Dual-track visualisation: **Obsidian** (graph view) + **GitHub Pages** (web).

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deploy-blue)](https://aussie-bzhang.github.io/cn-network-wiki)
[![Obsidian](https://img.shields.io/badge/Obsidian-Open_Vault-purple)](https://obsidian.md)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

---

## Acknowledgements

This wiki was developed with the generous support of
**Dr. Yang Xingguang** (杨星光老师),
who kindly provided the complete set of course slide decks,
examination materials, and supplementary resources for the
*Computer Networks Technology* course at NingboTech University.
His contribution made it possible to build a comprehensive,
slide-faithful knowledge base covering all nine chapters of
Xie Xiren's 8th edition.

> *We sincerely thank Dr.Yang Xingguang for his openness
> in sharing high-quality teaching materials and for his
> collaborative spirit in supporting the development of this
> LLM Wiki.*

---

## Contents

| Chapter | Topic | Slides |
|---------|-------|--------|
| Ch. 1 | Overview: Internet architecture, layered protocols | 149 |
| Ch. 2 | Physical Layer: channel capacity, multiplexing | 85 |
| Ch. 3 | Data Link Layer: Ethernet, CSMA/CD, switches | 151 |
| Ch. 4 | Network Layer: IP, routing, ARP (largest chapter) | 339 |
| Ch. 5 | Transport Layer: TCP/UDP, congestion control | 196 |
| Ch. 6 | Application Layer: DNS, HTTP, email, DHCP, SNMP, P2P | 280 |
| Ch. 7 | Network Security: cryptography, TLS, IPSec | 120 |
| Ch. 8 | Multimedia Networking: RTP, VoIP, QoS | 108 |
| Ch. 9 | Wireless & Mobile Networks: WiFi, LTE, Mobile IP | 162 |

**Total: 9 chapters · 1,590 slides · 27 wiki entries · 204 wikilinks**

---

## Quick Start

### Option 1 — Obsidian (recommended for graph exploration)

```
1. Install Obsidian  →  https://obsidian.md
2. File → Open Vault → select this repository root
3. Open  00-MOC.md  as the entry point
4. Press  Ctrl+G  to open the graph view (pre-configured colours)
```

Graph colour legend:
- 🟦 **Blue** — chapter entry pages (9 nodes)
- 🟠 **Orange** — atomic concept entries (18 nodes)
- 🟩 **Green** — this MOC root

### Option 2 — GitHub Pages (no software required)

Visit: `https://aussie-bzhang.github.io/cn-network-wiki`

### Option 3 — Local MkDocs preview

```bash
pip install mkdocs mkdocs-material pymdown-extensions
mkdocs serve          # preview at http://127.0.0.1:8000
```

### Option 4 — Deploy to GitHub Pages

```bash
# Edit mkdocs.yml → set site_url to your GitHub Pages URL first
mkdocs gh-deploy      # builds and pushes to gh-pages branch
```

---

## Repository Structure

```
cn-network-wiki/
├── 00-MOC.md               ← Entry point (Map of Content)
├── README.md               ← This file
├── mkdocs.yml              ← GitHub Pages configuration
├── .obsidian/              ← Obsidian vault config (open box)
│   ├── app.json
│   ├── graph.json          ← Graph colour & physics settings
│   ├── workspace.json      ← Default layout: MOC + graph panel
│   └── core-plugins.json
├── wiki/                   ← All 27 entries (flat, no subfolders)
│   ├── 01-概述.md
│   ├── ...
│   ├── 09-无线网络.md
│   ├── TCP三次握手.md
│   ├── TLS握手.md
│   └── ...
└── docs/                   ← MkDocs mirror (auto-generated)
```

---

## LLM Wiki Quality Metrics

| Metric | Value | Target |
|--------|-------|--------|
| Broken-link rate | **0 %** | < 1 % |
| Mean link density | **7.6 links/entry** | > 5.0 |
| Source traceability | **100 %** | 100 % |
| Atomicity compliance | **94.4 %** | > 90 % |

---

## How to Extend the Wiki

To add a new atomic concept entry, paste the following prompt
into any LLM with the relevant slide text:

```
You are an LLM Wiki maintainer (Karpathy paradigm).
Generate an atomic wiki entry for concept: [CONCEPT NAME].
Constraint: ≤200 lines, wiki_type: concept.
Required sections:
  - YAML frontmatter (title, tags, aliases, source, wiki_type)
  - ## Definition (2 sentences max)
  - ## Mechanism (with table/code/diagram if applicable)
  - ## Comparison (vs nearest related concept)
  - ## See Also (3–5 [[wikilinks]])
Source slides: [PASTE RELEVANT SLIDE TEXT]
```

---

## Citation

If you use this wiki in research or teaching, please cite:

```bibtex
@misc{zhang2026cnwiki,
  author  = {Zhang, Bailing},
  title   = {Computer Networks {LLM} Wiki
             ({Xie} {Xiren} 8th ed.)},
  year    = {2026},
  url     = {https://github.com/aussie-bzhang/cn-network-wiki},
  note    = {Distilled from 1,590 course slides using
             the Karpathy LLM Wiki paradigm}
}
```

---

## Licence

Wiki content is released under
[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).
Original textbook copyright © Xie Xiren / Publishing House of
Electronics Industry. Course slide copyright © Yang Xingguang /
NingboTech University.
This wiki is a derivative educational resource for non-commercial use only.

---

*Built with Claude AI · LLM Wiki Pipeline · NingboTech University · 2026*
