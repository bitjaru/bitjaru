<div align="center">

# Sunwoo Kim · 김선우

**Fullstack engineer & CTO · 12 years · I ship products — and I keep them running.**

`CTO @ YAYLABS` · `Co-founder @ YayPlanet` · `ex-eBay Korea` · `ex-Samsung Card` · `M.S. Hanyang Univ.`

<br>

[![styleseed](https://img.shields.io/github/stars/bitjaru/styleseed?style=for-the-badge&logo=github&label=styleseed&labelColor=0d1117&color=d4a72c)](https://github.com/bitjaru/styleseed)
[![codesyncer](https://img.shields.io/github/stars/bitjaru/codesyncer?style=for-the-badge&logo=github&label=codesyncer&labelColor=0d1117&color=d4a72c)](https://github.com/bitjaru/codesyncer)
[![pixelmind](https://img.shields.io/github/stars/bitjaru/pixelmind?style=for-the-badge&logo=github&label=pixelmind&labelColor=0d1117&color=d4a72c)](https://github.com/bitjaru/pixelmind)

<br>

| Shipped | Scale | Depth |
|:---:|:---:|:---:|
| **30+** products & platforms | **300K** users · **100+** TPS | **12 yrs** · 5 MSA in prod |

</div>

---

> Building fast is table stakes now. Anyone can generate a screen.
> **What I do is design the thing behind the screen so it doesn't fall over — and then actually operate it.**

---

## 📑 Index

- [What I actually do](#what-i-actually-do)
- [🚀 Products in production](#-products-in-production)
- [🎮 Games · Mini-apps](#-games--mini-apps)
- [📊 Data · AI · Automation](#-data--ai--automation)
- [⛓️ Web3](#️-web3)
- [🌐 Web · App · Community](#-web--app--community)
- [📦 Open source](#-open-source)
- [🛠️ Tools I built for myself](#️-tools-i-built-for-myself)
- [Experience](#experience)
- [Stack](#stack)
- [🇰🇷 한국어](#-한국어로-보기)

---

## What I actually do

| | |
|---|---|
| **Depth, not just breadth** | Led a legacy (JSP/jQuery/.NET) → React SPA migration on a *live* commerce platform. Page load −60%, DB load −40%. Nothing broke. |
| **0→1 with architecture** | Took a product from "we have an idea" to shipped MVP as a contractor — auth, payments, points, raffle engine, community, admin. |
| **Design without a designer** | I didn't hire one. I wrote a design system that teaches AI *judgment* — 74 rules, 48 components — and open-sourced it. |
| **Infra that stays up** | Kubernetes, zero-downtime deploys, CI/CD, Saga-pattern orchestration. Running today, not a demo. |
| **AI as a pipeline, not a demo** | Agents that scan → analyze → render → package on a schedule, with a quality gate and a human before publish. |

---

## 🚀 Products in production

### Oildealer — B2B fuel supply-chain reverse-auction platform
`CTO` `5 microservices` `Kubernetes` `Saga pattern` `LSTM 0.74% MAPE` `Zero designers`

Planning → architecture → development → operations. All of it.
Five services (dual frontend / collection API / business backend / scheduler / admin) on Kubernetes. MongoDB Time Series + Redis. Playwright market-data pipeline. GPT-4o news agent with a daily briefing. Reverse-auction orders orchestrated event-driven with the Saga pattern.
Cross-platform mobile app (Capacitor) in both stores. A Windows agent syncing POS + tank sensors on-site.

**In-house LSTM forecasting — MAPE 0.74%, 88% directional accuracy** — benchmarked against GARCH · VAR · VECM · XGBoost before I trusted it.

### Transaction forwarding API — LINE × Kaia
`300K users` `100+ TPS` `Redis + MQ` `nonce-safe`

Decouples transaction submission from service logic. Instead of hammering the chain, requests queue and workers drain them — sidestepping nonce collisions and rate limits. Retries, backoff, failure replay.

### penguinboard — multi-platform seller intelligence SaaS
[penguinboard.com](https://www.penguinboard.com) · `Chrome Extension MV3` `XHR interception` `2-person team` `launched`

Fashion/beauty brands sell across many marketplaces and their numbers live in a different admin panel for each one. This pulls them into one place — pricing, orders, per-channel P&L, SKU-level margin.

The collection engine is an **extension, not a scraper.** Public-page scraping gets you blocked; an extension runs inside the user's own authenticated session, on the user's own data. Two-layer content script (MAIN + ISOLATED world), XHR/Fetch interception instead of DOM parsing — so a UI redesign doesn't break it — plus session keep-alive so 2FA re-login stays rare.

### MARKET WHY — AI market-audit desk
[market-why-delta.vercel.app](https://market-why-delta.vercel.app/) · `quality gate` `replay check` `SEO/GEO` `human-gated publish`

An AI analyzes the market, then **interrogates its own verdict.** Every call ships with supporting evidence, *counter*-evidence, and the condition that would falsify it. Past calls get scored — and prediction / avoidance / live-trade are scored on **separate denominators**, because mixing them flatters the numbers.

Nothing publishes unless the data layers validate, and a **replay check** re-runs the same input to confirm the same verdict. Failures aren't hidden; they show as unconfirmed.

An attached video pipeline: script → TTS (SSML-controlled) → **scene timing auto-matched to the actual audio length** → subtitles → thumbnail → publish package. The sync isn't eyeballed on a timeline; the voice length *decides* the scene length.

### OHTTO — wish-based commerce + community
`contract work` `MVP shipped` `payments` `raffle engine` `admin`

Handed an idea, no spec, no design. Shipped the MVP. Social login and multi-role permissions, payments → points → entitlement, wishlist/challenge/raffle engine, community feed and ranking, operator admin. Frontend and backend, solo.

### YieldCore — RWA real-world-asset DeFi
`Solidity` `tokenization` `liquidity pool` `investor dashboard`

Product planning, fullstack, smart contract lead. Asset tokenization (deposit / redeem / secondary trade), pooled liquidity with arbitrage logic, investor dashboard, on-chain state monitoring and alerts.

### SuperAsset — game-asset generation SaaS
`Stable Diffusion` `inversion style transfer` `solo build` `🏆 TIPS selected`

Research (InST · WaveFunctionCollapse · ProSpect) → data pipeline → frontend → backend. Alone. Selected for the TIPS program.

---

## 🎮 Games · Mini-apps

Running a game inside a messenger mini-app is not the same as shipping a web app. You inherit someone else's container, someone else's auth, someone else's lifecycle — and you still have to settle rewards on-chain without losing a transaction.

### FANANAS — Unity Web3 game on Telegram & LINE mini-apps
`Unity` `WebGL` `C#` `Kotlin middleware` `Telegram mini-app` `LINE mini-app` `on-chain rewards` `Kubernetes`

A solitaire-based Web3 game, built in **Unity** and shipped inside **both Telegram and LINE mini-apps** — two different host platforms, one game.

- **Unity (C#) → WebGL** build embedded in the mini-app container
- **Kotlin middleware** bridging game score ↔ platform identity ↔ on-chain settlement
- Game economy: token accrual → conversion → reward distribution, designed so a failed on-chain payout is recoverable instead of silently lost
- Kubernetes, zero-downtime deploys

The hard part wasn't the card game. It was making a Unity build, a messenger's auth, and a blockchain agree with each other — reliably, at scale, on two platforms at once.

### NNN — Telegram × TON gamefi launchpad
`TON` `Tact/FunC` `Telegram mini-app` `partner API` `1-day integration`

A launchpad that aggregates multiple games. Launchpad backend, TON smart contracts, mini-app frontend, partner-game integration API.
Probability-driven mystery box engine with **externalized probability tables** — tuning odds doesn't require a redeploy. Weekly reward distribution via cron, with a recovery path for failed payouts.
**New partner games integrated in under a day** — because the score/reward API was designed as a contract, not as an afterthought.

> FANANAS is the game that goes *on* a launchpad. NNN is the launchpad. I built both sides.

---

## 📊 Data · AI · Automation

| Project | Tags | What it does |
|---|---|---|
| **charmander-rador** | `self-review loop` `agent` | Candidate-scoring engine where the agent writes its own report, requests critique, and commits the result |
| **exitbot** | `KRX + crypto` `ICT/SMC` `Gemini/Groq` | Real-time trading signal analysis with AI review and Telegram alerts |
| **WallSt.Savage** | `SEC Form 4` `Reddit heatmap` `dark pool` | US/KR equity intelligence — insider trades, congressional trades, short-squeeze radar, r/wallstreetbets mention heatmap |
| **COBOOK** | `10+ exchanges` `real-time` | Kimchi-premium monitor across domestic and international exchanges |
| **culture-leak-radar** | `Claude + Gemini` `RSS` | Dual-LLM pipeline for cultural-leak detection |
| **hermes-kiwi** | `multi-agent context` | Read-only mirror that lets a different machine and a different agent pick up where the last one left off |
| **market-insight** | `auto-report` `KR/US` | YouTube Charts · entertainment · news · gaming trend reports, collected and committed automatically |

**On forecasting:** the number that matters isn't 0.74% MAPE — it's that I benchmarked it against four other models before believing it.
**On agents:** the interesting part isn't that AI writes the report. It's that AI **doesn't ship it** when the data is thin.
**On SEO/GEO:** search isn't the only front door anymore. People ask ChatGPT and Perplexity, and the answer cites *someone*. I build content to be citable — structured markup, explicit sources, answer-first paragraphs. Applied on my own sites, not just recommended.

---

## ⛓️ Web3

| Project | Tags |
|---|---|
| **FANANAS** — Unity Web3 game | `Unity WebGL` `Telegram + LINE mini-app` `on-chain rewards` |
| **NNN** — Telegram × TON launchpad | `TON` `Tact/FunC` `token burn model` |
| **LINE × Kaia transaction API** | `Kaia SDK` `ethers` `Redis + Bull` `100+ TPS` |
| **JumpingPeng Drops** | `NFT drop dApp` `LINE mini-app` |
| **YieldCore** | `RWA` `Solidity` `liquidity pool` |
| **PBT / ARTIVIST** | `EIP-5791` `NFC chip ↔ NFT binding` |
| **MyCatIsFishingStar** | `contracts` |

---

## 🌐 Web · App · Community

| Project | Tags | Note |
|---|---|---|
| **HypeSeoul** | `PWA` `i18n ko/en/ja/zh` `Google Maps` `a11y 44px` | Seoul trend map — pop-ups, K-POP landmarks, gachapon shops |
| **DODOJI** | `trust score` `anonymous` `community` | Anonymous communities die from bad actors, not missing features. So: Trust Score = reviews 40% / reports 30% / recommendations 20% / activity 10% |
| **Chiwat** | `5 countries` `i18n` | Multi-region mini-app |
| **today-index** | `Apps in Toss` | Toss ecosystem app |
| **pickeat** | `own design system` | |
| **FANCUT** | `Vite + Python` | |

---

## 📦 Open source

### [styleseed](https://github.com/bitjaru/styleseed) [![stars](https://img.shields.io/github/stars/bitjaru/styleseed?style=flat-square&label=%E2%98%85&labelColor=0d1117&color=d4a72c)](https://github.com/bitjaru/styleseed/stargazers)
**Teach your AI design judgment. Not just components.**
[Live demo](https://styleseed-demo.vercel.app/) · `74 rules` `48 components` `7 brand skins` `MIT`

AI coding tools can produce a component. They cannot tell you *why* 16px is wrong here. This encodes that judgment — for Claude Code, Codex, Cursor. Brand skins: Toss / Stripe / Linear / Notion / Raycast / Arc / Vercel. Named motion system, 15 slash commands.

### [codesyncer](https://github.com/bitjaru/codesyncer) [![stars](https://img.shields.io/github/stars/bitjaru/codesyncer?style=flat-square&label=%E2%98%85&labelColor=0d1117&color=d4a72c)](https://github.com/bitjaru/codesyncer/stargazers)
**Claude forgets everything when the session ends. CodeSyncer makes it remember.**
`multi-repo` `@codesyncer-* tags` `npm`

Decisions and inferences get recorded in the code instead of evaporating with the session.
**Oildealer actually runs on it** — this isn't a proposal, it's how my production platform is maintained.

### [pixelmind](https://github.com/bitjaru/pixelmind) [![stars](https://img.shields.io/github/stars/bitjaru/pixelmind?style=flat-square&label=%E2%98%85&labelColor=0d1117&color=d4a72c)](https://github.com/bitjaru/pixelmind/stargazers)
**Your LLM is blind to what it creates. We give it eyes.**
`render-aware feedback loop`

### awesome-* lists
Curated: `claude-plugins` `agent-skills` `ai-coding-tools` `vibe-coding`

---

## 🛠️ Tools I built for myself

| Tool | Tags | Why |
|---|---|---|
| **tripstack** | `MCP server` `deterministic routing` | Places scattered across a chat → a distance-optimized itinerary. farthest-first seeding + Lloyd k-means + nearest-neighbour. Same input, same output, always. |
| **reels-mv-conti** | `Claude Code skill` | Song + concept → full short-form production package: second-by-second storyboard, AI video prompts, sound guide |
| **aiaiai / aicreation** | `content pipeline` | AI-generated content studio — worldbuilding, prompts, upload calendar, performance review |
| **goldmine** | `ideation workspace` | New-business ideation and competitive analysis, weekly reports |

Also: AX (AI transformation) engagements for clinics and investment firms — automating manual workflows with tools I built.

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
**🏆 TIPS program** — selected for SuperAsset

---

## Stack

| | |
|---|---|
| **Frontend** | React · TypeScript · Next.js · Vite · Capacitor · Tailwind · Vue/Nuxt |
| **Backend** | Node.js · Express · NestJS · TSOA · Python · FastAPI · Kotlin |
| **Game** | Unity · C# · WebGL · Telegram / LINE mini-app SDK |
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

**기술 깊이** — 이베이코리아에서 *운영 중인* 커머스의 레거시(JSP/jQuery/.NET) 화면을 React SPA로 이관하는 작업을 리드했습니다. 페이지 로드 60% 개선, DB 부하 40% 감소, 기존 동작은 한 군데도 깨뜨리지 않고.

**0→1** — 기획도 디자인도 없는 상태에서 외주로 받아 커머스+커뮤니티 MVP를 완주했습니다.

**디자이너 없이** — AI 코딩 도구는 컴포넌트를 만들어 줍니다. 하지만 "여기서 16px이 왜 틀렸는지"는 말해주지 못합니다. 그 판단 기준을 시스템으로 만들어 오픈소스로 공개했습니다 (styleseed).

**인프라** — 쿠버네티스 무중단 배포, CI/CD, Saga 패턴 이벤트 드리븐. 데모가 아니라 오늘도 돌고 있습니다.

**AI 파이프라인** — 수집 → 분석 → 렌더 → 발행 패키지까지 에이전트가 자동 실행하되, **품질 게이트를 통과하지 못하면 만들지 않고 발행은 사람이 결정**합니다. AI가 글을 쓰는 게 대단한 게 아니라, 데이터가 빈약할 때 AI가 **발행하지 않는 것**이 핵심입니다.

### 게임 · 미니앱

메신저 미니앱 안에서 게임을 돌리는 건 웹앱을 만드는 것과 다릅니다. 남의 컨테이너, 남의 인증, 남의 생명주기를 물려받은 채로, 온체인 보상을 트랜잭션 하나 잃지 않고 정산해야 합니다.

**FANANAS — Unity 기반 Web3 게임 (텔레그램 + LINE 미니앱)**
`Unity` `WebGL` `C#` `Kotlin 미들웨어` `텔레그램 미니앱` `LINE 미니앱` `온체인 리워드` `K8s`

솔리테어 기반 Web3 게임을 **Unity로 만들어 텔레그램과 LINE 미니앱 양쪽에** 올렸습니다. 서로 다른 두 호스트 플랫폼, 하나의 게임.

- Unity(C#) → **WebGL 빌드**를 미니앱 컨테이너에 임베드
- **Kotlin 미들웨어**가 게임 스코어 ↔ 플랫폼 아이덴티티 ↔ 온체인 정산을 연결
- 게임 경제: 토큰 적립 → 전환 → 리워드 분배. 온체인 지급이 실패해도 조용히 유실되지 않고 복구되도록 설계
- 쿠버네티스 무중단 배포

어려운 건 카드 게임이 아니었습니다. **Unity 빌드와 메신저 인증과 블록체인을 서로 합의시키는 것** — 그것도 두 플랫폼에서 동시에, 안정적으로.

**NNN — 텔레그램 × TON 게임파이 런치패드**
여러 게임을 모은 런치패드. 확률 테이블을 코드 밖으로 뺀 미스터리박스 엔진(재배포 없이 확률 조정), 주간 리워드 자동 분배(실패 시 리커버리 경로). **파트너 게임 신규 통합 1일 내** — 스코어/리워드 API를 나중에 붙인 게 아니라 처음부터 계약으로 설계했기 때문입니다.

> FANANAS는 런치패드에 **올라가는 게임**이고, NNN은 **런치패드 자체**입니다. 양쪽을 다 만들었습니다.

### 주요 프로젝트

| 프로젝트 | 태그 | 내용 |
|---|---|---|
| **Oildealer** | `CTO` `5개 MSA` `K8s` `LSTM 0.74%` `디자이너 0명` | B2B 유류 역경매 플랫폼. 기획·설계·개발·운영 총괄. Saga 패턴, Playwright 파이프라인, GPT-4o 뉴스 에이전트, 자체 LSTM 예측 |
| **LINE × Kaia API** | `30만 유저` `100+ TPS` | Redis + 메시지 큐로 트랜잭션 전송을 분리. nonce 충돌·레이트리밋 회피, 재시도·백오프·실패 재처리 |
| **penguinboard** | `크롬 익스텐션 MV3` `2인 런칭` | 멀티플랫폼 셀러 데이터 통합 SaaS. 스크래퍼가 아니라 익스텐션 — "사용자가 자기 어드민에서 자기 데이터를 보는 것"이라 차단 리스크가 없습니다 |
| **MARKET WHY** | `품질 게이트` `재현성 검사` `SEO/GEO` | AI가 시장을 분석하고 자기 판단을 심문. 지지·반대 근거와 폐기 조건 공개, 예측/회피/실거래를 분모를 나눠 채점 |
| **OHTTO** | `외주 MVP 완주` `결제` `추첨엔진` | 기획도 디자인도 없이 받아 출시까지 |
| **YieldCore** | `RWA` `Solidity` | 실물자산 유동화 DeFi |
| **SuperAsset** | `Stable Diffusion` `🏆 TIPS` | 논문 연구부터 프론트·백엔드까지 단독 구현 |
| **DODOJI** | `신뢰도 시스템` | 익명 커뮤니티는 기능이 아니라 악성 사용자 때문에 죽습니다. Trust Score = 후기 40% / 신고 30% / 추천 20% / 활동 10% |
| **HypeSeoul** | `PWA` `4개국어` `접근성` | 서울 트렌드 지도 |
| **WallSt.Savage** | `SEC Form 4` `Reddit 히트맵` | 미국·한국 주식 인텔리전스 대시보드 |
| **tripstack** | `MCP 서버` `결정적 알고리즘` | 흩어진 장소 → 동선 최적화 일정. 같은 입력이면 항상 같은 출력 |

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

**한양대학교 컴퓨터공학 석사** (컴퓨터네트워크보안연구실) · **TIPS 연계 선정**

</details>
