<div align="center">

# Pyae Sone Kyaw · `Seon`

### Evaluation-Driven AI Engineer · Agent Graphs · Evals · Full-Stack

**I build agent workflows as explicit graphs — then define how they're checked, trace every step, and observe the results.**

_Define → Build → Trace → Observe. Every project pairs what was built with how it's evaluated._

[![Portfolio](https://img.shields.io/badge/Portfolio-pseonkyaw.dev-C9A96E?style=for-the-badge&logo=vercel&logoColor=white)](https://pseonkyaw.dev/)
[![Hub](https://img.shields.io/badge/Portfolio_Hub-evals_%26_projects-CC7B7B?style=for-the-badge&logo=vercel&logoColor=white)](https://pseonkyaw-hub.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Pyae_Sone_Kyaw-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/pyae-sone-kyaw-80386721b)
[![Kaggle](https://img.shields.io/badge/Kaggle-pyaesonekyaw-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/pyaesonekyaw)
[![Email](https://img.shields.io/badge/Email-Get_in_touch-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:pyaesonekyaw1022000@gmail.com)

</div>

---

## 👋 Who I Am

I'm a **Full-Stack AI Engineer who ships products to real users, not demos.** Engineering since 2021, AI/ML since 2023 — from NLP research labs in Bangkok and Paris, to zero-to-one startups at Station F, to agentic pipelines as a freelance AI engineer.

Most recently at **Hoora Games (SAS EASYWIN)** I owned the **evaluation and quality-gating layer** of an agentic game-generation pipeline built on **Mastra / TypeScript**. Today I focus on **agent graphs you can measure**: routers, evaluators, tracing and observability.

- 🏗️ **I architect first, then build.** Clean / Hexagonal architecture, API-first design, real tests, CI that stays green.
- 🤖 **My specialty:** agent workflows and routers, evaluation harnesses (deterministic detectors, mutant testing, LLM judges), RAG / GraphRAG, observability, and LLM fine-tuning.
- 🎓 **Dual Master's in Data Science** — Télécom SudParis (Institut Polytechnique de Paris) 🇫🇷 & Asian Institute of Technology 🇹🇭.
- 🌏 Yangon → Bangkok → Paris. Social scientist turned engineer — communication and cross-cultural instincts are part of the toolkit.

---

## 🚀 Featured Projects — Built, Then Measured

> Each one pairs **what was built** with **how it's evaluated** — and says where the evaluation stops.

### 🛰️ [Faultline NOC](https://github.com/soneeee22000/faultline-noc) — Agent Router + Evaluation Harness

One router in front of three specialist agents, scored **before it can touch a network**. A typed `RoutePlan` contract (ordered steps, per-step context, which step may write and whether it needs confirmation), a keyword baseline and two Claude routers answering via a forced tool call — on a seeded, simulated 5G SA core. The harness is itself tested: **4 mutant routers each carry one planted defect and must trip their own detector.** CI replays every recorded model call with no API key.

`Python` · `pydantic` · `mypy strict` · `pytest` · `Anthropic tool use` — **Claude Haiku 4.5 & Sonnet 5: 45/52 vs keyword baseline 40/52** · [▶ Design note](https://faultline-noc.vercel.app/#router) · [Project page](https://faultline-noc.vercel.app)

### 🎮 [Agentic Game Generator](https://github.com/soneeee22000/cartridge) — Mastra Workflow Graph + Two-Tier Evaluator

Generates single-file HTML5 mini-games through an explicit workflow graph: plan → generate ⇄ verify (repair loop capped at 3) → finalize | reject, with typed Zod I/O and every failure attributed to its step. Checked by **24 deterministic contract rules**, a **Playwright runtime probe**, a cited LLM judge, and a language check. Key finding: **9 of 20 games that pass every static rule still fail at runtime.**

`TypeScript` · `Mastra` · `Zod` · `AI SDK` · `Playwright` · `Vitest` — **20/20 prompts produced a game · replayable from committed cassettes** · [▶ Live demo (replayed model calls)](https://cartridge-engine.vercel.app)

### 📡 [AgentPulse](https://github.com/soneeee22000/agentpulse) — Real-Time Observability for Agent Runs

Traces, tool calls, tokens, cost, latency and errors — streamed live from a swappable event bus (memory / Pub/Sub / Kafka drivers) into a span waterfall and a 60-second rolling p50/p95 aggregator. One Zod event contract, checked at ingest and in the browser. Demo traffic is simulated.

`TypeScript` · `Fastify` · `Vue 3` · `Kafka` · `GCP Pub/Sub` · `SSE` · `GraphQL` — **76 tests** · [▶ Live demo](https://agentpulse-web-171722935814.europe-west1.run.app)

### 📚 [WikiHow-MY](https://github.com/soneeee22000/wikihow-mt-my) — English→Myanmar MT, Fine-Tune & Human Study

~10K human post-edited pairs with article-disjoint splits, an **NLLB-200 600M fine-tune** ([weights on HF](https://huggingface.co/PyaeSoneK/nllb-600m-wikihow-en-my)), a 4-system benchmark (chrF++, spBLEU, COMET, MetricX-24), and a 9-rater human study — which showed my own proposed metric **fails** (r = 0.084). The negative result is reported.

`Python` · `Transformers` · `NLLB-200` · `COMET` · `MetricX-24` — **+5.63 chrF++ in-domain · +4.33 on FLORES+**

---

## 🏗️ Also Built

### 🔍 [AgentProbe](https://github.com/soneeee22000/AgentProbe) — AI Agent Failure Taxonomy & Eval Harness

A ReAct agent written from scratch, with a deterministic failure taxonomy, a 52-case evaluation harness and live SSE streaming of reasoning traces.

`Python` · `FastAPI` · `TypeScript` · `SSE` — **Recorded benchmark: Claude Haiku 4.5, 42/52**

### 🕸️ [Knowledge-Graph RAG Explorer](https://github.com/soneeee22000/Knowledge-Graph-RAG-Explorer) · 🧩 [AgentCanvas](https://github.com/soneeee22000/agentcanvas)

GraphRAG stages on an interactive canvas with a retrieval eval (vector-only vs graph-expanded), and a Vue Flow studio for composing agent workflows with step-level run visibility.

`Vue 3` · `VueFlow` · `Node/TS` · `Mastra` · `BAML` — [▶ KG-RAG demo (mock mode)](https://knowledge-graph-rag-explorer.vercel.app) · [▶ AgentCanvas demo (mock mode)](https://agentcanvas-demo.vercel.app)

### 💉 [VaxEvidence](https://github.com/soneeee22000/VaxEvidence-Dev) — Real-World Evidence Platform

PICO protocol builder, PRISMA screening, RoB 2 / ROBINS-I assessment, meta-analysis forest plots, real-time CRDT collaboration, and FDA / EMA / CDISC exports.

`Next.js 16` · `React 19` · `TypeScript` · `Supabase` — **76 API routes · 27 DB tables · 1,400+ tests** · [▶ Live demo](https://vaxevidence-dev.vercel.app/demo)

### ⚡ [EV Charging Copilot](https://github.com/soneeee22000/electra-charging-copilot) · 🪪 [FaceProof](https://github.com/soneeee22000/faceproof) · 🗣️ SpeakProof

A tool-grounded RAG assistant where every station, price and route comes from a tool call · face verification + liveness detection measured on the LFW protocol · a TOEFL speaking-practice bot inside Telegram used by learners in Myanmar.

> Data & back-end range: [GridFlex](https://github.com/soneeee22000/gridflex) (AWS grid lakehouse) · [CSRD Lake](https://github.com/soneeee22000/csrd-lake) (Snowflake + dbt) · [CDR Pipeline](https://github.com/soneeee22000/cdr-pipeline) & [Diameter Credit-Control](https://github.com/soneeee22000/diameter-cc) (Java 21 · Spring Boot 3.5 · Kafka) — more on [pseonkyaw.dev](https://pseonkyaw.dev/).

---

## 🛠️ Languages & Tools

### Languages

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

### AI & ML

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Anthropic](https://img.shields.io/badge/Claude-191919?style=for-the-badge&logo=anthropic&logoColor=white)
![Mistral AI](https://img.shields.io/badge/Mistral_AI-FA520F?style=for-the-badge&logo=mistralai&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

### Backend & Frameworks

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)

### Data Engineering

![Kafka](https://img.shields.io/badge/Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Spark](https://img.shields.io/badge/Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=for-the-badge&logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=for-the-badge&logo=dbt&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=for-the-badge&logo=snowflake&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)

### Cloud & DevOps

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=icloud&logoColor=white)
![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

### Databases

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Neo4j](https://img.shields.io/badge/Neo4j-4581C3?style=for-the-badge&logo=neo4j&logoColor=white)

---

## 📊 GitHub Stats

<div align="center">

<img src="https://github-readme-stats-sigma-five.vercel.app/api?username=soneeee22000&show_icons=true&theme=default&hide_border=true&count_private=true&include_all_commits=true" alt="GitHub Stats" height="165" />
<img src="https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=soneeee22000&layout=compact&theme=default&hide_border=true&langs_count=8" alt="Top Languages" height="165" />

<img src="https://streak-stats.demolab.com/?user=soneeee22000&theme=default&hide_border=true" alt="GitHub Streak" />

</div>

---

<div align="center">

**Building at the frontier of AI, data, and product — from Station F to the rest of the world.**

Open to mid-to-senior roles & collaboration — AI Engineer · ML Engineer · Applied AI / Evals.

📫 Always happy to talk AI, data, or building something ambitious.

[**pseonkyaw.dev**](https://pseonkyaw.dev/) · [**Portfolio Hub**](https://pseonkyaw-hub.vercel.app) · [**LinkedIn**](https://www.linkedin.com/in/pyae-sone-kyaw-80386721b) · [**Kaggle**](https://www.kaggle.com/pyaesonekyaw)

</div>
