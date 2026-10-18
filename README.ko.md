<div align="center">

# 송병갑 · Byeonggab Song

**🌐 [English](README.md) · 한국어**

### Blockchain Researcher · Product Builder

**크립토 리서치·트레이딩 데스크 → AI 부트캠프 → 프로덕트 구현.**
자산이 어떻게 움직이는지(온체인 흐름, 호가, 언락 일정)를 읽고, 그 판단에 쓰는 도구를 직접 만듭니다.

[![Portfolio](https://img.shields.io/badge/Portfolio-Notion-000000?style=for-the-badge&logo=notion&logoColor=white)](https://wry-willow-738.notion.site/389ed79dd39680c59e03e9dc8e6b2ff2)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/gabsong)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sbg0700@gmail.com)

</div>

---

## 👋 About

> 완벽해 보이는 모델은 대체로 어딘가 새고 있다. 시장에서 배운 이 의심이 지금 일하는 방식의 기본이다.

크립토에서 시작했습니다. 디지털자산 투자정보 회사의 선임 연구원으로 시장 동향 보고서 300건 이상을 쓰고 구독자 2.7만 유튜브 채널을 운영했고, 이어 크립토 헤지펀드 Research & Trading Desk에서 상장 예정 토큰 리포트 28건을 쓰고 롱/숏 콜을 내면서 데스크가 실제로 쓰는 Python 봇(지갑 입출금 알림, FDV 정렬, 시그널·갭 탐지)을 만들었습니다.

도구를 직접 만들고 싶어 AI 부트캠프를 거쳤습니다. 그 뒤로 지금 운영 중인 실시간 토큰 스크리너와 부트캠프 최종 프로젝트 대상을 받은 사람의 승인의 기반한 데이터 전처리 자동화 파이프라인, 제 8회 KDT 해커톤에서는 인프라(AWS, Docker Compose 패키징)를 맡아 고용노동부장관상(우수상)을 받았습니다.

모델은 지독하게 테스팅해 보기 전까지 함부로 신뢰하지 않습니다. 봇은 조건부 알림을 보내고, 최종 판단은 사람이 합니다.

## 🔧 What I build

- **시장·온체인 도구** — 실시간 스크리너, 지갑 자금 이동 알림, 토큰 리서치 템플릿, 사전 등록 OOS 검정
- **사람이 승인하는 AI** — MCP 에이전트와 로컬 LLM은 제안만, 결정론 코드가 실행, 사람이 승인, 모든 변경은 lineage로 기록
- **실제로 배포되는 인프라** — Docker Compose 패키징, 보안 스캔이 붙은 GitHub Actions CI, 재현 가능한 배포

## 🚀 Featured Projects

### SURGENT · 🚧 운영 중 (private) — 급등 임박 토큰 스크리너
바이낸스 무기한 선물 전 종목 **727종**(코인 527 + 전통자산 연동 200)을 15분봉 웹소켓으로 감시합니다. 당일 시가 대비 **+25%** 를 돌파한 종목이 나오면 그 종목의 직전 24시간을 벡터로 만들어 전 종목과 비교하고, 상위 다섯 개를 **에너지 점수**(최근 캔들 폭, 24시간 최대 상승, 펀딩비의 전 종목 내 순위)와 함께 텔레그램으로 보냅니다. 주문 기능은 없고 판단은 사람이 합니다.
- 초기 가설(급등 패턴과의 코사인 유사도)은 새 데이터에서 무너졌습니다. 피처 가중치를 학습하는 모델은 **test AUC 0.46**. 따라 오른 후보와 안 오른 후보를 원값으로 비교하니 답은 차트 모양이 아니라 *급등 직전 상태*에 있었습니다
- **사전 등록 봉인 데이터 검정**: 에너지 순 상위 5종이 코사인 순을 8월 103회 중 **91회**(+6.80% vs +2.53%, 4시간 고점 터치 기준, 보유 수익 아님), 9월 88회 중 **80회** 앞섰습니다. 라이브 로그는 거래소 원자료에서 100% 재현됩니다
- asyncio 웹소켓 수집과 자동 재연결, REST 보충, 재기동에도 같은 신호를 두 번 보내지 않는 중복 차단, SQLite 채점(1h / 4h / 24h)

### [GYEOL](https://github.com/sbg0700/mfg-mcp) — 사람이 승인해야 실행되는 온프레미스 데이터 전처리 에이전트 · 🏆 삼성 AXI 부트캠프 최종 프로젝트 대상 (2026.06)
공장 밖으로 내보낼 수 없는 제조 데이터를 위한 MCP + 로컬 LLM. AI는 코드로 정한 규칙 안에서 *제안*만 하고, 사람이 *승인*하면, 결정론 코드가 *실행과 검증*을 맡으며, 모든 변경은 lineage로 남습니다.
- 프로젝트 스켈레톤, 엔드투엔드 에이전틱 플로우(Inspector → Planner → 사람의 승인 → Executor → Validator), 승인 게이트·lineage·스키마 검증 구조, React 6단계 파이프라인 UI 설계·구축
- 승인 반복 실행 문제 해결: 승인을 작업 순번에 걸어 두었는데 LLM이 계획마다 순서를 바꿨고, `작업 종류 + 대상 컬럼` 고정 식별자로 바꿔 해결
- 공공 제조 데이터 **KAMP 32종(약 5GB)** 에서 전 과정 작동, **자동 테스트 94건** 통과. 시연에서 승인된 사이클 타임 이상치 22행을 제거하자 예측 모델 **R² 0.9965** 회복(8GB VRAM 서버)

### [MoGuk](https://github.com/sbg0700/MoGuk) — 해커톤 인프라 · 🏆 제8회 K-디지털 트레이닝 해커톤 우수상(고용노동부장관상, 326팀)
소규모 제조업 외국인 근로자용 다국어 소통·안전교육 플랫폼. 4인 팀에서 배포와 운영을 전담했습니다.
- LLM, DB, API, 웹서버를 **Docker Compose** 한 묶음으로 패키징하고 GPU 설정은 별도 파일, 기능별 설정은 환경 변수로 분리해, 같은 패키지를 CPU 서버(LLM 응답 25초 초과)에서 GPU 서버(**2~3초**)로 코드 수정 없이 이전
- **GitHub Actions** 2단계 CI(정적 검증 + **Trivy** 보안 스캔)로 **HIGH 취약점 3건** 머지 전 차단, **Caddy** 로 HTTPS와 관리자 경로 IP 화이트리스트, IAM 최소 권한, DB 백업·복원 검증
- 팀원 PR을 인프라 관점에서 리뷰, 본선 전날 머지 21건을 사전 공지한 재배포 두 차례(각 **7분**)로 반영, 본선 이틀 장애 0건

### [PaintGuard](https://github.com/sbg0700/paintguard) — 자동차 도장 불량 예측, 완벽한 점수는 누수였습니다
팀 프로젝트, 모델링 담당.
- 첫 LightGBM 모델이 **AUC 1.0**. 피처 중요도에서 **검사 이후에만 알 수 있는 피처 5개**를 찾아 제거하고 시간 순 분할로 다시 검증하니 **0.556**
- 발표 며칠 전 팀에 재학습이 필요하다고 알리고, 검사 데이터로는 불량을 예측할 수 없다는 한계를 확정한 뒤 도장 표면 이미지 검출로 전환: **YOLOv11s, mAP@0.5:0.95 = 0.8656**
- 점수가 무너진 이유와 전환 과정을 발표에서 그대로 공개. 시간 순 검증 기준은 SURGENT에도 이어짐

### [PeakShield](https://github.com/sbg0700/PeakShield) — 철강 공정 전력 최적화, 기준을 전기 비용으로 바꿨습니다
부트캠프 첫 팀 프로젝트(Team MaD Fairies). 팀은 역률과 피크 감소로 개선을 평가하려 했고, 저는 **전기 비용**을 단일 목표로 제안하고 직접 만들었습니다.
- 한전 전기공급약관 기반 **전기료·ROI 계산 엔진**(계절·시간대별 단가, 역률 페널티), 최적화 목표 함수로 채택된 전기료 타깃 피처, 공정 영역을 클릭하면 노드를 조절할 수 있는 디지털 트윈 탭이 있는 **Flask 대시보드**
- 제시한 결과: 피크 수요 **629 → 531 kW(−15%)**, 역률 페널티 구간 **−6%**. 모델링(XGBoost/Optuna)은 팀원 담당

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

### (주)퍼스트소울코리아 (1st Soul Ventures) — Research & Trading Desk 인턴 · 2025.03 – 2025.08
*전통 금융 출신 멤버들이 설립한 크립토 헤지펀드 & VC.*
- 주간 리서치와 주야간 시장 모니터링 로테이션. 상장 예정 토큰 리서치(FDV/MC 밸류에이션, 투자자 티어, 토크노믹스, vesting)로 **리서치 리포트 28건** 작성, FDV·유통량·락업·다음 언락 시점을 고정 항목으로 둔 양식이 데스크 표준으로 채택
- OI, Funding Rate, Liquidation Map, Whale Flow를 근거로 **롱/숏 콜 제시**(진입·청산 집행과 펀드 운용은 대표 담당)
- 데스크의 **Python 봇** 제작: 지갑 입출금 알림 봇(유통량 대비 임계치 초과 시 텔레그램 알림, $BAN·$ORCA 적용, $BAN의 분산 후 재집중 흐름을 트랜잭션 단계에서 발견), FDV 정렬, Long/Short Signal Bot, Alpha Tracker, CME Gap Detector, SurgePlunge. 리서치 한 건 약 2시간 → 30분
- **Falcon Finance** 화이트리스트 부스트 딜을 자산 보호 조건(USDf 발행 구조, OCR 버퍼와 델타 중립 헤지, 청산 조건, sUSDf 리스테이킹과 NFT 락업) 기준으로 검토, 검토 자료가 회사 투자 판단에 반영

### 히포케이메논 — 투자정보파트 선임 연구원 · 2022.01 – 2024.09
*가상자산 시황과 투자 정보를 유튜브·텔레그램으로 제공하는 투자정보 회사.*
- 블록체인·자본시장 리서치: 프로젝트 분석(메인넷, 유통량, Price action)으로 투자 기회 발굴과 의사결정 지원
- 데일리·주간·월간 시장 동향 보고서 **300건 이상** 작성, 주 5회 이상 콘텐츠 발행
- 회사 채널 직접 운영(유튜브 **3천 → 2.7만**, 텔레그램 **5.6천**), 구독자 질문 응대·피드백 반영·채널 내 상품 판매
- 가상자산을 제도권 금융의 언어로 설명하기 위해 재직 중 투자자산운용사 자격 취득

## 🎓 Education & Certifications

- 🎓 **경영학 학사**, 동국대학교 DUICA
- 🧪 **삼성 AXI K-Digital Training**(2개 과정, 2025.09 – 2026.06) · **Schneider Electric Academy**(반도체/배터리 산업 솔루션) · **Build with AI Seoul 2026**(with Google DeepMind)
- 📜 투자자산운용사 · 증권투자권유대행인(금융투자협회) · ADsP · 빅데이터분석기사(필기)

---

<div align="center">

**블록체인 금융과 응용 AI 분야의 프로덕트·엔지니어링 포지션을 찾고 있습니다 — 한국 & 미국.**

[Portfolio](https://wry-willow-738.notion.site/389ed79dd39680c59e03e9dc8e6b2ff2) · [LinkedIn](https://linkedin.com/in/gabsong) · sbg0700@gmail.com

</div>
