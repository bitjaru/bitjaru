# Sunwoo Kim (김선우)

**Fullstack engineer & CTO. 12 years. I ship products — and I keep them running.**

Building fast is table stakes now. Anyone can generate a screen.
What I do is design the thing behind the screen so it doesn't fall over — and then actually operate it.

```
CTO @ YAYLABS · Co-founder @ YayPlanet
5 microservices on Kubernetes, in production · LSTM at 0.74% MAPE
300K users, 100+ TPS on-chain · Zero designers, by design
Before: eBay Korea · Samsung Card
```

---

## What I actually do

| | |
|---|---|
| **Depth, not just breadth** | Led a legacy (JSP/jQuery/.NET) → React SPA migration on a *live* commerce platform. Page load −60%, DB load −40%. Nothing broke. |
| **0→1 with architecture** | Took a product from "we have an idea" to shipped MVP as a contractor — auth, payments, points, raffle engine, community, admin. |
| **Design without a designer** | I didn't hire one. I wrote a design system that teaches AI *judgment* — 74 rules, 48 components — and open-sourced it. |
| **Infra that stays up** | Kubernetes, zero-downtime deploys, CI/CD, Saga-pattern event-driven orchestration. Running today, not a demo. |
| **AI as a pipeline, not a demo** | Agents that scan → analyze → render → package on a schedule, with a quality gate and a human before publish. |

---

## Products in production

### Oildealer — B2B fuel supply-chain reverse-auction platform
*CTO. Planning → architecture → development → operations.*

Five microservices (dual frontend / collection API / business backend / scheduler / admin) on Kubernetes.
MongoDB Time Series + Redis. Playwright market-data pipeline. GPT-4o news agent with a daily briefing.
Reverse-auction orders orchestrated with the **Saga pattern**, event-driven.
Cross-platform mobile app (Capacitor) shipped to both stores. A Windows agent syncing POS + tank sensors on-site.

**In-house LSTM price forecasting — MAPE 0.74%, 88% directional accuracy**, benchmarked against GARCH · VAR · VECM · XGBoost.
**Zero designers on the project.**

### Transaction forwarding API — LINE × Kaia
Redis + message queue architecture that decouples transaction submission from service logic.
Instead of hammering the chain, requests queue and workers drain them — sidestepping nonce collisions and rate limits. Retries, backoff, failure replay.

**300K game users. 100+ TPS at peak.**

### NNN — Telegram × TON gamefi launchpad
Launchpad backend (layered Node/Express), TON smart contracts, Telegram mini-app frontend, partner-game integration API.
Probability-driven mystery box engine with **externalized probability tables** — tuning odds doesn't require a redeploy.
Weekly reward distribution via cron, with a recovery path for failed payouts.
New partner games integrated in **under a day**.

