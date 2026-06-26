<div align="center">

# 송병갑 · Byeong gab Song

**🌐 [English](README.md) · 한국어**

### Industrial AI & Data Engineer

**퀀트 금융 → 산업 AI.**
리스크 모델링의 엄밀함과 실시간 데이터 감각을 금융 시장에서 제조 현장으로 가져옵니다.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/gabsong)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sbg0700@gmail.com)

</div>

---

## 👋 About

> 완벽해 보이는 모델은 대체로 어딘가 새고 있다. 금융에서 배운 이 의심이 지금 일하는 방식의 기본이다.
 
크립토 헤지펀드와 VC에서 리서치·트레이딩을 했습니다. 프로젝트를 분석하고 포지션을 잡았고, 데스크에서 쓸 자동화 봇(실시간 알파 트래킹, 이상치·갭 탐지, 시그널 모니터링)을 직접 만들어 돌렸습니다. 리서치 보고서는 **300건** 이상 발행했습니다. 틀리면 바로 돈이 나가는 환경이라, 데이터가 새는지 의심하는 습관이 몸에 뱄습니다.
 
지금은 그 습관을 제조 현장으로 가져오고 있습니다. 실시간으로 데이터를 다루고, 비용을 최적화하고, 모델이 진짜 맞는지 끝까지 의심합니다. — 제조 ML, 에너지 최적화, 에이전틱 파이프라인, 그리고 실제로 배포되는 시스템까지.
 
모델에 많은 Negative를 적용시키기 전까진 믿지 않습니다.

## 🔧 What I build

- **산업 AI** — 결함 탐지, 예측 품질, 에너지·비용 최적화, 리스크 스코어링
- **데이터 엔지니어링** — 수집부터 서빙까지의 파이프라인, 온프레미스 & 클라우드, 감사 가능한 lineage
- **에이전틱 & 실시간 AI** — MCP 에이전트, 로컬/폐쇄망 LLM, 스트리밍 이상 탐지

## 🚀 Featured Projects

### [GYEOL](https://github.com/sbg0700/mfg-mcp) — 제조 데이터 전처리 온프레미스 AI 에이전트
MCP + 로컬 LLM, 완전 **폐쇄망**, **감사 대응**(IATF 16949 / 21 CFR Part 11). AI가 *계획*하고, 결정론 코드가 *실행*하며, 사람이 *승인*합니다.
- 프로젝트 스켈레톤과 엔드투엔드 에이전틱 플로우 골격 설계(Inspector → Planner → Executor → Validator)
- React 6단계 파이프라인 UI 구축, 트러블슈팅 리드, 제한 스펙(8GB VRAM) LLM 벤치마킹

### [PaintGuard](https://github.com/sbg0700/paintguard) — 자동차 도장공정 듀얼 트랙 ML + 4-Layer MES &nbsp;·&nbsp; [🌐 Live](https://paintguard.argos-i.com)
비전 + 정형 ML을 리스크 스코어로 통합해 AWS에 배포된 **4-Layer MES**로 제공. ML 스택 전체와 React 대시보드를 직접 구축.
- **YOLOv11s** 결함 탐지 — Recall **0.9975**, mAP@0.5 **0.9875** (안전 중요 검사를 위한 Recall 우선)
- **타깃 누수** 적발(가짜 AUC 1.0) 후 정직한 **0.556** 보고 — 정형 데이터만으론 실패 예측 불가임을 입증, 비전 트랙의 근거 마련
- **100점 리스크 스코어**로 251건 탐지를 CRITICAL → LOW로 등급화

### PeakShield — 철강 공정 에너지·탄소 최적화 (ML)
12개월 철강 공정 시계열에서 **역률(PF)** 과 **피크 부하**를 최적화해 전기료와 CO₂를 절감 — surrogate 모델 + optimizer + ROI 루프.
- 본인 역할: **피처 엔지니어링, 모델 최적화, 백엔드 / DB**
- 결과: 연간 CO₂e **−18.5%** · **₩4.41M** 절감 · 최대 피크 **660 → 590 kW**
- Team MaD Fairies (3인)

### SURGENT &nbsp;·&nbsp; 🚧 진행 중 (private) — 실시간 스트리밍 이상 탐지
**Transformer 기반** 탐지 시스템 — 데스크에서 만든 트레이딩 봇(서지·갭·이상 탐지)을 범용 실시간 파이프라인으로 발전시키는 중. *1차(Transformer 모델링) 완료.*

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

### (주)퍼스트소울코리아 (1st Soul Ventures) — Research & Trading &nbsp;·&nbsp; 2025.03 – 2025.08
*크립토 헤지펀드 & VC (AUM $10M+).*
- 상장 토큰 밸류에이션(FDV/MC, 토크노믹스, 투자자 구조, vesting) 종합 리서치 → 전략 기획 및 포지션 익스큐션, VC 타입 리서치 보고서 **30건+** 발행
- 온체인·파생 지표(OI, Funding Rate, Liquidation Map, Whale Flow) 해석 및 트레이딩 전략 적용
- **Python 자동화 봇**(Long/Short Signal Bot, Alpha Tracker, CME Gap Detector) 기획·개발 — 실시간 알파 종목 모니터링
- 헤지펀드 롱/숏 포지션 조정에 직접 기여

### 히포케이메논 — 투자정보파트 선임연구원 &nbsp;·&nbsp; 2022.01 – 2024.09
- 블록체인·자본시장 리서치, 공시자료·시장 데이터 통계 분석을 통한 투자 기회 발굴 및 의사결정 지원
- 데일리·주간·월간 시장 동향 보고서 **300건+** 작성
- 투자·경제 콘텐츠 채널 운영(유튜브 + 텔레그램, 구독자 **2.7만 / 5천**), 브랜딩·신뢰도 구축
- 금융 데이터 가공·시각화(Excel, Google 플랫폼), OKR 기반 목표 설정

## 🎓 Education & Certifications

- 🎓 **경영학 학사**, 동국대학교
- 🧪 **삼성 AXI K-Digital Training**(AI & 데이터) · **Schneider Electric Academy**(반도체/배터리 산업 솔루션) · **Build with AI Seoul 2026**(with Google DeepMind)
- 📜 ADsP · 빅데이터분석기사(필기) · 투자자산운용사

---

<div align="center">

**Data Engineering · Industrial AI 포지션을 찾고 있습니다 — 미국 & 한국.**

[LinkedIn](https://linkedin.com/in/gabsong) · sbg0700@gmail.com

</div>
