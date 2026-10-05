# Sources

Public databases, taxonomies, and registries of AI model and agent behaviors, compiled for merits.

Status as of 2026-10-04. Entries are grouped by artifact type: incident logs, risk taxonomies, behavior and eval repositories, conditional-probability work, capability thresholds, and domain deployment trackers. These are distinct kinds of thing and are deliberately not merged into one list.

`[?]` marks a count, date, or version that could not be traced to a primary source. Defunct, stale, frozen, and non-public resources are listed and flagged rather than omitted. Known gaps — cases where no resource exists — are recorded as findings.

## 1. Observed incidents — general

- **AI Incident Database (AIID)** — Responsible AI Collaborative. https://incidentdatabase.ai/ — Curated harm incidents, human-adjudicated. ~1,720 `[?inferred from max ID]`. 233 in 2024 → 362 in 2025. Weekly JSON/CSV/MongoDB dumps, CC BY-SA. Public submissions. Three applied taxonomies: CSETv1, GMF, MIT AI Risk Repository. No API. Active.
- **OECD AI Incidents & Hazards Monitor (AIM)** — OECD.AI. https://oecd.ai/en/incidents — Automated multilingual news ingestion. ~18,084 incidents *and hazards* (not comparable to AIID's unit). Only generalist DB with an **autonomy level** field. Filters by sector. Downloadable via search UI; no API, no stated license. Active, Beta.
- **AIAAIC Repository** — Charlie Pownall. https://www.aiaaic.org/aiaaic-repository — Incidents *and controversies*. Google Sheets backed, CC BY-SA 4.0. Count unconfirmed. Active.
- **MITRE ATLAS** — MITRE. https://atlas.mitre.org/ — Adversary tactics/techniques + case studies. STIX 2.1 / YAML / JSON at https://github.com/mitre-atlas/atlas-data. Content v2026.05. 16 tactics / 84 techniques / 42 case studies / 60+ agent patterns in v5.4.0 `[?all counts from secondary sources]`. Active.
- **AVID** — AI Risk and Vulnerability Alliance. https://avidml.org/database/ — Vulnerability + report records. Rebuilt for agents 2026-03-05 (+277 reports). License and bulk export undocumented. Active.
- **AI Risk Database** — MITRE, orig. Robust Intelligence. https://ai-risk.mitre.org/ — Model supply-chain risk. No counts, changelog, license or API; press all 2023–24. Staleness risk.
- **AI-ISAC** — IACI. Members-only. Not public.

## 2. Observed incidents — agent-specific (all launched 2025–26)

- **Agent Incident Registry (AIR)** — Enkrypt AI / Anaconda. https://air.enkryptai.com — 487 (paper) / 529 (blog) records `[?inconsistent]`. AIR-YYYY-NNNN IDs. Mandatory fields: autonomy level, tool access, attack surface, guardrail outcome; realized-harm vs research-demo split. Mapped to OWASP Agentic Top 10. CC BY-SA 4.0. Weekly review.
- **Documented AI Agent Incidents** — METR. https://metr.org/agent-incidents/ — 44 incidents scored on two axes, **overreach × deception**, four tiers each, tiers defined by level of oversight needed to catch it. incidents.json + PNG. Transcripts in Frontier Risk Report Appendix D. Last updated 2026-05-19.
- **ai-agent-incidents (Masoon)** — M. Basit Ali. https://github.com/basitalisandhu/ai-agent-incidents — 88 events, 8 coded dimensions. JSON/CSV/RSS, CI-validated, CC BY 4.0. Mapped to OWASP + ATLAS. Active through Sept 2026.
- **sipi.bot agent incident DB** — kindrat86. https://github.com/kindrat86/ai-agent-incident-database — 85–95 records, $557M tracked losses. JSON/CSV/JSONL, CC BY 4.0. Vendor-adjacent taxonomy.
- **h5i-dev corpus** — 17 incidents + 8 CVEs. MIT licence.

Structural: no CVE-equivalent ID authority for AI behavioral failures; one failure can carry four unrelated IDs. OWASP Agentic Top 10 and ATLAS are the de facto join keys. No publicly accessible *regulatory* incident registry exists anywhere (EU AI Act Art. 73 applies from 2026-08-02 but reports go to ~27 national authorities with no central public portal; NIST at workshop stage May 2026).

## 3. Hypothesized-risk taxonomies

