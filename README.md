# System Design Posters

Single-sheet reference posters on system design, distributed systems, data infrastructure and
AI engineering — each one dense enough to work as a desk reference rather than a summary.

Every poster ships in three forms:

| File | What it is |
|---|---|
| `*.pdf` | Vector, one page. Zooms indefinitely without pixelation — **use this one** |
| `*.png` | High-resolution raster, rendered from the PDF |
| `*.source.html` | The HTML the poster is generated from, so it can be edited and re-rendered |

---

## Roadmaps & Guides

Two learning roadmaps sharing a layout — a map of numbered branches grouped into themes, then an
expanded card per branch — and an end-to-end operations guide.

| | Poster | Covers |
|---|---|---|
| 🗺️ | **[System Design — Learning Roadmap](System_Design_Roadmap_Mindmap/)** | 20 branches in six themes. Fundamentals and estimation, networking and protocols, API design, data stores, storage engines, caching, distributed fundamentals, consensus and coordination, scaling, partitioning, load balancing and gateways, resilience patterns, architectural styles, distributed transactions, messaging and event streaming, IAM, observability, algorithms for system design, delivery and cost. Plus a framework for approaching design problems and practice problems grouped by pattern. |
| 🔧 | **[DevOps — Learning Roadmap](DevOps_Roadmap_Mindmap/)** | 20 branches in five themes, with tools for each. Linux and networking, version control, cloud fundamentals, CI, testing, artifacts and supply chain, CD and GitOps, IaC, configuration management, containers, Kubernetes, deployment strategies, observability, SRE and incident response, capacity and FinOps, DevSecOps, platform services, platform engineering, database operations. Plus twelve practice projects in order and career paths. |
| 🚀 | **[Deployment Architecture & Operations Guide](Deployment_Architecture_And_Operations/)** | A reference deployment architecture drawn as trust and network boundaries, the pipeline stage by stage, environments and promotion, deployment strategies, database and data migrations, zero-downtime mechanics, rollback and recovery, configuration and secrets, what to decide per system, resource estimation, HA/DR/backup, vulnerability and patch management, and a before/during/after checklist. |

## Architecture & Distributed Systems

| | Poster | Covers |
|---|---|---|
| 🔀 | **[Kafka — Architecture & Configuration](Kafka_Architecture_And_Configuration/)** | Cluster architecture and KRaft, the log storage model, replication and ISR, write and read paths, consumer groups and liveness, the durability model, producer / consumer / topic configuration, configuration profiles per use case, exactly-once, security and sizing, and the misconfigurations that reach production. |
| ⚡ | **[Circuit Breaker Framework in Java — Resilience4j](Circuit_Breakers_In_Java/)** | The six circuit breaker states, how the open decision is actually made, sliding window sizing, the decorator order (`Retry → CircuitBreaker → RateLimiter → TimeLimiter → Bulkhead`), working synchronous and asynchronous code, fallbacks, metrics, testing, and eighteen production traps. |
| 🗄️ | **[Columnar Databases](Columnar_Databases/)** | Physical file anatomy (file → row group → column chunk → page), encodings vs compression codecs, data skipping and why sort order decides everything, vectorized execution, partitioning, the write path and table formats, and a worked query end to end. |
| 🛒 | **[Recommendation Engine — System Design](Recommendation_Engine/)** | Item-to-item collaborative filtering, two-stage candidate generation and ranking, embeddings and ANN, cold start, training data and position bias, evaluation, and failure modes. |

## AI Engineering

| | Poster | Covers |
|---|---|---|
| 📚 | **[RAG Explained](RAG/)** | Opens with what RAG is and why it exists — the four steps, a worked example, the problems it solves, and when it is the wrong tool. Then the production pipeline: chunking, hybrid retrieval and reciprocal rank fusion, reranking, vector index internals, evaluation, a pattern ladder from simple to advanced, latency and cost, and security and multi-tenancy. |
| 🧩 | **[AI Engineering Projects](AI_Engineer_Projects/)** | A portfolio built as five sequenced projects — production RAG, local inference, observability, fine-tuning, real-time voice — with evaluation as the spine, repository standards, what fails review, and acceptance criteria. |
| 🎛️ | **[Production Multimodal Agent Architecture](Multimodal_Agent_Architecture/)** | A multimodal agent worked through motor claim triage: multimodal ingestion, agent loop control, guardrails, threat model, hallucination control, token and cost engineering, accuracy and evaluation, and graceful degradation. |
| 🏦 | **[Real Agentic AI — Banking Customer Service](Real_Agentic_AI_Banking_Customer_Service/)** | Taking an agentic assistant from demo to production inside a bank: multi-agent design, MCP, delegated authorization, memory, hybrid LLM and data residency, prompt injection, evaluation, observability, cost, and seventeen production gaps. |
| 🚚 | **[Real Agentic AI — GPS & Fuel Monitoring](Real_Agentic_AI_GPS_Fuel_Monitoring/)** | A privacy-preserving telematics support agent: the context-handle pattern and its limits, MCP tool contracts, telemetry ingestion, domain semantics, offline diagnosis, fuel analytics, safety-critical actions, and eighteen design traps. |

---

## How these are built

Each poster is hand-written HTML and inline SVG, rendered through Chrome headless to a
single-page vector PDF, then rasterized from that PDF to PNG.

The PNG is generated **from the PDF**, not by screenshotting the page. Chrome's screenshot
rasterizer silently truncates tall pages at high device-scale-factor, which produced partially
blank images for three posters before the pipeline was changed — see commit `0fcbd22`.

## Notes

- Posters are self-contained. No external fonts, scripts or images.
- Where a claim comes from a specification, standard or regulation, the poster names it, so it
  can be checked against the source rather than taken on trust.
- Figures that are workload-dependent — compression ratios, speed-ups, latency budgets — are
  presented as illustrative with the reasoning shown, not asserted as fact.
- `Recommendation_Engine` predates the convention of shipping `*.source.html` and has PDF and
  PNG only.
