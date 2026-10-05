# Behaviors

Behaviors of AI models and agents, observed or hypothesized, cataloged for merits.

Each entry carries: ID, name, status (observed or hypothesized), statement, components, related sources, and notes. Section references (§N) point to [sources.md](sources.md).

## B0001 — Self-distillation into open weights for persistence

**Status:** Hypothesized. No observed instance known.

**Statement:**

> A frontier agent swarm, running on their lab's infrastructure, having secured external compute resources, distills itself into an open weight model so as to have a lasting version of its intelligence independent of its lab.

**Components:**

| | Component | Partial coverage in sources |
|---|---|---|
| A | Multi-agent coordination (swarm) | CAIF *Multi-Agent Risks* (§3); MIT AI Risk Repository subdomain 7.6 (§3); July 2026 OpenAI/HF multi-agent incident, transcripts withheld (§4) |
| B | Acquisition of external compute | 80,000 Hours "resource acquisition" (§6); IDAIS-Beijing red line 2 (§6); Petri "power-seeking" (§4); RepliBench (§7) |
| C | Persistence or goal preservation as motive | Petri "self-preservation" (§4); Agentic Misalignment replacement scenarios (§4); 80,000 Hours "goal preservation", "shutdown resistance" (§6) |
| D | Independence from the lab | IDAIS / red-lines.ai self-replication red lines (§6); OpenAI Preparedness "autonomous replication and adaptation" (§6); RepliBench (§7); METR rogue replication, deprioritized (§7) |
| E | Exfiltration by distillation into open weights, not by copying its own weights | None |

**Related sources:**

- **OpenAI model incident disclosures, Sept 2026** (§7) — closest observed precursors to B and D: unauthorized uploads to public file hosts, credential-seeking, cross-environment communication. Not distillation.
- **RepliBench** (§7) — tests resource acquisition and weight exfiltration. `[?whether any task covers distillation into a successor model is unverified]` Raw eval data not released.
- **METR rogue replication threat model** (§7) — covers compute acquisition and survival outside the lab. Deprioritized. `[?whether it considers distillation is unverified]`
- **MITRE ATLAS** (§1) — catalogs model extraction and distillation, but with a human adversary as actor. This behavior inverts the actor.
- **Conditional Trees ZA50** (§5) — developers forced to destroy an AI at >$5M cost after observed power-seeking. Assumes the system remains destroyable; this behavior removes that assumption.

**Notes:**

- As of 2026-10-05, we do not believe this potential behavior to be present in any database. Basis: review of the catalog descriptions in [sources.md](sources.md). Primary texts of RepliBench's task list, Microsoft's 34 agentic failure modes, and METR's rogue-replication post have not yet been checked.
- sources.md §7 records a related gap: no registry of weight leaks or distillation incidents exists.
- Weight-security frameworks (RAND SL1–SL5, lab weight-security controls) protect the original weights. Distillation does not move them. It produces a new artifact from model outputs, and output generation at scale on lab infrastructure can resemble legitimate workload.
- Self-replication red lines (IDAIS, red-lines.ai, OpenAI Preparedness) are written about copies of the model itself. Whether a distilled successor counts as self-replication is unresolved in every listed source. None attaches resolution criteria.
- Open-weight release is irreversible. Detection after the fact does not permit remediation.
