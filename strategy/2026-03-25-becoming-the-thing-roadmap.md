# Becoming the Thing: Alpha → Omega Institutional Roadmap

**Created:** 2026-03-25
**Authority:** META — aerarium--res-publica
**Purpose:** Close the gap between what ORGANVM IS and what funders need it to BE. Applications are the ask; this roadmap is the becoming.

> *The system cannot apply to be what it has not yet become. The directory structure is the paperwork. This document is the work.*

---

## The Fundamental Gap

ORGANVM operates at institutional scale internally (117 repos, 8 organs, formal governance, internal university). But externally it appears as: one person's private GitHub repositories. The institutional roadmap closes this gap across five dimensions that map to funder expectations.

---

## Five Dimensions of Becoming

| Dimension | What Funders See Now | What They Need to See | Who Demands It |
|-----------|---------------------|----------------------|----------------|
| **I. Public Infrastructure** | Private governance tooling | Extractable tool anyone can install | NLnet, Sovereign Tech, NSF |
| **II. Artistic Evidence** | Code in a repo | Documented, exhibited artwork with video | Creative Capital, ZKM |
| **III. Academic Credibility** | Research in git repos | Published papers, ORCID, scholar identity | Sloan, NSF, university affiliates |
| **IV. Institutional Presence** | No legal entity | Fiscal sponsor, advisory board, mission statement | Aspiration Tech, all funders |
| **V. Community Proof** | Zero external users | Contributors, users, events, inbound links | All funders ("who benefits?") |

---

## ═══════════════════════════════════════════
## DIMENSION I: PUBLIC INFRASTRUCTURE
## ═══════════════════════════════════════════

**Question every infrastructure funder asks:** *"Can someone else use this?"*

### Current State
- organvm-engine: 44 Python modules, working governance engine
- Manages 117 repos with promotion state machines, dependency validation, seed contracts
- Entirely internal — no external documentation, no PyPI package, no standalone install path

### Alpha → Omega

| # | Task | Deliverable | Validates For | Priority |
|---|------|-------------|---------------|----------|
| I-1 | **Extract governance engine core** as standalone package | `pip install organvm-governance` — promotion state machine, dependency validator, seed contract parser as library, decoupled from ORGANVM-specific config | NLnet abstract: "generalizable infrastructure" | P0 |
| I-2 | **Write external documentation** | README with quickstart, API reference, tutorial: "Add governance to your multi-repo project in 15 minutes" | NLnet: "ecosystem engagement" | P0 |
| I-3 | **Publish to PyPI** | `organvm-governance` package on pypi.org with CI-driven releases | NLnet: evidence of public artifact; Sovereign Tech: maintained infrastructure | P1 |
| I-4 | **Create example project** | A minimal 3-repo example (not ORGANVM) governed by the engine — proves generalizability | NLnet: "comparison against existing efforts" | P1 |
| I-5 | **Open issues for contribution** | "Good first issue" labels, CONTRIBUTING.md, contributor guide | NLnet: "ecosystem"; Omega #12 (external contributions) | P2 |
| I-6 | **Schema definitions as standalone** | `organvm-schemas` on PyPI/npm — seed.yaml, registry, governance-rules as reusable contracts | NLnet: additional grant component | P2 |
| I-7 | **Publish architecture paper** | "Promotion State Machines for Multi-Repository Governance" — arXiv preprint | Sloan, NSF; Omega #14 (recognition) | P2 |

### NLnet-Ready Gate
I-1 + I-2 completed = credible NLnet abstract. I-3 + I-4 = strong application. The application can describe I-3/I-4 as funded deliverables — NLnet funds R&D, not deployment of what already exists.

---

## ═══════════════════════════════════════════
## DIMENSION II: ARTISTIC EVIDENCE
## ═══════════════════════════════════════════

**Question every arts funder asks:** *"Show me the work."*

### Current State
- Alchemical Synthesizer: 21K LOC SuperCollider + 12 Pd patches + p5.js web visualization
- Chthon-Oneiros: psychological horror narrative engine with director dials, Giallo linter
- ETCETER4 (a-mavs-olevm): custom SPA artist website
- Krypto-Velamen: queer literary archive platform (8 microservices)
- No video documentation, no exhibition history, no artist statement, no public presentation

