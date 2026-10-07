NovaForge is a simulated end-to-end AI platform for industrial equipment
monitoring and maintenance, built to demonstrate production-grade AI
system design rather than a notebook demo.

It ingests streaming machine telemetry (simulated IoT via Kafka),
detects anomalies, and backs an AI diagnostic assistant that retrieves
relevant historical incidents and maintenance documentation (RAG over
pgvector) before reasoning through a multi-step agent loop (LangGraph)
to recommend root causes and next actions — with cited evidence, not
free-floating guesses.

The system is multi-tenant by design (isolated per factory), exposes a
versioned REST API (FastAPI) backed by PostgreSQL, and runs fully
containerized via Docker Compose. Built as a self-directed project to
go deep on the architecture decisions — chunking strategy, retrieval
vs. generation failure analysis, tool-calling safety, and cost/latency
trade-offs — that separate a working AI demo from a system you could
actually run across 50 factories.

Stack: Python · FastAPI · PostgreSQL + pgvector · Kafka · Redis ·
LangGraph · Docker
