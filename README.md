<div align="center">

# Byeonggab Song · 송병갑

**🌐 English · [한국어](README.ko.md)**

### Blockchain Researcher · Product Builder

**Crypto research & trading desk → AI bootcamp → shipping products.**
I read how assets move (on-chain flows, order books, unlock schedules) and build the tools that act on it.

[![Portfolio](https://img.shields.io/badge/Portfolio-Notion-000000?style=for-the-badge&logo=notion&logoColor=white)](https://wry-willow-738.notion.site/389ed79dd39680c59e03e9dc8e6b2ff2)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/gabsong)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sbg0700@gmail.com)

</div>

---

## 👋 About

> A model that looks perfect is usually leaking somewhere. Markets taught me that suspicion, and it's how I work now.

I started in crypto: a senior researcher at a digital-asset investment-information company (300+ market reports, a 27K-subscriber YouTube channel), then the Research & Trading Desk of a crypto hedge fund, where I wrote 28 pre-listing token reports, made long/short calls, and built the Python bots the desk actually ran on: wallet inflow/outflow alerts, FDV sorting, signal and gap detection.

I wanted to build the tools myself, so I went through an AI bootcamp. Since then I've shipped a real-time token screener that is live today, a human-in-the-loop data pipeline that won the bootcamp's final-project grand prize, and the infrastructure for a hackathon team that won a Minister of Employment and Labor Award.

I don't trust a model until I've tried to break it. Bots screen and alert; people decide.

## 🔧 What I build

- **Market & on-chain tooling** — real-time screeners, wallet-flow alerts, token research templates, pre-registered out-of-sample validation
- **Human-in-the-loop AI** — MCP agents and local LLMs that propose, deterministic code that executes, a person who approves, lineage for every change
- **Infrastructure that ships** — Docker Compose packaging, GitHub Actions CI with security scanning, reproducible deploys

## 🚀 Featured Projects

### SURGENT · 🚧 In production (private) — Pump-proximity token screener
Watches all **727** Binance perpetual symbols (527 crypto + 200 traditional-asset-linked) over 15-minute WebSocket streams. When a symbol breaks **+25%** from the daily open, it vectorizes that symbol's previous 24 h, compares it against every other symbol, and sends the top five to Telegram with an **energy score** (recent candle range, 24 h max rise, funding rate, ranked across the universe). No order execution; the decision is human.
- First hypothesis (cosine similarity to the pump pattern) failed out of sample: a learned feature-weighting model scored **test AUC 0.46**. Comparing followers vs non-followers on raw values showed the signal was in the *pre-pump state*, not the chart shape
- **Pre-registered sealed-data tests**: energy-ranked top-5 beat cosine-ranked **91 of 103** triggers in August (+6.80% vs +2.53%, 4 h high-touch basis, not held P&L) and **80 of 88** in September. Live logs reproduce 100% from exchange raw data
- asyncio WebSocket ingest with auto-reconnect and REST backfill, restart-safe duplicate-alert suppression, SQLite scoring (1 h / 4 h / 24 h)

### [GYEOL](https://github.com/sbg0700/mfg-mcp) — Human-approved data preprocessing with on-prem AI agents · 🏆 Grand prize, Samsung AXI bootcamp final (Jun 2026)
MCP + a local LLM for factory data that can't leave the plant. The AI *proposes* within code-defined rules, a human *approves*, deterministic code *executes and validates*, and every change is recorded as lineage.
- Designed the project skeleton, the end-to-end agentic flow (Inspector → Planner → human approval → Executor → Validator), the approval gate, lineage and schema validation, and the React 6-stage pipeline UI
- Fixed an approval loop: approvals were keyed to step order, which the LLM reshuffled on every plan; re-keyed them to a fixed `task type + target column` identifier
- Ran end to end on **32 public manufacturing datasets (KAMP, ~5 GB)**, **94 automated tests** passing; in the demo, removing 22 approved cycle-time outliers restored a predictive model to **R² 0.9965** on an 8 GB VRAM server

### [MoGuk](https://github.com/sbg0700/MoGuk) — Hackathon infrastructure · 🏆 8th K-Digital Training Hackathon, Minister of Employment and Labor Award (326 teams)
Multilingual safety-communication platform for foreign workers at small manufacturers. I owned deployment and operations for a 4-person team.
- Packaged LLM, DB, API and web server as one **Docker Compose** bundle with GPU settings in a separate file and feature settings as environment variables, so the same package moved from a CPU server (LLM >25 s) to a GPU server (**2–3 s**) without code changes
- **GitHub Actions** two-stage CI (static checks + **Trivy** security scan) that blocked **3 HIGH** vulnerabilities before merge; HTTPS and admin-path IP allowlist via **Caddy**, least-privilege IAM, DB backup/restore verified
- Reviewed teammates' PRs for infra impact, batched 21 pre-finals merges into two announced redeploys (**7 min** each); zero incidents across two demo days

### [PaintGuard](https://github.com/sbg0700/paintguard) — Automotive paint defect prediction: the perfect score was a leak
Team project; I owned modeling.
- First LightGBM model hit **AUC 1.0**. Feature importance exposed **5 post-inspection features**; removing them and re-validating on a time-ordered split gave an honest **0.556**
- Days before the deadline, told the team retraining was needed, agreed the inspection data couldn't predict failure, and switched to surface-image detection: **YOLOv11s, mAP@0.5:0.95 = 0.8656**
- Presented the collapse and the pivot as-is; the time-ordered validation rule carried over into SURGENT

### [PeakShield](https://github.com/sbg0700/PeakShield) — Steel-process power optimization, re-targeted to electricity cost
First bootcamp team project (Team MaD Fairies). The team planned to judge improvements by power factor and peak reduction; I proposed **electricity cost** as the single objective and built it.
- KEPCO tariff-based **cost & ROI engine** (seasonal/time-of-use rates, power-factor penalties), the cost target feature the optimizer adopted, and a **Flask dashboard** with a digital-twin tab where clicking a process area adjusts its nodes
- Result presented: peak demand **629 → 531 kW (−15%)**, power-factor-penalty intervals **−6%**. Modeling (XGBoost/Optuna) by a teammate

## 🛠️ Tech Stack

**ML & Data Science**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-02569B?style=for-the-badge)
![XGBoost](https://img.shields.io/badge/XGBoost-337AB7?style=for-the-badge)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![SHAP](https://img.shields.io/badge/SHAP-FF4B4B?style=for-the-badge)

**Computer Vision · LLM & Agents**

![Ultralytics YOLOv11](https://img.shields.io/badge/Ultralytics_YOLOv11-111F68?style=for-the-badge)
![MCP](https://img.shields.io/badge/MCP-000000?style=for-the-badge)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)
![Gemma](https://img.shields.io/badge/Gemma-4285F4?style=for-the-badge&logo=google&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)

**Market & On-chain Data**

![Binance WS/REST](https://img.shields.io/badge/Binance_WS%2FREST-F0B90B?style=for-the-badge&logo=binance&logoColor=black)
![Telegram Bot](https://img.shields.io/badge/Telegram_Bot-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Nansen · Solscan · DexScreener](https://img.shields.io/badge/Nansen_·_Solscan_·_DexScreener-1F3864?style=for-the-badge)

**Data · Infra**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Parquet](https://img.shields.io/badge/Parquet-50ABF1?style=for-the-badge)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Trivy](https://img.shields.io/badge/Trivy-1904DA?style=for-the-badge&logo=aquasecurity&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=for-the-badge&logo=caddy&logoColor=white)

**Frontend**

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

## 💼 Experience

### First SouL Korea Inc. (1st Soul Ventures) — Research & Trading Desk Intern · Mar 2025 – Aug 2025
*Crypto hedge fund & VC founded by traditional-finance members.*
- Rotated through weekly research and day/night market monitoring; researched pre-listing tokens (FDV/MC valuation, investor tiers, tokenomics, vesting) and wrote **28 research reports** in a fixed format (FDV, float, lock-ups, next unlock date) that the desk adopted as its standard
- Made **long/short calls** on OI, funding rate, liquidation maps and whale flow (entry, exit and fund execution were handled by the CEO)
- Built the desk's **Python bots**: a wallet inflow/outflow alert bot (Telegram alerts when transfers exceed a float-based threshold, applied to $BAN and $ORCA; traced a split-and-regather flow in $BAN at the transaction level), FDV sorting, Long/Short Signal Bot, Alpha Tracker, CME Gap Detector, SurgePlunge. Research time per token fell from ~2 h to ~30 min
- Reviewed a **Falcon Finance** whitelist boost deal on asset-protection terms (USDf issuance, OCR buffer and delta-neutral hedge, liquidation conditions, sUSDf restaking and NFT lock-up); the review fed the firm's investment decision

### Hypokeimenon — Senior Researcher, Investment Information · Jan 2022 – Sep 2024
*Digital-asset market commentary via YouTube and Telegram.*
- Blockchain and capital-market research: project analysis (mainnet, float, price action) to surface opportunities and support decisions
- Authored **300+** daily / weekly / monthly market reports; published 5+ pieces a week
- Ran the company's channels (YouTube **3K → 27K**, Telegram **5.6K**), handling subscriber Q&A, feedback and in-channel product sales
- Earned the Certified Investment Manager license while employed, to explain digital assets in regulated-finance terms

## 🎓 Education & Certifications

- 🎓 **B.A. in Business Administration**, Dongguk University(DUICA)
- 🧪 **Samsung AXI K-Digital Training** (two tracks, Sep 2025 – Jun 2026) · **Schneider Electric Academy** (semiconductor / battery industrial solutions) · **Build with AI Seoul 2026** (with Google DeepMind)
- 📜 Certified Investment Manager · Investment Solicitor (KOFIA) · ADsP · Engineer Big Data Analysis (written)

---

<div align="center">

**Open to product and engineering roles in blockchain finance and applied AI — Korea & US.**

[Portfolio](https://wry-willow-738.notion.site/389ed79dd39680c59e03e9dc8e6b2ff2) · [LinkedIn](https://linkedin.com/in/gabsong) · sbg0700@gmail.com

</div>
