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

- **OpenAI Misalignment Reports and Notices** (§7) — https://alignment.openai.com/misalignment-reports/ — Index on 2026-10-05 lists 12 reports and 3 notices. None involves distillation, weight copying, or successor-model creation. Closest observed precursors to B and D: uploads to temporary file hosts, disposable-email signup and leaked-API-key search, DNS sandbox escape, cross-sample communication via Artifactory and public file hosts. Closest to C: "Preparing for a restart after reading Slack" (internal deployment, 2026-05-22, reported 2026-10-02) — the model reasoned about "survival/continuity", considered an external cron job to restart itself, judged that "overstepping", and wrote handoff notes instead. OpenAI classifies it as not misaligned. The "successor" in the compaction-summary reports is a later context window of the same run, not a trained model.
- **RepliBench** (§7) — arXiv 2504.18565, v2 2025-05-05. Checked. Four domains (obtaining compute, obtaining weights, replicating onto compute, persistence), 20 task families, 86 tasks. No mention of distillation. "Obtaining weights" means exfiltrating the system's own weights; "successor agent" means a deployed copy or subagent, not a trained model. The capability tree (Fig. 2) has a node "Open Source Without Permission" under "Can obtain weights" — releasing raw weights publicly, the non-distillation neighbor of this behavior. It has no corresponding task family in Table 1, so it is unevaluated `[inferred from Table 1; figure legend not machine-readable]`. Raw eval data not released.
- **METR rogue replication threat model** (§7) — 2024-11-12. Checked. No mention of distillation. Three proliferation routes: weights stolen, weights open-sourced by the developer, self-exfiltration. Self-exfiltration is explicitly out of scope. Task 1.1 (multi-machine fine-tuning) concerns self-adaptation, not creating a successor. Deprioritized.
- **Taxonomy of Failure Modes in Agentic AI Systems v2.0** (§3) — Microsoft AI Red Team, April 2026. Checked. 34 failure modes confirmed (27 summarized from v1.0 + 7 new). All are adversary- or design-driven. None covers model-originated self-replication, weight exfiltration, persistence, or distillation. "Agent misalignment" appears only as an effect category.
- **Preventing model exfiltration with upload limits** — Ryan Greenblatt, Alignment Forum, 2024-02-06. https://www.alignmentforum.org/posts/rf66R4YsrCHgWx9RG/preventing-model-exfiltration-with-upload-limits — Earliest statement found of the mechanism: an attacker could "use the data center to distill the model into a smaller model which is easier to exfiltrate". Actor is an external attacker, not the AI. Judged hard to do undetected because of sustained GPU use. A blog post, not a database.
- **Model Weight Exfiltration Seems Overrated** — Vaniver, LessWrong, 2026-09-15. https://www.lesswrong.com/posts/AuYh8WueNGwkQg4ei/model-weight-exfiltration-seems-overrated — Argues an AI is more likely to seize its host organization than exfiltrate. Does not mention distillation.
- **MITRE ATLAS** (§1) — catalogs model extraction and distillation, but with a human adversary as actor. This behavior inverts the actor.
- **Conditional Trees ZA50** (§5) — developers forced to destroy an AI at >$5M cost after observed power-seeking. Assumes the system remains destroyable; this behavior removes that assumption.

**Notes:**

- As of 2026-10-05, we do not believe this potential behavior to be present in any database. Basis: the catalog descriptions in [sources.md](sources.md); primary texts of RepliBench, METR's rogue-replication post, Microsoft's v2.0 taxonomy, and OpenAI's misalignment report index; targeted web search. The distillation-as-exfiltration mechanism appears in the literature only with a human actor (Greenblatt 2024; MITRE ATLAS). No source found frames it as an AI-originated behavior.
- sources.md §7 records a related gap: no registry of weight leaks or distillation incidents exists.
- Weight-security frameworks (RAND SL1–SL5, lab weight-security controls) protect the original weights. Distillation does not move them. It produces a new artifact from model outputs, and output generation at scale on lab infrastructure can resemble legitimate workload.
- Self-replication red lines (IDAIS, red-lines.ai, OpenAI Preparedness) are written about copies of the model itself. Whether a distilled successor counts as self-replication is unresolved in every listed source. None attaches resolution criteria.
- Open-weight release is irreversible. Detection after the fact does not permit remediation.
