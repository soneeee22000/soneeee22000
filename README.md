# Pyae Sone Kyaw · Seon

**Evaluation-driven AI engineer.** I build agent workflows as explicit graphs, then define how they are checked, trace every step and observe the results.

Engineering since 2021, AI/ML since 2023. Paris.

[Portfolio hub](https://pseonkyaw-hub.vercel.app) · [pseonkyaw.dev](https://pseonkyaw.dev) · [LinkedIn](https://www.linkedin.com/in/pyae-sone-kyaw) · [Hugging Face](https://huggingface.co/PyaeSoneK) · [Email](mailto:pyaesonekyaw101010@gmail.com)

---

### How I work: Define → Build → Trace → Observe

1. **Define:** the contract, schema or dataset the system is checked against
2. **Build:** the system itself
3. **Trace:** per-step records a person can follow afterwards
4. **Observe:** measurement (evals, benchmarks, human studies, live metrics)

Every project below pairs what was built with how it is evaluated, and says where the evaluation stops.

---

### Featured

#### [Faultline NOC](https://github.com/soneeee22000/faultline-noc): a router over three specialist agents, scored before it can touch a network

- **Built:** a typed `RoutePlan` contract (ordered steps, per-step context, which step may write and whether it needs confirmation). The routers are a keyword baseline and two Claude models answering through a forced tool call, from a prompt frozen by SHA-256. They sit on a seeded, simulated 5G SA core.
- **Evaluated by:** 4 deterministic detectors (misroute, missing handoff, unsafe write, missed clarification) plus set-level metrics. The harness is itself tested: 4 mutant routers each carry one planted defect and must trip their own detector. CI replays every recorded model call with no API key.
- **Numbers:** Claude Haiku 4.5 and Sonnet 5 each got 45/52 exact routes; the keyword baseline got 40/52. The intervals overlap, so this is a comparison, not a quality claim.
- **Limits:** the 52 items were written by me, with one recorded answer per model per item.

[Design note](https://faultline-noc.vercel.app/#router) · [Project page](https://faultline-noc.vercel.app) · [Repo](https://github.com/soneeee22000/faultline-noc)
`Python` `pydantic` `mypy --strict` `pytest` `Anthropic tool use`

#### [Agentic game generator](https://github.com/soneeee22000/cartridge): an explicit workflow graph with a two-tier evaluator

- **Built:** a Mastra workflow with typed Zod step I/O. It plans, then runs generate → verify in a loop, then finalizes or rejects. The repair loop is capped at 3, and each failure is attributed to the step that produced it.
- **Evaluated by:**
  - E1: 24 deterministic contract rules
  - E2: a Playwright runtime probe with 6 detectors
  - E3: a cited judge, where each finding must quote a real line
  - E4: a language-match check
- **Numbers:** 20 of 20 authored prompts produced a game. 9 of the 20 games passed every static rule and still failed at runtime (E2 passed 11 of 20), so passing static checks does not make a game work.
- **Limits:** one generation per item, and I wrote the prompts.

[Live demo (replayed model calls)](https://cartridge-engine.vercel.app) · [Repo](https://github.com/soneeee22000/cartridge)
`TypeScript` `Mastra` `Zod` `AI SDK` `Playwright` `Vitest`

#### [AgentPulse](https://github.com/soneeee22000/agentpulse): real-time observability for agent runs

- **Built:** one Zod event contract with 7 event types, checked at ingest and in the browser. An event bus with memory, Pub/Sub and Kafka drivers. A 60 s rolling aggregator (p50/p95, error rate, cost). SSE and GraphQL subscriptions feeding a span waterfall.
- **Evaluated by:** 76 Vitest tests across contracts, percentiles, window eviction, projection and the bus drivers. It is a dashboard, so there is no benchmark.
- **Limits:** the demo traffic is simulated, not produced by real agents, and state is held in memory only.

[Live demo](https://agentpulse-web-171722935814.europe-west1.run.app) · [Repo](https://github.com/soneeee22000/agentpulse)
`TypeScript` `Fastify` `Vue 3` `Kafka` `Pub/Sub` `Cloud Run`

#### [WikiHow-MY](https://github.com/soneeee22000/wikihow-mt-my): English→Myanmar MT, a fine-tune, and a metric that fails

- **Built:** about 10K post-edited pairs with article-disjoint splits (asserted in code), and an NLLB-200 600M fine-tune.
- **Evaluated by:** a 4-system benchmark (chrF++, spBLEU, COMET, MetricX-24) with a FLORES+ control, plus a human study: 9 raters gave 420 followability ratings.
- **Numbers:** the fine-tune gains +5.63 chrF++ in domain and +4.33 chrF++ on FLORES+.
- **The metric fails:** my own IFS metric correlates with human followability at r = 0.084, and I report that negative result.

[Repo](https://github.com/soneeee22000/wikihow-mt-my) · [HF weights](https://huggingface.co/PyaeSoneK/nllb-600m-wikihow-en-my)
`Python` `Transformers` `NLLB-200` `COMET` `MetricX-24`

#### Also built

- [AgentProbe](https://github.com/soneeee22000/AgentProbe): a ReAct agent written from scratch, with a deterministic failure taxonomy and a multi-model benchmark.
- [Knowledge-Graph RAG Explorer](https://github.com/soneeee22000/Knowledge-Graph-RAG-Explorer): GraphRAG stages on a canvas, with a retrieval eval comparing vector-only and graph-expanded search. [Demo (mock mode)](https://knowledge-graph-rag-explorer.vercel.app)
- [AgentCanvas](https://github.com/soneeee22000/agentcanvas): a Vue Flow studio for composing agent workflows, with step-level run visibility. [Demo (mock mode)](https://agentcanvas-demo.vercel.app)
- [VaxEvidence](https://github.com/soneeee22000/VaxEvidence-Dev): a real-world-evidence platform for vaccine research (PICO, PRISMA, RoB 2, meta-analysis, regulatory exports). [Live demo](https://vaxevidence-dev.vercel.app/demo)
- [EV charging copilot](https://github.com/soneeee22000/electra-charging-copilot): a tool-grounded RAG assistant; every station, price and route comes from a tool call, never from the model.
- [FaceProof](https://github.com/soneeee22000/faceproof): face verification and liveness detection, measured on the LFW protocol.
- SpeakProof: a TOEFL speaking-practice bot inside Telegram, used by learners in Myanmar.

Data and back-end range: [GridFlex](https://github.com/soneeee22000/gridflex) (AWS grid lakehouse), [CSRD Lake](https://github.com/soneeee22000/csrd-lake) (Snowflake + dbt), [CDR pipeline](https://github.com/soneeee22000/cdr-pipeline) and [Diameter credit-control](https://github.com/soneeee22000/diameter-cc) (Java 21, Spring Boot 3.5, Kafka).

---

### Experience

| When                | Role                                                        | Where                  |
| ------------------- | ----------------------------------------------------------- | ---------------------- |
| May 2026 – Sep 2026 | Freelance AI Engineer, Hoora Games (SAS EASYWIN)            | Metz, France (remote)  |
| Jun 2025 – May 2026 | Full-Stack AI Engineer, Siloett.AI                          | Station F, Paris       |
| Jul 2024 – Dec 2025 | Data Science / Cloud Data Engineer, Floware                 | Station F, Paris       |
| Jan 2023 – Jul 2024 | Research & Back-End Engineer, AIT BrainLab → DiCE Lab       | Bangkok → Paris        |
| Jan 2021 – Dec 2022 | Software Engineer (Web), FAO (UN Food and Agriculture Org.) | Yangon (remote/hybrid) |

At Hoora, I owned the evaluation and quality-gating layer end to end, and worked across the Mastra agent graph, its tool contracts and multilingual behaviour. The agentic game generator above is my independent design of the full pipeline.

### Education

- **MSc Data Science and Network Intelligence**, Télécom SudParis (Institut Polytechnique de Paris)
- **MSc Data Science and AI**, Asian Institute of Technology

### Stack

- **Languages:** Python · TypeScript · Java · SQL
- **AI:** Anthropic / Claude · Mastra · LangGraph · Hugging Face · PyTorch
- **Back end:** FastAPI · Fastify · Spring Boot · Kafka · PostgreSQL
- **Cloud:** GCP Cloud Run · Azure · AWS · Docker · GitHub Actions