### penguinboard — multi-platform seller intelligence SaaS
[penguinboard.com](https://www.penguinboard.com) · built and launched with one friend

Fashion/beauty brands sell across many marketplaces and their numbers live in a different admin panel for each one. This pulls them into one place — pricing, orders, revenue, per-channel P&L, SKU-level margin.

The collection engine is a **Chrome Extension (Manifest V3)**, not a scraper. Public-page scraping gets you blocked; an extension runs inside the user's own authenticated session looking at the user's own data. Two-layer content script (MAIN + ISOLATED world), XHR/Fetch interception rather than DOM parsing — so a UI redesign doesn't break it — plus session keep-alive so 2FA re-login stays rare.

### MARKET WHY — AI market-audit desk
[market-why-delta.vercel.app](https://market-why-delta.vercel.app/)

An AI analyzes the market, then **interrogates its own verdict**. Every call ships with supporting evidence, *counter*-evidence, and the condition that would falsify it. Past calls are scored — and prediction / avoidance / live-trade are scored on **separate denominators**, because mixing them flatters the numbers.

Nothing publishes unless the data layers pass validation, and a **replay check** re-runs the same input to confirm the same verdict comes out. Failures aren't hidden; they're shown as unconfirmed.
Runs headless on a schedule. **Publishing stays a human decision.**

There's a video pipeline attached to it too: script → TTS (SSML-controlled) → **scene timing auto-matched to the actual audio length** → subtitles → thumbnail → publish package. The sync isn't eyeballed on a timeline; the voice length *decides* the scene length. Rewrite the script, re-render, still in sync.

### YieldCore — RWA real-world-asset DeFi platform
Product planning, fullstack, smart contract lead. Asset tokenization (deposit / redeem / secondary trade), pooled liquidity with arbitrage logic, investor dashboard (yield, holdings, transaction history), on-chain state monitoring and alerts.

---

## Data & AI systems

**Forecasting that had to be right, not interesting.** LSTM price model at 0.74% MAPE and 88% directional accuracy — but the number that matters is that I benchmarked it against GARCH, VAR, VECM and XGBoost before trusting it.

**Collection that doesn't break.** Playwright pipelines running daily in production. Separate fixed-IP collection servers to survive IP-based limits. When a site can't be scraped safely, I switch to an extension-based path instead of escalating the arms race.

**Agents with a gate.** Multi-agent setups where one agent scans and writes, another reviews, and the result only publishes if it passes a quality check. The interesting part isn't that AI writes it — it's that AI *doesn't ship it* when the data is thin.

**SEO / GEO.** Search isn't the only front door anymore. People ask ChatGPT and Perplexity, and the answer cites *someone*. I build content to be citable: structured markup, explicit sources, answer-first paragraphs. Applied on my own sites, not just recommended.

---

## Open source

**[styleseed](https://github.com/bitjaru/styleseed)** — *Teach your AI design judgment. Not just components.*
[Live demo](https://styleseed-demo.vercel.app/) · Design system engine for Claude Code / Codex / Cursor. 74 rules, 48 components, 7 brand skins (Toss/Stripe/Linear/Notion/Raycast/Arc/Vercel), a named motion system. MIT.
The problem it solves: AI coding tools can produce a component. They cannot tell you *why* 16px is wrong here. This encodes that judgment.

**[codesyncer](https://github.com/bitjaru/codesyncer)** — *Claude forgets everything when the session ends. CodeSyncer makes it remember.*
Multi-repo collaboration framework for AI coding agents. Decisions and inferences get recorded as `@codesyncer-*` tags in the code instead of evaporating with the session. On npm.
**Oildealer actually runs on it** — this isn't a proposal, it's how my production platform is maintained.

**[pixelmind](https://github.com/bitjaru/pixelmind)** — *Your LLM is blind to what it creates. We give it eyes.*
Render-aware feedback loop for LLM-generated UI.

---

## Also built

| | |
|---|---|
| **WallSt.Savage** | US/KR equity intelligence dashboard — SEC Form 4 insider tracking, congressional trades, short-squeeze radar, r/wallstreetbets mention heatmap |
| **HypeSeoul** | Seoul trend map — PWA, 4 languages (ko/en/ja/zh), Google Maps with custom markers, 44px touch targets for accessibility |
| **DODOJI** | Anonymous community platform with a **trust-score system** (reviews 40% / reports 30% / recommendations 20% / activity 10%) — because anonymous communities die from bad actors, not bad features |
| **COBOOK** | Real-time kimchi-premium monitor across 10+ exchanges |
| **exitbot** | Trading signal engine — KRX + crypto, ICT/SMC pattern analysis, Gemini/Groq signal review, Telegram alerts |
| **charmander-rador** | Candidate-scoring engine with a **self-review loop** — the agent writes its own report, asks for critique, and commits |
| **tripstack** | MCP server — turns places scattered across a chat into a distance-optimized itinerary (farthest-first seeding + k-means + nearest-neighbour, deterministic) |
| **SuperAsset** | Stable Diffusion inversion style-transfer SaaS for game assets. Research → pipeline → frontend → backend, solo. **Selected for TIPS.** |

---

## Experience

| | | |
|---|---|---|
| 2025.12 – | **YayPlanet** | Co-Founder |
| 2022.05 – | **YAYLABS** | **CTO & Co-Founder** |
| 2021.12 – 2022.05 | **Samsung Card** | Frontend (CL3) — Vue/Nuxt architecture for a new service |
| 2017.07 – 2022.05 | **eBay Korea** | Software Engineer — Smile Club. Led legacy → React SPA migration |
| 2014.01 – 2017.02 | Research (military service) | Intrusion-tolerant systems — Xen hypervisor-based hidden-process and VM memory-tampering detection |

**M.S. Computer Science**, Hanyang University — Computer Network Security Lab

---

## Stack

| | |
|---|---|
| **Frontend** | React · TypeScript · Next.js · Vite · Capacitor · Tailwind · Vue/Nuxt |
| **Backend** | Node.js · Express · NestJS · TSOA · Python · FastAPI |
| **Data** | MongoDB (Time Series) · PostgreSQL · Redis · pandas · TensorFlow |
| **Infra** | Kubernetes · Docker · GitHub Actions · AWS · GCP · NCP · Nginx |
| **Web3** | Solidity · TON · Kaia · ethers |
| **AI** | Claude · GPT · Gemini · LangChain · MCP servers · agent pipelines · RAG |
| **Scraping** | Playwright · Chrome Extension (MV3) · anti-blocking strategy |

---

<details>
<summary><b>🇰🇷 한국어로 보기</b></summary>

<br>

## 김선우 — 풀스택 엔지니어 / CTO (12년차)

**빠르게 만드는 사람은 많아졌습니다. 저는 그렇게 만든 것을 실제로 운영해서 무너뜨리지 않은 사람입니다.**

화면을 뽑는 것과 아키텍처를 설계하는 것은 다릅니다. 5개 마이크로서비스를 직접 설계해 쿠버네티스에 무중단 배포하고, 지금도 운영하고 있습니다.

### 제가 남들과 다른 지점

**기술 깊이 — 얕게 넓은 게 아니라 깊게 넓습니다**

이베이코리아에서 *운영 중인* 커머스의 레거시(JSP/jQuery/.NET) 화면을 React SPA로 이관하는 작업을 리드했습니다. 페이지 로드 60% 개선, DB 부하 40% 감소, 기존 동작은 한 군데도 깨뜨리지 않고.

**0→1 — 빠른데 설계가 있습니다**

기획도 디자인도 없는 상태에서 외주로 받아 커머스+커뮤니티 MVP를 완주했습니다. 회원·권한, 결제, 포인트, 추첨 엔진, 커뮤니티, 어드민까지 프론트와 백엔드 전부.

**디자이너 없이 만듭니다 — 단, "AI 티 나는 UI"가 아닙니다**

AI 코딩 도구는 컴포넌트를 만들어 줍니다. 하지만 "여기서 16px이 왜 틀렸는지"는 말해주지 못합니다. 그 판단 기준을 시스템으로 만들어 오픈소스로 공개했습니다 (styleseed — 74개 룰, 48개 컴포넌트).

**인프라가 버팁니다**

쿠버네티스 무중단 배포, CI/CD, Saga 패턴 이벤트 드리븐 오케스트레이션. 데모가 아니라 오늘도 돌고 있습니다.

**AI를 파이프라인으로 씁니다**

수집 → 분석 → 렌더 → 발행 패키지 생성까지 에이전트가 스케줄로 자동 실행하되, **품질 게이트를 통과하지 못하면 만들지 않고, 발행은 사람이 결정**합니다. AI가 글을 쓰는 게 대단한 게 아니라, 데이터가 빈약할 때 AI가 **발행하지 않는 것**이 핵심입니다.

### 실서비스

**Oildealer — B2B 유류 공급망 역경매 플랫폼** (CTO / 기획·설계·개발·운영 총괄)
5개 마이크로서비스를 쿠버네티스로 운영. MongoDB Time Series + Redis, Playwright 시장 데이터 파이프라인, GPT-4o 뉴스 에이전트 일일 브리핑. 역경매 주문은 Saga 패턴 이벤트 드리븐. 자체 LSTM 가격 예측 **MAPE 0.74% · 방향 정확도 88%** (GARCH·VAR·VECM·XGBoost 대비 우위 검증). Capacitor 앱 양대 스토어 출시. 주유소 현장 POS·탱크 센서 동기화 Windows 에이전트. **디자이너 0명.**

**트랜잭션 포워딩 API — LINE × Kaia**
Redis + 메시지 큐로 트랜잭션 전송을 서비스 로직에서 분리. 체인을 직접 때리는 대신 큐에 적재해 nonce 충돌과 레이트리밋을 회피하고, 재시도·백오프·실패 재처리 경로를 확보. **게임 유저 30만, 피크 100+ TPS.**

**NNN — 텔레그램 × TON 게임파이 런치패드**
런치패드 백엔드, TON 스마트컨트랙트, 텔레그램 미니앱, 파트너 게임 연동 API. 확률 테이블을 코드 밖으로 뺀 미스터리박스 엔진(확률 조정에 재배포 불필요), 주간 리워드 자동 분배(실패 시 리커버리 경로). 파트너 게임 신규 통합 **1일 내**.

**penguinboard — 멀티플랫폼 셀러 인텔리전스 SaaS** (친구와 2인 팀으로 런칭)
여러 이커머스에 흩어진 셀러 데이터를 하나로 통합. 수집 엔진은 스크래퍼가 아니라 **크롬 익스텐션(MV3)** 입니다. 퍼블릭 페이지 스크래핑은 차단당하지만, 익스텐션은 "사용자가 자기 어드민에서 자기 데이터를 보는 것"이라 리스크가 없습니다. XHR/Fetch 인터셉트 방식이라 UI가 리디자인돼도 안 깨집니다.

**MARKET WHY — AI 시장 감사 데스크**
AI가 시장을 분석하고 **자기 판단을 심문**합니다. 모든 판정에 지지 근거·반대 근거·폐기 조건을 함께 공개하고, 과거 판정을 채점하되 예측·회피·실거래를 **분모를 나눠서** 계산합니다(섞으면 성과가 왜곡되니까요). 데이터 레이어 검증을 통과하지 못하면 발행하지 않고, 같은 입력으로 재실행해 같은 결론이 나오는지 확인하는 **재현성 검사**를 거칩니다.

**YieldCore — RWA 실물자산 유동화 DeFi**
자산 토큰화(예치·반환·2차 거래), 풀드 유동성 + 아비트라지 로직, 투자 대시보드, 온체인 상태 모니터링.

### SEO / GEO

이제 검색엔진만이 유입 경로가 아닙니다. 사람들이 ChatGPT·Perplexity에 묻고, AI가 **어떤 사이트를 인용해서** 답합니다. 그래서 콘텐츠를 인용 가능한 형태로 만듭니다 — 구조화된 마크업, 명시적 출처, 질문에 먼저 답하는 문단 구조. 제 사이트에 실제로 적용해 두었습니다.

### 경력

| | | |
|---|---|---|
| 2025.12 ~ | **YayPlanet** | Co-Founder |
| 2022.05 ~ | **YAYLABS** | CTO & Co-Founder |
| 2021.12 ~ 2022.05 | **삼성카드** | 프론트엔드 CL3 — 신규 서비스 Vue/Nuxt 아키텍처 |
| 2017.07 ~ 2022.05 | **eBay Korea** | 소프트웨어 엔지니어 — 스마일클럽, 레거시→React SPA 이관 리드 |
| 2014.01 ~ 2017.02 | 전문연구요원 | 침입감내 시스템 — Xen Hypervisor 기반 은닉 프로세스·VM 메모리 변조 탐지 |

**한양대학교 컴퓨터공학 석사** (컴퓨터네트워크보안연구실)
**TIPS 연계 프로그램 선정** — Stable Diffusion 기반 게임 에셋 생성 SaaS를 논문 연구부터 프론트·백엔드까지 단독 구현

</details>
