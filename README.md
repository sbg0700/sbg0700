<div align="center">

# Byeonggab Song · 송병갑

**🌐 English · [한국어](README.ko.md)**

### Industrial AI & Data Engineer

**Quantitative finance → industrial AI.**
I bring risk-modeling rigor and real-time data instincts from financial markets to the factory floor.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/gabsong)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sbg0700@gmail.com)

</div>

---

## 👋 About

> A model that looks perfect is usually leaking somewhere. Finance taught me that suspicion, and it's how I work now.

I came up in crypto-finance — research and trading at a hedge fund and VC, where I analyzed projects, took positions, and built the Python bots my desk actually ran on: real-time alpha tracking, anomaly and gap detection, signal monitoring. I wrote **300+** research reports along the way. When being wrong costs you money, you learn to distrust data that looks too clean.

I bring that same habit to the factory floor now — working with real-time data, optimizing for cost, and pushing on a model until I'm sure it actually holds. Manufacturing ML, energy optimization, agentic pipelines, and systems that actually ship.

I don't trust a model until I've tried to break it.

## 🔧 What I build

- **Industrial AI** — defect detection, predictive quality, energy & cost optimization, risk scoring
- **Data Engineering** — ingestion-to-serving pipelines, on-prem & cloud, with audit-ready lineage
- **Agentic & real-time AI** — MCP agents, local / air-gapped LLMs, streaming anomaly detection

## 🚀 Featured Projects

### [GYEOL](https://github.com/sbg0700/mfg-mcp) — On-prem AI agents for manufacturing data preprocessing
MCP + a local LLM, fully **air-gapped** and **audit-ready** (IATF 16949 / 21 CFR Part 11). The AI writes the *plan*, deterministic code *executes* it, and a human *approves*.
- Designed the project skeleton and the end-to-end agentic-flow backbone (Inspector → Planner → Executor → Validator)
- Built the React 6-stage pipeline UI; led troubleshooting and limited-spec (8 GB VRAM) LLM benchmarking

### [PaintGuard](https://github.com/sbg0700/paintguard) — Dual-track ML + 4-Layer MES for automotive paint shops &nbsp;·&nbsp; [🌐 Live](https://paintguard.argos-i.com)
Vision + structured ML fused into a risk score, served through a **deployed 4-Layer MES** on AWS. I built the entire ML stack and the React dashboard.
- **YOLOv11s** defect detector — Recall **0.9975**, mAP@0.5 **0.9875** (recall-first for safety-critical inspection)
- Caught **target leakage** (a fake AUC 1.0) and reported the honest **0.556** — proving structured data alone can't predict failure, which justified the vision track
- **100-point risk score** ranking 251 detections from CRITICAL → LOW for the factory floor

### PeakShield — ML-driven energy & carbon optimization for steel processes
Cut electricity cost and CO₂ by optimizing **power factor** and **peak load** over 12 months of steel-process time-series — a surrogate model + optimizer + ROI loop.
- My role: **feature engineering, model optimization, backend / DB**
- Results: **−18.5%** annual CO₂e · **₩4.41M** cost saving · peak demand **660 → 590 kW**
- Team MaD Fairies (3-person)

### SURGENT &nbsp;·&nbsp; 🚧 Ongoing (private) — Real-time streaming anomaly detection
A **Transformer-based** detection system — the evolution of the trading-desk bots I built (surge / gap / anomaly detection) into a general real-time pipeline. *Phase 1 (Transformer modeling) complete.*

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

**Data · Infra**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?style=for-the-badge&logo=duckdb&logoColor=black)
![Parquet](https://img.shields.io/badge/Parquet-50ABF1?style=for-the-badge)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

**Frontend**

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

## 💼 Experience

### First SouL Korea Inc. (1st Soul Ventures) — Research & Trading &nbsp;·&nbsp; Mar 2025 – Aug 2025
*Crypto hedge fund & VC (AUM $10M+).*
- Researched token valuations (FDV/MC, tokenomics, investor structure, vesting) → strategy planning and position execution; published **30+** VC-grade research reports
- Interpreted on-chain & derivatives signals (OI, funding rate, liquidation maps, whale flow) and applied them to trading strategy
- Designed and built **Python automation bots** — Long/Short Signal Bot, Alpha Tracker, CME Gap Detector — for real-time alpha monitoring
- Contributed directly to hedge-fund long/short position adjustments

### Hypokeimenon — Senior Researcher, Investment Information &nbsp;·&nbsp; Jan 2022 – Sep 2024
- Blockchain & capital-market research; statistical analysis of disclosures and market data to surface opportunities and support decisions
- Authored **300+** daily / weekly / monthly market reports
- Ran investment content channels (YouTube + Telegram, **27K / 5K** subscribers), building brand and credibility
- Financial data processing & visualization (Excel, Google tools); OKR-based goal setting

## 🎓 Education & Certifications

- 🎓 **B.A. in Business Administration**, Dongguk University
- 🧪 **Samsung AXI K-Digital Training** (AI & Data) · **Schneider Electric Academy** (semiconductor / battery industrial solutions) · **Build with AI Seoul 2026** (with Google DeepMind)
- 📜 ADsP · Engineer Big Data Analysis (written) · Certified Investment Manager (투자자산운용사)

---

<div align="center">

**Open to Data Engineering & Industrial AI roles — US & Korea.**

[LinkedIn](https://linkedin.com/in/gabsong) · sbg0700@gmail.com

</div>