### Alpha → Omega

| # | Task | Deliverable | Validates For | Priority |
|---|------|-------------|---------------|----------|
| II-1 | **Record Alchemical Synthesizer** | 5-minute video: SC engine running + Pd interface + p5.js organism visualization. Upload to Vimeo (private w/ password) | Creative Capital: work sample (BLOCKING) | P0 |
| II-2 | **Write work sample caption** | 100 words: title, materials, date, description | Creative Capital: required field | P0 |
| II-3 | **Write artist statement** | 3 lengths (50-word, 200-word, 500-word) — the system-as-artwork thesis | Creative Capital: bio fields; all arts funders | P0 |
| II-4 | **Document exhibition/presentation history** | List every public showing, performance, screening, reading, panel. Need 5+ years of professional practice for CC eligibility. Even informal presentations count. | Creative Capital: eligibility requirement | P0 |
| II-5 | **Create artist resume** | 1-page PDF, art-only (no employment), reverse chronological, last 5 years | Creative Capital: required upload | P0 |
| II-6 | **Deploy ETCETER4** | Live artist website at a public URL (GitHub Pages or Cloudflare) | All funders: "show me your website" | P1 |
| II-7 | **Document the system as artwork** | "ORGANVM: A Living Creative System" — essay/manifesto framing the 117-repo ecosystem as artistic practice | Creative Capital Q1 (Innovation); Omega #6 (AI-conductor essay = MET, but need system-as-art essay) | P1 |
| II-8 | **Submit to exhibition/festival** | Apply to at least 1 media art festival, open call, or screening with the Alchemical Synthesizer video | Omega #14 (recognition event) | P2 |

### Creative Capital-Ready Gate
II-1 + II-2 + II-3 + II-4 + II-5 = complete Round I application. Without the work sample video (II-1), the application cannot be submitted.

---

## ═══════════════════════════════════════════
## DIMENSION III: ACADEMIC CREDIBILITY
## ═══════════════════════════════════════════

**Question every research funder asks:** *"What is your scholarly identity?"*

### Current State
- SGO research corpus: 13 works, 500K+ words, all TRP-cleared
- Dissertation in progress (SGO-2026-D-002, 11 chapters)
- No ORCID, no arXiv submissions, no peer-reviewed publications
- No institutional affiliation

### Alpha → Omega

| # | Task | Deliverable | Validates For | Priority |
|---|------|-------------|---------------|----------|
| III-1 | **Register ORCID** | ORCID iD — persistent researcher identifier | All academic funders; Omega #15 (portfolio validation) | P0 |
| III-2 | **Submit first paper to arXiv** | "Recursive Institutional Governance: A Computational Framework for Self-Evaluating Systems" or equivalent — the SGO's strongest completed work | Sloan: scholarly credibility; NSF: PI evidence; Omega #14 (recognition) | P1 |
| III-3 | **Create researcher profile** | Google Scholar profile, ResearchGate, or Semantic Scholar — link ORCID, list works | University affiliate applications; Sloan LOI | P1 |
| III-4 | **Identify university partner** | Contact 3-5 faculty in DH, CS, media arts. Offer ORGANVM as research platform. Seek research affiliate status. | NSF POSE: PI eligibility (BLOCKING for federal grants) | P2 |
| III-5 | **Submit to peer-reviewed venue** | Conference paper or journal article — ACM, IEEE, or digital humanities journal | Omega #14; long-term credibility | P2 |
| III-6 | **Publish SGO methodology** | "The Studium Generale ORGANVM: An Independent Academic Organ for Self-Sovereign Knowledge Production" — position paper on the SGO model itself | Distinguishes ORGANVM from other OSS projects | P3 |

### Academic-Ready Gate
III-1 + III-2 = minimum viable scholarly identity. III-3 + III-4 = NSF-eligible.

---

## ═══════════════════════════════════════════
## DIMENSION IV: INSTITUTIONAL PRESENCE
## ═══════════════════════════════════════════

