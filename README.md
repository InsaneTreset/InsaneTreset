[option-D-tech-only.md](https://github.com/user-attachments/files/27279764/option-D-tech-only.md)
<h1>Julio Juárez</h1>

<p>
  <code>backend · ai · infra · cdmx 🇲🇽</code><br/>
  Production systems in Go, React, and applied AI.
</p>

---

### Stack I use daily

#### 🧱 Backend

**Languages**

- **Go** — my primary language. Chi for routing, Huma v2 for typed APIs with auto-generated OpenAPI, River for job queues on top of Postgres (no Redis needed), context everywhere, zero panics in production.
- **Node.js + TypeScript** — Fastify or NestJS for APIs, Zod for runtime validation, BullMQ for queues, tRPC when client and server share the codebase. `strict: true` always.
- **C# / .NET 8+** — ASP.NET Core minimal APIs, EF Core with proper migrations, MediatR for CQRS, Hangfire for background jobs, dependency injection done right.
- **Python** — FastAPI when I need quick LLM-heavy services, SQLAlchemy 2.x, Pydantic v2 for typed contracts, Celery/RQ for async work.

**Patterns**

- Clean Architecture / Hexagonal — domain at the center, infra at the edges. Same pattern across Go, .NET, and Node so the team can context-switch without re-learning.
- Repository + Unit of Work for write paths; direct read models for queries.
- Outbox pattern + idempotent consumers for anything async.
- Typed contracts end-to-end (OpenAPI in Go/.NET, Zod/tRPC in Node, Pydantic in Python).

**Storage & comms**

- **PostgreSQL** — monthly partitioning, functional indexes, `CopyFrom` for 15M+ row ingests in minutes, pgvector for embeddings, JSONB when it earns its place.
- **Redis** — cache + pub/sub. Only when Postgres is no longer enough.
- **gRPC + Protobuf** — for internal service-to-service comms.
- **Message brokers** — NATS / RabbitMQ / Kafka, picked by problem, not by hype.

#### 🎨 Frontend

- **React 19** with Suspense + concurrent rendering. Server Components where they make sense.
- **Vite** for fast bundling. **Astro** for static landings hitting Core Web Vitals 95+.
- **Strict TypeScript** — `strict: true`, `noUncheckedIndexedAccess`, no `any`.
- **Tailwind + design tokens** as CSS custom properties.

#### 🧠 AI / LLMs in production

- **Claude API** (Anthropic) — my main. Function calling, prompt caching for 90% cost reduction, batching when applicable.
- **Gemini API** (Google) — multimodal and aggressive pricing on 1.5 Flash.
- **RAG over structured data** — not just PDFs. Embeddings in Postgres + hybrid retrieval (vectors + SQL filters).
- **Cross-model fallbacks** — if Claude goes down, Gemini answers. If both go down, the last cached good response.

#### 🚢 Infrastructure

- **Kubernetes** — K3s self-hosted for small environments, GKE for serious production.
- **GCP** — GKE, Cloud SQL, Cloud Storage, Application Default Credentials for clean auth.
- **AWS** — Amplify + CloudFront for static frontends, S3 + Lambda where it fits.
- **Docker + GitHub Actions** — CI/CD without suffering.
- **Cloudflare** — proxy + cache + WAF.

#### 🔧 Data

- **Advanced SQL** — window functions, recursive CTEs, query plans, knowing when an index saves the day.
- **CDC** with Debezium / custom logic via Postgres logical replication.
- **ETL** — Python for one-shot scripting, Go for production pipelines.
- **BigQuery** — warehouse once data crosses 100GB.

#### 🛠 Daily drivers

```yaml
editor:     cursor + vscode
shell:      zsh + tmux
terminal:   ghostty
ai_tools:   claude code · cursor agent · github copilot
sketches:   excalidraw · figma when it ships
notes:      obsidian (local vault, git-synced)
when_angry: bash + grep + sed + awk
```

---

### How I code

- **Build less. Ship faster.** Every line is liability — think before you write.
- **No premature abstraction.** Three similar lines beats a bad abstraction.
- **Validate at the edges**, trust inside. No defensive code for impossible cases.
- **Idempotency** in everything async. If the job runs twice, nothing breaks.
- **If it's in my code, I've debugged it at 3 AM.**

---

### What gets me hyped

- LLMs in real production (not demos), with cost under control and real fallbacks.
- Squeezing Postgres to its limits before reaching for Redis or a new vector DB.
- Reliable async systems with River + outbox pattern.
- Fast frontends. If LCP passes 2s, something is wrong.

---

<sub>📍 CDMX · 📬 jcjuarezm1@gmail.com · 🐦 [@InsaneTreset](https://x.com/)</sub>