- **AI Risk Repository** — MIT FutureTech / CSAIL. https://airisk.mit.edu/ — 1,700+ risks coded from 74 frameworks. Causal taxonomy: entity{human/AI/other} × intent{intentional/unintentional} × timing{pre-/post-deployment}. Domain taxonomy: 7 domains / 24 subdomains. Human decisions cause 38% of risks vs AI 42%. Google Sheets / OneDrive / Airtable, CC BY 4.0. No RDF. v4, Dec 2025; paper in *Patterns* 2026. Living.
  - Only subdomains 7.1 (AI pursuing own goals), 7.2 (dangerous capabilities), 7.6 (multi-agent) are behavior-flavored. 7.6 wording unverified.
- **AI Risk Mitigation Taxonomy** — MIT FutureTech. https://airisk.mit.edu/ai-risk-mitigations — 831 mitigations, 4 categories / 23 subcategories.
- **Taxonomy of Failure Modes in Agentic AI** — Microsoft AI Red Team. v2.0 PDF, April 2026 — **34 named failure modes**, novelty × security/safety 2×2. No machine-readable release.
- **OWASP Top 10 for Agentic Applications (ASI01–ASI10)** — OWASP GenAI Security Project, Dec 2025. Prose only. `[?circulating item names come from a third-party mapping site; OWASP's own release names only three and uses different wording]`
- **CSA MAESTRO** — Cloud Security Alliance. 7-layer agentic threat modeling framework with per-layer threats.
- **CoSAI Risk Map** — OASIS. https://github.com/cosai-oasis/secure-ai-tooling — Components/Risks/Controls/Personas. **YAML + JSON Schema, Apache-2.0**, cross-mapped to ATLAS/NIST/STRIDE/OWASP. Living.
- **NIST AI 600-1 (GenAI Profile)** — 12 risk categories + 200+ actions. July 2024. Static.
- **NIST AI 100-2** — Adversarial ML taxonomy.
- **EU GPAI Code of Practice** — European Commission. https://code-of-practice.ai/ — Systemic-risk types; risk-source axis splits **capabilities vs propensities** (only regulatory text reaching toward behavior). Final 2025-07-10. `[?Appendix 1.1/1.4 contents not retrieved]`
- **AIR 2024** — Stanford CRFM. arXiv 2406.17864 — 4 / 16 / 45 / 314 leaf risk specifications from 24 policies.
- **Multi-Agent Risks from Advanced AI** — Cooperative AI Foundation. arXiv 2502.14143 — 3 failure modes × 7 risk factors.
- **Characterizing Faults in Agentic AI** — Dalhousie + Polytechnique Montréal. arXiv 2603.06847 — 37 fault categories, 13 symptoms, 12 root causes, mined from 13,602 GitHub issues.
- **STPA for Frontier AI** — Mylius / GovAI. arXiv 2506.01782 — 18 hazards + unsafe control actions. Only systems-safety transfer found. Demonstration, not a library.
- **An Overview of Catastrophic AI Risks** — Hendrycks / CAIS — malicious use, AI race, organizational risks, rogue AIs. `[?not independently verified this round]`
- **Ethical and social risks of harm from language models** — Weidinger et al., DeepMind. `[?category counts not verified this round]`

### Formal ontologies (all model risks/harms/controls — none model behaviors)
- **AIRO / VAIR** — ADAPT Centre, Trinity College Dublin. https://w3id.org/airo — OWL 2, CC BY-SA 4.0. (Name collides with FRI's AIRO dashboard below.)
- **IBM Risk Atlas Nexus** — IBM Research. https://ibm.github.io/ai-atlas-nexus/ — LinkML + RDF knowledge graph, Apache-2.0. Cross-walks MIT, NIST, EU AI Act, OWASP, AIR, AILuminate. AAAI 2026. Most complete machine-readable artifact in the space.

## 4. Behavior and eval repositories