**Question every institutional funder asks:** *"Are you a real organization?"*

### Current State
- No legal entity (no LLC, no nonprofit, no fiscal sponsor)
- No EIN, no bank account, no advisory board
- No Candid profile, no donor infrastructure
- Vision and governance exist in git, not in legal filings

### Alpha → Omega

| # | Task | Deliverable | Validates For | Priority |
|---|------|-------------|---------------|----------|
| IV-1 | **Form ORGANVM LLC** | Articles of Organization + Operating Agreement + EIN + bank account | Commercial arm operational; Aspiration Tech: "separate legal entity" | P0 |
| IV-2 | **Email Aspiration Tech** | Initial inquiry to fiscalservices@aspirationtech.org with project description, budget, financial goals | Fiscal sponsor application initiated | P0 |
| IV-3 | **Assemble advisory board** | Identify 3+ people willing to serve as advisors. Not governance board — advisory. Can be peers, mentors, collaborators. | Aspiration Tech: Model C may require governance body | P1 |
| IV-4 | **Write mission statement** | 1-paragraph institutional mission for ORGANVM-the-organization (not the software). Derived from VISION.md but oriented toward public benefit. | All funders: "what is your mission?" | P1 |
| IV-5 | **Set up GitHub Sponsors** | Personal account first, org later. Configure tiers, add FUNDING.yml to key repos. | Immediate funding channel; Omega #9 (revenue) | P1 |
| IV-6 | **Enroll in Candid FSP pilot** | Email fiscalsponsorship@candid.org once sponsor confirmed. Earn Bronze → Gold Seal. | 230+ platform syndication; Omega #13 (inbound links) | P2 |
| IV-7 | **Register on donation platforms** | Every.org, Benevity, PayPal Giving Fund — all free, all require 501(c)(3) via sponsor | Donor infrastructure operational | P2 |
| IV-8 | **Draft annual budget** | Projected Year 1 budget: what the sponsored project spends on (infrastructure, research, travel, contractor time) and what the LLC generates | Aspiration Tech: required; all funders want budget realism | P1 |

### Institution-Ready Gate
IV-1 + IV-2 = dual-entity model initiated. IV-3 + IV-4 + IV-8 = Aspiration Tech application complete.

---

## ═══════════════════════════════════════════
## DIMENSION V: COMMUNITY PROOF
## ═══════════════════════════════════════════

**Question every funder asks:** *"Who else cares?"*

