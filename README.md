# TraceGuard

**A privacy-first observability layer for OpenLLMetry-based AI agent traces.**

TraceGuard sits on top of [OpenLLMetry](https://github.com/traceloop/openllmetry)
and adds the PII redaction, policy modes, and audit tooling that regulated
industry deployments (fintech, healthtech, legaltech) need before they can
turn on full GenAI tracing in production.

> **Status: Pre-development (design phase).** Implementation begins June 2026.
> The current artifact is the [design document](docs/PRD.md) — code lands as
> v0.1 by end of July 2026.

## What it does (planned for v0.1)

- **PII redaction** on prompts, completions, and tool call arguments
  before any OTLP exporter sees them
- **Three policy modes** — `strict` / `balanced` / `debug`
- **Diff CLI** — `traceguard diff <trace_id>` to audit what was redacted
- **Drop-in install** — change one import line; the rest of your
  OpenLLMetry / OTel setup is untouched

## Why this exists

OpenLLMetry captures full prompt and completion content by default. The
only toggle is `TRACELOOP_TRACE_CONTENT=true|false` — binary. Regulated
teams need selective redaction with an audit trail, not on/off.

Full motivation and competitive analysis in [docs/PRD.md](docs/PRD.md).

## License

Apache 2.0 — see [LICENSE](LICENSE).