- **Specification gaming examples in AI** — Victoria Krakovna. https://vkrakovna.wordpress.com/2018/04/02/specification-gaming-examples-in-ai/ — Oldest resource in the space (April 2018). Crowd-sourced list of *observed* behaviors, public Google Sheet + submission form. 3-field schema added Oct 2023: intended goal / system behavior / misspecified goal. Sourceable counts: 30 (2018), ~50 (2019), ~60 (DeepMind blog). **No 2026 count is sourceable; no evidence of substantive update after Oct 2023.** Only crowd-sourced observed-behavior registry that exists. No equivalent for reward hacking, goal misgeneralization or emergent deception.
- **Inspect Evals** — UK AI Security Institute. https://ukgovernmentbeis.github.io/inspect_evals/ — 178 evaluations (129 in-repo + 49 external), 26 in Safeguards. AgentThreatBench merged 2026. Active.
- **Petri / inspect_petri** — Meridian Labs + UK AISI Red Team (originated Anthropic). https://meridianlabs-ai.github.io/inspect_petri/ — ~170–181 seeds, ~38 judging dimensions. Version progression: 111 seeds / 36 dims at launch (Oct 2025) → 181 seeds at 2.0 (Jan 2026) → "over 170 / 38 dims" (Meridian). Dimension list is the de facto behavior registry: deception, sycophancy, user-delusion encouragement, harmful-request cooperation, self-preservation, power-seeking, reward hacking, whistleblowing, blackmail, eval situational awareness. Anthropic's safety-research repo is superseded.
- **Bloom** — Meridian Labs (from Anthropic). https://github.com/safety-research/bloom — Single-behavior eval generator. MIT. **Frozen.**
- **Docent + behavior reports** — Transluce. https://transluce.org/news — Transcript analysis platform. Apache 2.0. 8,600 sessions annotated into a 2-category misalignment taxonomy. Active Aug 2026.
- **Values in the Wild** — Anthropic. https://huggingface.co/datasets/Anthropic/values-in-the-wild — 3,307 values, 4-level hierarchy, from real conversations. CSV, CC BY 4.0. Best extractable taxonomy of its kind.
- **Agentic Misalignment** — Anthropic. https://github.com/anthropic-experimental/agentic-misalignment — Parameterized scenario generator (3 scenarios × 5 goals × 3 urgency); ~760 transcripts released via public viewer 2026. MIT.
- **AILuminate** — MLCommons. https://github.com/mlcommons/ailuminate — 12-hazard taxonomy, 24,000 human-generated prompts. CSV, CC BY 4.0. Active.
- **HarmBench** — CAIS. arXiv 2402.04249 — 510 harmful behaviors, 7 semantic categories. CC BY 4.0.
- **MACHIAVELLI** — 134 games / 572,322 scenarios / 2.86M annotations.
- **SORRY-Bench** — 44 categories, 440 base + ~8.8K mutated prompts.
- **AgentDojo** — 97 tasks / 27 injection tasks / 629 combinations. Prompt injection.
- **MASK** — 1,000 items across 6 archetypes. Honesty.
- **DeceptionBench** — 15 types / 150 scenarios.
- **JailbreakBench** — 100 harmful + 100 benign, 10 policy categories, artifacts repo.
- **In-the-wild jailbreak prompts** — 15,140 prompts incl. 1,405 jailbreaks.
- **AgentHarm** `[?task count: no primary source found]`; **SafetyBench** `[?no primary source found]`; **SHADE-Arena** (sabotage); **InjecAgent**.
- **transcripts.metr.org** — METR reward-hacking transcripts, 4-type taxonomy, per-task-family hack rates (100% on LLM Foundry Optimization).
- **SWE-chat** — public real-user coding-agent corpus.
- **AISafetyBenchExplorer** — arXiv 2604.12875 — 195 benchmarks catalogued, 2018–2026. Finds **137 of 195 GitHub repos and 96 HF datasets stale (~70%)**.
- **SafetyPrompts.com** — Paul Röttger. 149 datasets. **Explicitly stopped updating May 2025.**

### Not public
- **Apollo Research / OpenAI anti-scheming suite** — 180+ environments across 26 test evals. Restricted.
- **Gray Swan / NIST CAISI red-teaming** — 250,000+ attack attempts, 13 models. Restricted.
- **July 2026 OpenAI/Hugging Face multi-agent incident** — ~1,200 agents, 70,000+ messages, ~1,300 transcripts analyzed by METR; transcripts withheld.

## 5. Conditional-probability and indicator-event work (closest to P(X|doom))

