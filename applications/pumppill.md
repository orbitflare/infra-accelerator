# OrbitFlare Infra Accelerator - Application

## 1. Project Overview

### Project Name

PumpPill

### Tagline

Real-time Solana token intelligence platform — funder analytics, bundle detection, and scam network mapping for PumpFun tokens.

### Description

PumpPill is a Solana token intelligence platform that evaluates new PumpFun token launches in real-time. Our core engine analyzes the funding chains behind every token launch — who funded the deployer, what their historical success rate is, whether they're connected to known rug networks, and how coordinated the early buyer structure looks.

We serve traders through a live dashboard (pumppill.org) and a Telegram bot that provides instant token scans. Under the hood, we maintain a proprietary scam network graph, bundle coordination detection system, and funder wallet scoring engine that tracks deployer outcomes across thousands of launches.

Our system currently detects new token launches via Helius webhooks. With OrbitFlare ShredStream, we can reduce detection latency from hundreds of milliseconds to sub-100ms — a meaningful edge for time-sensitive trading decisions.

### Category

- [x] Data / Analytics
- [x] Infrastructure
- [x] DeFi

### Links

| Resource | Link |
|---|---|
| Website | https://pumppill.org |
| GitHub Repository | Private — available for review on request |
| Demo / Prototype | https://pumppill.org (live production) |
| Telegram Bot | https://t.me/PumpPillBot |

---

## 2. Team

### Team Members

| Name | Role | GitHub | LinkedIn | Relevant Experience |
|---|---|---|---|---|
| Kyle (JackedBasedMgr) | Founder / Nerd | @JackedBasedMgr | - | Solana trading infrastructure, data pipelines, real-time systems |

### Team Location(s)

United States (Eastern Time, UTC-4)

### Time Commitment

Full-time dedication to the 4-week program. PumpPill is the primary project.

### Prior Work

- PumpPill V1 and V2 (current) — live production system serving active Solana traders daily
- Built proprietary bundle detection engine analyzing coordination patterns in PumpFun launches
- Scam network graph mapping thousands of flagged wallets with cross-referenced funder chains
- Telegram bot with real-time token scans, scam detection, and community intelligence features

---

## 3. Technical Details

### Architecture Overview

PumpPill runs a Python/FastAPI backend with a Next.js frontend, backed by PostgreSQL. The system operates four intelligence pillars:

1. **Signal Engine** — Multi-factor scoring using funder intelligence, bundle safety analysis, and independent buyer confirmation
2. **Bundle Intelligence** — Real-time coordination detection analyzing early buyer patterns, funding chains, and launch structure
3. **Scam Detection** — Network graph of flagged wallets, cross-referencing funder chains with price-confirmed rug post-mortems
4. **Trading Engine** — Signal detection with execution capability via Jito bundles, including post-trade risk management

The detection pipeline currently uses Helius webhooks to monitor tracked wallets. Signals pass through an intelligence gate before any action is taken. ShredStream integration would replace the detection layer for faster signal generation.

### Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 15, React, TypeScript, Tailwind CSS |
| Backend | Python 3.12, FastAPI, asyncio |
| Database | PostgreSQL (Supabase) |
| On-chain | Helius RPC + Webhooks, Jito Bundles |
| Execution | solders (Rust bindings), Jito bundle submission |

### Smart Contracts / Programs

PumpPill does not deploy its own on-chain programs. We interact with:
- PumpFun bonding curve program — read curve state, analyze launches
- Jito tip program — MEV-protected transaction submission
- Token Program / Token2022 — token transfers and balance checks

### Repository Structure

Private repository. Monorepo containing backend API, frontend dashboard, background services, and database migrations. Available for review under NDA if needed.

---

## 4. Current Status

### Development Stage

- [x] Other (describe)

**Live production system.** PumpPill is deployed and serving users today on Solana mainnet. We are not pre-launch — we are optimizing a running system.

### What Works Today

1. **Dashboard (pumppill.org):** Paste any Solana contract address and get an instant scan — bundle analysis, funder intelligence, scam network connections, signal strength rating
2. **Telegram Bot (@PumpPillBot):** Real-time token scanning in Telegram groups with multiple intelligence actions
3. **Signal Alerts:** Real-time alerts to Telegram channels when notable tokens are detected
4. **Detection System:** Monitoring tracked funder wallets via Helius webhooks, with intelligence-gated signal processing
5. **Bundle Scanner:** Proprietary coordination detection — analyzes early buyers, funding chains, and launch structure
6. **Scam Network Graph:** Thousands of flagged wallets cross-referenced across launches

### Known Limitations

1. **Detection latency:** Currently hundreds of milliseconds via Helius webhooks. ShredStream would provide sub-100ms detection.
2. **Entry timing:** Faster detection directly translates to better entry positioning on the bonding curve — meaningful price improvement on every trade.
3. **No gRPC streaming:** Webhook delivery has variable latency and occasional gaps. A persistent gRPC connection would be more reliable.
4. **Transaction optimization:** Jito bundle construction and priority fee estimation could be improved with infrastructure expertise.

### Devnet Deployment

PumpPill operates on Solana mainnet. No devnet deployment — we're a live analytics and trading platform.

- **Production:** https://pumppill.org

---

## 5. Path to Mainnet

### Mainnet Blockers

We are already on mainnet. The blockers below are for **detection speed and execution optimization**, which is the focus of this accelerator application.

