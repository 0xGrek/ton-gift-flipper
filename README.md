# TON Gift Flipper

> Multi-agent NFT trading system on TON blockchain — 115K LOC, 400+ parallel sessions, production 24/7.

<div align="left">

![Python](https://img.shields.io/badge/Python-1a1a1a?style=flat-square&logo=python&logoColor=cccccc)
![asyncio](https://img.shields.io/badge/asyncio-1a1a1a?style=flat-square&logoColor=cccccc)
![TON](https://img.shields.io/badge/TON-1a1a1a?style=flat-square&logo=ton&logoColor=cccccc)
![Pyrogram](https://img.shields.io/badge/Pyrogram-1a1a1a?style=flat-square&logoColor=cccccc)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-1a1a1a?style=flat-square&logo=postgresql&logoColor=cccccc)
![Redis](https://img.shields.io/badge/Redis-1a1a1a?style=flat-square&logo=redis&logoColor=cccccc)

</div>

---

## Overview

TON Gift Flipper is a production-grade, multi-agent NFT trading engine built on The Open Network (TON) blockchain. It runs 24/7, manages 400+ parallel Telegram sessions simultaneously, and integrates with 6 NFT marketplace APIs for real-time price discovery and execution.

Built entirely in Python with asyncio — no frameworks, no boilerplate. Every architectural decision was made under production constraints: latency, session stability, and capital efficiency.

---

## Architecture

```
HyperSniperOrchestrator
├── SessionManager        — 400+ Pyrogram sessions, rotating proxies
├── MarketplaceRouter     — 6 API integrations (GetGems, Fragment, ...)
├── PricingEngine         — dynamic repricing, spread calculation
├── ExecutionAgent        — buy/sell order dispatch, retry logic
├── BacktestFramework     — historical strategy validation
└── TelegramDashboard     — real-time P&L, session health monitoring
```

4 concurrent bot instances run independently with shared state through Redis. PostgreSQL persists trade history, session metadata, and pricing snapshots.

---

## Key Features

- **Multi-agent orchestration** — HyperSniperOrchestrator dispatches tasks across 4 independent bot instances
- **400+ parallel sessions** — Pyrogram-based session pool with health monitoring and auto-recovery
- **6 marketplace integrations** — unified API layer across TON NFT platforms
- **Dynamic repricing** — real-time spread recalculation based on market depth
- **Backtesting framework** — strategy validation against historical order flow
- **Telegram dashboard** — live P&L, session status, and error alerts

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.11+ |
| Async | asyncio, aiohttp |
| Telegram | Pyrogram |
| Blockchain | TON SDK, tonapi.io |
| Storage | PostgreSQL, Redis |
| Monitoring | Custom Telegram dashboard |
| Infrastructure | VPS, systemd services |

---

## Metrics

- **115,000 LOC** — total codebase
- **400+** parallel Pyrogram sessions
- **6** marketplace APIs integrated
- **4** concurrent bot instances
- **24/7** uptime, production since 2024

---

More at [0xgrek.com](https://0xgrek.com/projects/ton-gift-flipper)

---

*Private repository — architecture overview only.*