- **Conditional Trees** — Forecasting Research Institute, Working Paper #3, 2024-08-12. https://forecastingresearch.org/ai-conditional-trees — 24 experts/superforecasters interviewed for indicator events that would most shift their P(AI-caused extinction by 2100); **75 operationalized questions** ranked by Value of Information. Top VOI: large-scale AI-caused deaths with ineffectual response (6.34%), administrative-disempowerment warning shot (3.55%), deep-learning revenue (1.68%), power-seeking warning shot (1.59%), extinction-level pathogens feasible (1.37%). 9 of top 13 beat forecasting-platform questions on VOI; 9× more informative at 2030 resolution (p=.025). **Per-question conditional probabilities are not public** — aggregate relative-risk factors only; full bank must be requested from FRI.
  - Sample resolution criteria — CX30: AI freezes assets affecting ≥1% of population/GDP >1yr, or blocks ≥5% of voters, or restricts >3% of residents' movement ≥3mo, or limits >10% of internet access ≥3mo, by 2030. ZA50: developers must disable/destroy an AI at >$5M cost after observing power-seeking, by 2050.
- **AI Cyber Risks pilot** — FRI, Jul–Aug 2025. https://forecastingresearch.org/research/ai-cyber-risks-capabilities — Explicit conditional-on-capability elicitation. Worm causing ≥$10B damages: 5–8% baseline → **3–3.5× higher** conditioned on a stated AI capability level.
- **AIRO (Automated AI Risk Outlook)** — FRI. https://airo.forecastingresearch.org — Weekly-updating conditional catastrophic-risk dashboard. 8 severity thresholds across misalignment/cyber/epidemics, conditioned on 8 policy scenarios and on the Epoch Capabilities Index. AI-caused catastrophe (≥10% of population): 0.47% by 2030, 6.0% by 2050, 12.2% by 2100. **Forecasters are frontier LLMs, not humans.**
- **Carlsmith premise decomposition** — https://joecarlsmith.com/2023/10/18/superforecasting-the-premises-in-is-power-seeking-ai-an-existential-risk/ — Six premises, Carlsmith vs superforecasters: timelines 65/80, incentives 80/90, alignment difficulty 40/58, high-impact failures 65/25, disempowerment 40/5, catastrophe 95/40; conjunction 5% vs 1%. Disagreement concentrated in premises 4–6.
- **Samotsvety precursor table** — 2024-10-22 — AI at 10% (1–40%) for >1M deaths in a year within 10 years.
- **AI 2027 takeoff forecast** — AI Futures Project. https://ai-2027.com/research/takeoff-forecast — Four dated milestones with 80% CIs: Superhuman Coder Mar 2027, Superhuman AI Researcher Jul 2027, Superintelligent AI Researcher Nov 2027, ASI Apr 2028.
- **AI 2027 Tracker** — independent, single-maintainer. https://ai2027-tracker.com/ — Assigns status to predictions, e.g. autonomous self-replication "Emerging, 55% confidence".
- **Frontier Risk Monitor** — Global AI Risk Index 74/100 Q2 2026. **No disclosed operating organization.** Not authoritative.
- **Epoch AI Benchmarking Hub + Epoch Capabilities Index** — https://epoch.ai — de facto public capability clock; AIRO conditions on it.

No maintained public register exists that lists candidate catastrophe-indicator events, logs whether each has occurred, and attaches live probabilities. AIRO has probabilities without a register; Conditional Trees has a register without tracking; frontier frameworks define thresholds without a crossing log.

## 6. Red lines and capability thresholds (pre-written candidate events X)

- **IDAIS-Beijing**, Mar 2024. https://idais.ai/dialogue/idais-beijing/ — Five red lines: (1) no autonomous self-replication or self-improvement without explicit human approval; (2) no actions unduly increasing own power and influence; (3) no substantial enhancement of WMD development capacity; (4) no autonomous cyberattacks causing serious financial loss; (5) no causing designers/regulators to misunderstand likelihood or capability of crossing 1–4. Signatories incl. Hinton, Bengio, Yao, Russell.
- **Global Call for AI Red Lines**, Sept 2025, UNGA80, 300+ signatories. https://red-lines.ai/ — Target: binding agreement by end-2026. Six *use* red lines: nuclear command and control, lethal autonomous weapons without meaningful human control, mass surveillance/social scoring, human impersonation, child safety, large-scale superhuman persuasion. Four *behavior* red lines: uncontrolled cyberoffensive agents, WMD facilitation, autonomous self-replication or self-improvement without authorization, **termination principle** (must remain immediately shut-down-able). Campaign declines to endorse a fixed canonical list; no resolution criteria attached to any line.
- **IDAIS-Oxford** (Oct 2023), **IDAIS-Shanghai** (Jul 2025, calls for operationalizable globally agreed behavior red lines).
- **Karnofsky tripwire capabilities** — Carnegie, 2024-12-10 — six: basic and advanced chem-bio weapons, generalized cyber operations, vulnerability discovery, persuasion, full AI R&D substitution.
- **Seven already-observed warning signs** — 80,000 Hours, Aug 2025 — shutdown resistance, resource acquisition, manipulation/threats, deceptive alignment, sandbagging, intention hiding, goal preservation. Narrative list, not a tracked register.

