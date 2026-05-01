[option-D-tech-only.md](https://github.com/user-attachments/files/27279444/option-D-tech-only.md)
<h1>Julio Juárez</h1>

<p>
  <code>backend · ai · infra · cdmx 🇲🇽</code><br/>
  Production systems en Go, React e IA aplicada.
</p>

---

### Stack que uso a diario

#### 🧱 Backend

- **Go** — mi lenguaje principal. Chi para routing, Huma v2 para APIs typed con OpenAPI auto-generado, River para job queues sobre Postgres (sin Redis), context everywhere, cero pánico en producción.
- **PostgreSQL** — particionado por mes, índices funcionales, CopyFrom para ingestas de 15M+ filas en minutos, pgvector para embeddings, JSONB cuando vale la pena.
- **Redis** — cache + pub/sub. Solo cuando Postgres ya no alcanza.
- **gRPC + Protobuf** — comunicación entre servicios internos.

#### 🎨 Frontend

- **React 19** con Suspense + concurrent rendering. Server Components donde aplica.
- **Vite** para bundling rápido. **Astro** para landings estáticas con Core Web Vitals 95+.
- **TypeScript estricto** — `strict: true`, `noUncheckedIndexedAccess`, sin `any`.
- **Tailwind + design tokens** en CSS custom properties.

#### 🧠 IA / LLMs en producción

- **Claude API** (Anthropic) — mi principal. Function calling, prompt caching para 90% menos costo, batching cuando aplica.
- **Gemini API** (Google) — multimodal y precio agresivo en 1.5 Flash.
- **RAG sobre datos estructurados** — no solo PDFs. Embeddings en Postgres + retrieval híbrido (vectores + filtros SQL).
- **Fallbacks entre modelos** — si Claude se cae, Gemini responde. Si los dos se caen, respuesta cacheada del último ok.

#### 🚢 Infraestructura

- **Kubernetes** — K3s self-hosted para entornos pequeños, GKE para producción seria.
- **GCP** — GKE, Cloud SQL, Cloud Storage, Application Default Credentials para auth limpia.
- **AWS** — Amplify + CloudFront para frontends estáticos, S3 + Lambda donde aplica.
- **Docker + GitHub Actions** — CI/CD sin sufrir.
- **Cloudflare** — proxy + cache + WAF.

#### 🔧 Datos

- **SQL avanzado** — window functions, CTEs recursivos, query plans, cuando un índice salva el día.
- **CDC** con Debezium / lógica custom en Postgres (logical replication).
- **ETL** — Python para scripting one-shot, Go para pipelines en producción.
- **BigQuery** — warehouse cuando los datos pasan los 100GB.

#### 🛠 Daily drivers

```yaml
editor:    cursor + vscode
shell:     zsh + tmux
terminal:  ghostty
ai_tools:  claude code · cursor agent · github copilot
sketches:  excalidraw · figma cuando la cosa va a producción
notes:     obsidian (vault local, sync con git)
when_angry: bash + grep + sed + awk
```

---

### Cómo programo

- **Build less. Ship faster.** Cada línea es liability — pensar antes de escribir.
- **No premature abstraction.** Tres líneas similares > un mal abstract.
- **Validar en bordes**, confiar adentro. No defensive code para casos imposibles.
- **Idempotencia** en todo lo async. Si el job corre dos veces, no pasa nada.
- **Si está en mi código, lo he debuggeado a las 3 AM.**

---

### Lo que más me prende

- LLMs en producción real (no demos), con costo controlado y fallbacks de verdad.
- Postgres exprimido al máximo antes de meter Redis o un vector DB nuevo.
- Sistemas async confiables con River + outbox pattern.
- Frontend rápido. Si el LCP pasa de 2s, algo está mal.

---

<sub>📍 CDMX · 📬 jcjuarezm1@gmail.com · 🐦 [@InsaneTreset](https://x.com/)</sub>