### Current State
- Zero external contributors to ORGANVM repos
- Zero external users of governance tooling
- No community events (salons, reading groups, workshops)
- Some external engagement on agentic-titan (Issue #20: m13v, 3 substantive comments)
- Portfolio site live but no organic traffic data

### Alpha → Omega

| # | Task | Deliverable | Validates For | Priority |
|---|------|-------------|---------------|----------|
| V-1 | **Open flagship repos for contribution** | CONTRIBUTING.md, "good first issue" labels, code of conduct on organvm-engine, alchemical-synthesizer, schema-definitions | NLnet: ecosystem; Omega #12 (contributions) | P1 |
| V-2 | **Write "How to Govern Your Multi-Repo Project"** | Blog post / tutorial showing how to use the governance engine on YOUR project. Publish on portfolio site (Organ V). | NLnet: public benefit proof; Omega #6 (essay published = already MET, but need infrastructure-specific essay) | P1 |
| V-3 | **Host first community event** | Reading group, salon, or workshop — can be online. 3+ external participants. | Omega #11 (2 events with external participants) | P2 |
| V-4 | **Collect external feedback** | 3+ pieces of written feedback from people outside the system — on the governance engine, the research, or the art | Omega #7 (external feedback); Shuttleworth replacement applications | P2 |
| V-5 | **Submit to Hacker News / relevant forum** | "Show HN: Governance engine for multi-repo open-source projects" — test public reception | Organic inbound links; Omega #13 (MET but strengthen) | P2 |
| V-6 | **Engage existing OSS community** | Comment on relevant GitHub discussions (Backstage, CNCF governance, ASF Incubator). Offer governance engine as solution. Don't spam — contribute genuinely. | NLnet: "relevant actors"; Omega #7 (feedback) | P2 |

### Community-Ready Gate
V-1 + V-2 = minimum viable public presence. V-3 + V-4 = demonstrable community engagement.

---

## ═══════════════════════════════════════════
## EXECUTION TIMELINE
## ═══════════════════════════════════════════

### Week 1 (March 25 — April 1): SPRINT — NLnet Deadline

| Day | Tasks | Gate |
|-----|-------|------|
| Mar 25 | I-1: Begin extracting governance engine core. III-1: Register ORCID. | Identity established |
| Mar 26 | I-1: Continue extraction. I-2: Write external README + quickstart. | Standalone engine exists |
| Mar 27 | NLnet draft: abstract, background, comparison, technical challenges, ecosystem. | Draft complete |
| Mar 28 | NLnet budget: task-level breakdown with rates. | Budget complete |
| Mar 29 | NLnet review: read aloud, verify claims, check scoring criteria alignment. | Review complete |
| Mar 30 | II-1: Record Alchemical Synthesizer video (for CC, but starts now). | Work sample in progress |
| Mar 31 | NLnet final polish. AI disclosure section. Submit buffer day. | **Application ready** |
| **Apr 1** | **SUBMIT NLnet by 12:00 CEST** | **SUBMITTED** |

### Week 2 (April 2 — April 8): SPRINT — Creative Capital + Sovereign Tech

| Day | Tasks | Gate |
|-----|-------|------|
| Apr 2 AM | **SUBMIT Creative Capital by 3:00 PM ET** (if work sample ready) | **SUBMITTED** |
| Apr 2-3 | II-3: Write artist statement (50/200/500 word versions). II-5: Artist resume. | Artist identity documented |
| Apr 4-5 | IV-1: Form LLC. IV-2: Email Aspiration Tech. | Dual-entity initiated |
| Apr 6 | Apply Sovereign Tech Fellowship (if eligible after research). | Application submitted or ruled out |
| Apr 7-8 | IV-5: Set up GitHub Sponsors. V-1: Open repos for contribution. | Public channels open |

### Week 3-4 (April 9 — April 22): BUILD — Infrastructure + Credibility

| Tasks | Gate |
|-------|------|
| Apr 12: Apply ZKM Rauschenberg (if eligible). | Arts track extended |
| I-3: Publish organvm-governance to PyPI. | Public artifact exists |
| I-4: Create example project (3-repo non-ORGANVM demo). | Generalizability proven |
| III-2: Submit first paper to arXiv. | Scholar identity established |
| III-3: Create researcher profiles (Google Scholar, ORCID linked). | Academic presence |
| IV-3: Assemble advisory board (3 people). | Governance body exists |
| IV-4: Write institutional mission statement. | Mission articulated |
| V-2: Write + publish "How to Govern Your Multi-Repo Project." | Public benefit documented |

### Month 2-3 (May — June): DEEPEN — Community + Sloan

| Tasks | Gate |
|-------|------|
| Send Sloan Foundation LOI (2-page letter of inquiry). | Foundation engagement |
| V-3: Host first community event (online reading group or workshop). | Community proof |
| V-4: Collect 3+ external feedback pieces. | External validation |
| II-6: Deploy ETCETER4 artist website. | Public artist presence |
| IV-6: Enroll Candid FSP pilot (if sponsor confirmed). | Visibility infrastructure |
| III-4: Contact 3-5 faculty for research affiliate status. | Academic pathway |

### Month 4-6 (July — September): SOLIDIFY — NSF + Academic

| Tasks | Gate |
|-------|------|
| NSF POSE Phase I application (September 2 deadline). | Federal grant pipeline |
| III-5: Submit to peer-reviewed venue. | Academic credibility |
| V-5: Submit to HN or relevant forum. | Public reception test |
| II-8: Submit to media art festival. | Exhibition trajectory |
| IV-8: Draft annual budget. | Financial planning |

### Month 6-12: INSTITUTIONAL SCALE

| Tasks | Gate |
|-------|------|
| Evaluate: Convert LLC → Delaware PBC. | Mission embedded in entity |
| Build 501(c)(3) application (3 board members, articles of incorporation). | Independence pathway |
| Candid Gold Seal → free Premium ($1,199). | Funder discovery tools |
| Second arXiv paper or journal submission. | Academic trajectory |
| Omega scorecard: target 10/17 met. | System maturity |

### Year 2-3: MOZILLA MODEL

| Tasks | Gate |
|-------|------|
| File 501(c)(3). IRS review (6-10 months). | Independent nonprofit |
| Spin off from fiscal sponsor (60-120 day transition). | Self-governing |
| Foundation owns PBC. Board governs mission. | Full institutional structure |
| Omega 17/17. | **The system simply is.** |

---

## ═══════════════════════════════════════════
## CROSS-REFERENCE: OMEGA CRITERIA ALIGNMENT
## ═══════════════════════════════════════════

| Omega # | Criterion | Institutional Task | Status |
|---------|-----------|-------------------|--------|
| 1 | 30-day soak test | Not institutional — system health | Independent |
| 2 | Stranger test ≥80% | V-2 (tutorial), I-2 (external docs) | Enabled by I-2 |
| 3 | Engagement baseline | V-3, V-4 (community events + feedback) | Enabled by V-1 |
| 4 | Runbooks validated | Not institutional — operational | Independent |
| 5 | ≥1 application submitted | **IRF-INST-001 (NLnet), IRF-INST-002 (CC)** | THIS ROADMAP |
| 6 | AI-conductor essay published | **MET** | — |
| 7 | ≥3 external feedback | V-4 | Enabled by V-1 |
| 8 | ≥1 product live | **MET** | — |
| 9 | Revenue status: live | IV-1 (LLC), IV-5 (GitHub Sponsors) | THIS ROADMAP |
| 10 | MRR ≥ operating costs | Revenue from LLC products + Sponsors | Long-term |
| 11 | ≥2 events with external participants | V-3 | Enabled by IV presence |
| 12 | ≥3 external contributions | V-1, V-5, V-6 | Enabled by I-2 |
| 13 | ≥1 organic inbound link | **MET** | — |
| 14 | ≥1 recognition event | III-2 (arXiv), II-8 (exhibition), NLnet/CC grants | THIS ROADMAP |
| 15 | Portfolio updated with validation | III-3 (profiles), II-6 (artist site) | THIS ROADMAP |
| 16 | Bus factor >1 | IV-3 (advisory board), V-1 (contributors) | Enabled by community |
| 17 | (Check roadmap doc) | — | — |

**Institutional roadmap directly advances 10 of 17 omega criteria.**

---

## ═══════════════════════════════════════════
## ANTI-PATTERNS
## ═══════════════════════════════════════════

1. **Do not apply without becoming.** An application that says "we will build X" when X could be built NOW is weaker than one that says "we have built X, fund us to make it universal."
2. **Do not build in private.** Every task should produce a public artifact. Git commits are not public artifacts — deployed docs, published packages, arXiv papers are.
3. **Do not conflate internal governance with public infrastructure.** The governance engine governing ORGANVM is proof of concept. The governance engine governing SOMEONE ELSE'S project is proof of value.
4. **Do not skip the video.** Creative Capital requires a work sample. No video = no application. The Alchemical Synthesizer must be recorded.
5. **Do not apply to academic funders without ORCID.** It takes 5 minutes. There is no excuse.
6. **Do not form an advisory board of strangers.** Find people who know the work, believe in it, and will pick up the phone when a funder calls.

---

## Sources

- ORGANVM Omega Scorecard: `docs/strategy/there+back-again.md`
- Institutional Strategy Master: `aerarium--res-publica/strategy/2026-03-24-organvm-institutional-strategy-master.md`
- NLnet Research: `aerarium--res-publica/research/2026-03-24-nlnet-application-research.md`
- Creative Capital Research: `aerarium--res-publica/research/2026-03-24-creative-capital-application-research.md`
- VISION.md: `meta-organvm/VISION.md`