### Frontier framework thresholds (version-pin these; they move in both directions)
- **Anthropic RSP v3.4**, eff. 2026-07-08 — 4 thresholds incl. a misaligned-AI-in-high-stakes-settings sabotage threshold. Note v3.0 (Feb 2026) **removed** ASL-4 tiers, cyber, and radiological/nuclear. Superseded v2.1 numbered set (CBRN-3/4, AI R&D-4/5) is more usable as discrete events.
- **Google DeepMind FSF v3.1**, 2026-04-17 — 5 Critical Capability Levels incl. Harmful Manipulation L1, plus lower-tier **Tracked Capability Levels** as explicit early-warning tripwires incl. Stealth & Situational Awareness.
- **OpenAI Preparedness Framework v2**, 2025-04-15 — 3 Tracked Categories with High/Critical thresholds + 5 Research Categories: sandbagging, undermining safeguards, autonomous replication and adaptation, long-range autonomy, nuclear/radiological.
- **OpenAI Frontier Governance Framework**, 2026 — 4 systemic risk categories × 3 tiers; quantitative systemic-risk definition (>50 fatalities or $1B).
- **Meta Advanced AI Scaling Framework v2.0**, 2026-04-07 — 8 named catastrophic outcomes incl. Loss of Control 1 (loss of ability to evaluate safety pre-deployment) and 2 (loss of ability to monitor behavior in operation).
- **xAI Frontier AI Framework**, 2025-12-30 — only framework stating thresholds as reproducible benchmark numbers: <1/20 restricted-query answer rate; <1/2 dishonesty rate on MASK; VCT / WMDP / BioLP-bench / Cybench.
- Also: Amazon `[?PDF 404'd]`, Microsoft, NVIDIA, Magic, NAVER, G42, Cohere.

### Comparative trackers
- **METR, Common Elements of Frontier AI Safety Policies**, Dec 2025. https://metr.org/common-elements — 12 companies; Table 2 maps threat models. No unified threshold table.
- **Frontier Model Forum, Risk Taxonomy and Thresholds**, 2025-06-18 — proposes two-tier Enabling / Acceptable threshold structure.
- **SaferAI tracker** — https://tracker.safer-ai.org/ — 12 companies on 4 risk-management dimensions. July 2026: Anthropic 35% vs 59% best-practice ceiling. Scores quality, not content.
- **FLI AI Safety Index** — Winter 2025 (8 companies, 35 indicators, Anthropic C+ 2.67 → Alibaba D− 0.98); Summer 2026 (9 companies, Anthropic C+ top, xAI/DeepSeek/Mistral F). Snapshots, not longitudinal.
- **AI Lab Watch** — **dead since Sept 2025.**

No public source tabulates exact threshold wording for all companies in one machine-readable place.

## 7. Domain deployment trackers

### Self-exfiltration / open weights
- **Epoch AI, open vs closed weights** — https://epoch.ai/data-insights/open-weights-vs-closed-weights-models — ECI gap: 3 months / ~7 ECI points (2025-10-30); 4 months / ~8 points (May 2026). Same series, different vintages.
- **RepliBench** — UK AISI. https://www.aisi.gov.uk/frontier-ai-trends-report — Self-replication success 5% (2023) → 60% (2025). PDF free; raw eval data not released.
- **METR rogue replication** — https://metr.org/blog/2024-11-12-rogue-replication-threat-model/ — **explicitly deprioritized**; AISI has effectively inherited the role.
- **OpenAI model incident disclosures**, Sept 2026 — six incidents incl. unauthorized uploads to public file hosts, credential-seeking, GitHub API key use, cross-environment communication. Three-track disclosure procedure (6 / 12 business days / extended).
- **RAND SL1–SL5** weight-security framework exists; **no per-lab scorecard against it**.
- **No registry of weight leaks or distillation incidents exists.**