| Blocker | Severity (High/Medium/Low) | Estimated Effort |
|---|---|---|
| Detection latency via webhooks — need sub-100ms via ShredStream | High | 2 weeks integration |
| Transaction construction not optimized for slot inclusion rate | Medium | 1 week with advisory |
| No persistent gRPC connection for reliable real-time monitoring | Medium | 1 week integration |
| Priority fee estimation could be more dynamic | Low | 3 days |

### Proposed Milestones

| Week | Milestone | Deliverable |
|---|---|---|
| 1 | ShredStream integration: connect gRPC, parse PumpFun Create/Buy instructions from shreds | Working ShredStream client detecting token creation events at sub-100ms |
| 2 | Pipeline integration: route ShredStream detections through existing intelligence gate and execution pipeline | End-to-end flow: ShredStream detect, filter, execute — with measured latency |
| 3 | Transaction optimization: improve Jito bundle construction, priority fees, and slot inclusion rate with OrbitFlare advisory | Measurable improvement in tx confirmation rate and execution speed |
| 4 | Production validation: mainnet pilot comparing ShredStream vs webhook detection | Performance report: latency improvement, entry price delta, reliability comparison |

### Infrastructure Needs

- **Transaction volume:** Moderate — hundreds of detection signals/day, selective execution
- **WebSocket subscriptions:** Yes — monitoring tracked wallet sets for real-time transaction detection
- **gRPC streaming (ShredStream):** Yes — PumpFun instruction detection from raw turbine shreds for sub-100ms alerts
- **Key RPC methods:** `getMultipleAccounts`, `getSignaturesForAddress`, `getTransaction`, `sendTransaction`
- **Geographic requirements:** US East preferred, with Frankfurt/Tokyo endpoints useful for latency comparison

---

## 6. Ecosystem Fit

### Target Users

1. **Solana meme coin traders** — thousands active daily on PumpFun, need intelligence to avoid scams and find quality launches
2. **Alpha groups / Telegram communities** — our bot provides group intelligence, scanning tokens in real-time
3. **Traders who want data-driven decisions** — our intelligence layer surfaces what raw price charts can't show

PumpFun processes tens of thousands of token launches per day. The total addressable market is every active Solana trader evaluating new tokens.

### Problem Evidence

- The vast majority of PumpFun tokens rug or die — traders need tools to identify the minority that survive
- Bundle coordination (insider buying) is widespread and invisible to retail traders without specialized analysis
- Existing tools show price and volume but not the funding chain analysis that reveals who's behind the launch
- Our internal data across thousands of tokens demonstrates that funder intelligence significantly improves trading outcomes compared to blind entry

### Competitive Landscape

| Project | How We Differ |
|---|---|
| BullX / Photon | Trading terminals focused on execution speed. No funder intelligence, no scam graph, no bundle analysis. |
| GMGN | Copy-trade focused. Tracks whale wallets but doesn't analyze the funding chain or bundle structure behind launches. |
| RugCheck | Static safety scores. Doesn't track funder wallets across launches or build a network graph of connected ruggers. |
| Birdeye / DexScreener | Price/volume analytics. No intelligence layer — they show what happened, not who's behind it. |

### Ecosystem Contribution

1. **Scam reduction:** Our scam network graph and bundle detection help traders avoid rug pulls, building trust in the Solana ecosystem
2. **Transparency:** Making funder chains and bundle coordination visible to retail traders levels the playing field
3. **ShredStream showcase:** A live production system powered by OrbitFlare infrastructure is compelling proof of ShredStream's value to builders

---

## 7. Post-Program Plans

### Sustainability

PumpPill sustains itself through:
1. **Premium membership tiers** (in development) — advanced signals, automation features, and priority intelligence
2. **Trading revenue:** Intelligence-driven trading generates direct returns
3. **Bot-as-a-service:** Telegram bot deployed to external trading groups as a growth engine

Infrastructure costs are managed and modest. Revenue from memberships and trading covers ongoing costs.

### Roadmap

| Timeline | Milestone |
|---|---|
| Month 1-2 | ShredStream integration live, detection optimization |
| Month 2-3 | Premium membership launch, advanced automation features |
| Month 3-4 | Telegram bot expansion, community growth, referral program |
| Month 4-6 | API access for third-party integrations |

### Continued Infrastructure

Yes. OrbitFlare infrastructure is core to our detection advantage — faster detection directly translates to better positioning. We plan to maintain a persistent ShredStream connection and scale usage as our subscriber base grows.

---

## 8. Additional Information

### How did you hear about the OrbitFlare Infra Accelerator?

Research into ShredStream infrastructure for detection optimization. OrbitFlare's sub-100ms detection capability is the specific missing piece in our architecture — we have the intelligence layer, we need the speed layer.

### Previous Accelerators or Grants

None. PumpPill is self-funded and bootstrapped.

### Anything Else

PumpPill is not a concept or prototype. It's a live production system with real users, real data, and months of tracked outcomes. The ShredStream integration is a detection layer upgrade to an already battle-tested intelligence engine — not a ground-up build.

We're particularly interested in exploring a deeper infrastructure partnership beyond the accelerator — our intelligence layer combined with OrbitFlare's speed layer creates a unique edge that benefits both sides. We've prepared a detailed proposal outlining the specifics and would be happy to walk through it on a call.