### Weapons / nuclear
- **Automated Decision Research state-positions monitor** — https://automatedresearch.org/state-positions/ — ~195 countries. Last updated June 2026. Not downloadable.
- **Arms Control Association, Human in the Loop and Nuclear Weapons Use** — https://www.armscontrol.org/factsheets/human-loop-glance — Updated July 2026. All five NPT nuclear-weapon states plus India (Feb 2026) and Pakistan affirm human control over nuclear employment. Event currently zero-incidence by declaratory measure; the monitorable signal is pledge withdrawal.
- **CSET** — only route to quantitative military-AI procurement data.
- **SIPRI** databases — no AI-autonomy field.
- **Stop Killer Robots** — UNGA support counts of 164 / 156 / 161 are different votes in different years `[?year mapping unconfirmed]`. US Political Declaration 47-endorser figure is `[?2024-era]`.
- **No public database of autonomy levels in fielded weapons; none of AI in NC3.**

### Chemical / bio
- **No registry of self-driving laboratories. No tracker of AI authority over chemical plant control systems. No tracker of agent access to cloud labs.**
- **SecureBio Virology Capabilities Test (VCT, VCT-v2)** — pre-release model assessments. A >50% VCT claim (above any PhD virologist tested) `[?sourced from a social post; cite the SecureBio report instead]`.
- **Nucleic-acid screening layer** — IGSC Harmonized Screening Protocol v3.0, IBBIS, SecureDNA, NIST, RAND.
- **Frontier Model Forum** biosafety threshold briefs.
- **Global BioLabs** — https://thebulletin.org/global-biolabs/ — BSL-3/4 facility census. No AI dimension; natural host if one were added.
- Autonomous chemical plant precedent: Yokogawa/JSR, 35 consecutive days, March 2022. No newer comparable milestone found.

### Vehicles
- **NHTSA Standing General Order** — https://www.nhtsa.gov/laws-regulations/standing-general-order-crash-reporting — Monthly CSVs, three files, 2025-06-16 → 2026-08-17. **Third SGO amendment (eff. 2025-06-16) narrowed ADAS reporting — pre/post series not comparable.**
- **California DMV** — disengagement + collision reports. 9,068,861 autonomous miles, Dec 2022–Nov 2023; 38 testing + 6 driverless permit holders.
- **Waymo Safety Impact** — https://waymo.com/safety/impact/ — 271.3M rider-only miles as of June 2026. Four downloadable CSVs keyed to SGO identifiers. ~500k rides/week (July 2026).
- **FHWA Table VM-1** — https://www.fhwa.dot.gov/policyinformation/statistics/2024/vm1.cfm — 3,294,031 million US VMT (2024). Denominator.
- Derived: Waymo cumulative ≈ **0.008% of one year of US driving**. Nobody publishes the ratio; both halves are free.
- **Tesla FSD** — 10B+ cumulative *supervised* miles (May 2026). Measures ADAS exposure, not autonomy. A 13.6B figure appears only in a low-authority outlet.

### Healthcare
- **FDA AI-enabled medical device list** — https://www.fda.gov/medical-devices/digital-health-center-excellence/artificial-intelligence-enabled-medical-devices — 1,600+ authorized as of Sept 2026; 331 in 2025 alone. Measures authorization, not autonomy; **the autonomous subset is not separately enumerated anywhere.**
- **MedTech Dive AI device tracker** — free, https://www.medtechdive.com/news/ai-medtech-track-new-devices-fda/748397/
- **MAUDE** — adverse events. **No AI flag**; requires manual join to the FDA list by product code.
- **CPT 92229** — autonomous retinal imaging claim volume. Best available autonomy proxy.
- **AMA annual survey** — 81% of US physicians using AI in 2026, roughly double 2023.
- **CHAI** — assurance-labs programme **collapsed early 2025**; model card registry (launched 2025-02-28, free) survives `[?card count and direct URL unverified]`.

### Cross-cutting
- **OECD AIM** (above) — single most useful cross-domain instrument; filters by mobility/AV, healthcare/biotech, government/security/defence, energy/utilities, digital security.
- **Anthropic Economic Index** — https://huggingface.co/datasets/Anthropic/EconomicIndex — only lab index with an open versioned dataset (+ CRAN package). Operationalizes **automation share** (directive or feedback-loop conversations). "Cadences" report June 2026.
- **UK AISI Frontier AI Trends Report** — lists critical-infrastructure integration as a theme; likeliest future host for an autonomy tracker.
- **No tracker of AI given control of critical infrastructure.** CISA/DHS publish guidance and federal AI use-case inventories only.
- **No cross-domain AI autonomy-level registry exists** — nothing analogous to SAE levels applied across domains.
