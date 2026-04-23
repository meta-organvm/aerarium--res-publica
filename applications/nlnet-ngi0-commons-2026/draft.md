# NLnet NGI0 Commons Fund — Application Draft

## Proposal Name

<!--
  Short, descriptive. Examples of funded projects: "TrailBase", "Typed Nix", "GoActivityPub"
-->

Cvrsvs Honorvm — Governance Engine for Multi-Repository Open-Source Ecosystems

## Website / Wiki

https://github.com/meta-organvm/organvm-engine — the production codebase from which the governance engine will be extracted. See also: [schema-definitions](https://github.com/meta-organvm/schema-definitions) (JSON Schemas), [organvm-corpvs-testamentvm](https://github.com/meta-organvm/organvm-corpvs-testamentvm) (governance corpus including registry-v2.json and governance-rules.json).

## Abstract

<!--
  200-500 words. Full project + expected outcomes.
  Frame as INTERNET COMMONS INFRASTRUCTURE, not personal tooling.
  Focus on WHAT and HOW, not so much on WHY.
-->

Multi-repository governance is an unsolved structural problem for the Next Generation Internet. An estimated 150,000+ GitHub organizations maintain 10 or more repositories, and approximately 15,000 of these exceed 50 — the threshold at which ad-hoc governance consistently breaks down. Maintainers track repository maturity in spreadsheets, enforce dependency rules through convention, and coordinate lifecycle decisions through processes that do not scale. No existing open-source tool provides machine-enforceable lifecycle governance for multi-repository ecosystems.

Cvrsvs Honorvm is an open-source Python library that provides three primitives for multi-repository ecosystem governance:

**1. Promotion State Machine.** A configurable finite state machine governing repository lifecycle transitions (e.g., LOCAL → CANDIDATE → PUBLIC → GRADUATED → ARCHIVED). Transition topology is declared in a JSON configuration file. Each transition triggers configurable infrastructure audits — verifying that CI, documentation, and licensing requirements are met before a repository can advance. Successful transitions emit events to an append-only ledger, producing an audit trail of governance decisions.

**2. Dependency Graph Validator.** A directed acyclic graph (DAG) validator enforcing dependency flow rules across organizational boundaries. The validator performs cycle detection, back-edge enforcement between organizational tiers, self-dependency checking, and missing-target detection. Edge types (build dependency, data flow) are distinguished to enable independent validation of different relationship categories.

**3. Seed Contract System.** A declarative YAML contract format (`seed.yaml`) — similar in concept to Backstage's `catalog-info.yaml` but focused on governance rather than service cataloging — that each repository uses to declare its organizational membership, maturity tier, dependency edges, and event subscriptions. The engine discovers seed files across a workspace and constructs the full ecosystem graph from their declarations.

The central R&D question is: **can formal governance be declaratively specified as a portable open standard that works across heterogeneous open-source ecosystems?** The funded work will answer this by extracting these primitives from a working 145-repository implementation, redesigning the interface layer for portability, publishing the seed contract format as an open specification, and demonstrating adoption on an independent ecosystem.

**Expected outcomes:**

- A published PyPI package (`cvrsvs-honorvm`) providing promotion state machines, dependency DAG validation, and seed contract parsing as a reusable library. All funded deliverables licensed under Apache License 2.0 (SPDX: Apache-2.0). (The existing engine is MIT-licensed; the extracted standalone package will use Apache 2.0 for its stronger patent grant protections, which is compatible with MIT provenance.)
- The seed.yaml contract format published as a versioned open specification (CC-BY-4.0), with interoperability adapters for publiccode.yml (EU public administration standard) and Backstage catalog-info.yaml
- External documentation (WCAG 2.1 AA compliant) with quickstart guide, API reference, and tutorial
- A minimal example project (3 repositories, not from ORGANVM) demonstrating the engine applied to an independent ecosystem
- JSON Schema definitions for all contract formats, published as a standalone schema package enabling validation in any language

## Background

<!--
  100-300 words. Prior relevant project or organizational involvement.
  What has already been built? What's the track record?
-->

The governance primitives proposed for extraction already exist as production software. They have been developed since 2025 as part of the ORGANVM project — a multi-organ open-source ecosystem spanning 145 repositories across 9 GitHub organizations.

The engine currently manages the full lifecycle of these repositories: enforcing promotion state transitions, validating dependency flows across organizational boundaries, and maintaining a central registry with computed system metrics. The codebase consists of 376 Python source files (~87,000 lines) with a unified CLI exposing 44 command groups. The project has 5,200+ test functions across 247 test files, and a CI pipeline running on every push. Source code: [github.com/meta-organvm/organvm-engine](https://github.com/meta-organvm/organvm-engine).

Concrete capabilities already implemented and in daily use:
- A 6-state promotion state machine with data-driven transition rules, configurable infrastructure audit gates, and event emission on state change
- A dependency graph validator with cycle detection (DFS with three-color marking) and back-edge enforcement across organizational tiers
- A seed contract discovery system that traverses a workspace, parses declarative YAML contracts, and constructs a produces/consumes graph across 96 repositories
- A JSON Schema suite (33 schemas) covering registry, seed, governance-rules, dispatch-payload, formation, ontologia-event, pulse-event, signal-signature, state-snapshot, and 24 additional domain-specific formats

The applicant has built and maintained this system as a solo developer, demonstrating the governance model's feasibility at scale. The funded work is not building from scratch — it is redesigning the interface layer for portability, publishing the contract format as an open specification, and proving generalizability beyond its origin ecosystem.

## Other Funding Sources

<!--
  Past and present funding. Be honest.
-->

This project has not received prior external funding. Development has been self-funded by the maintainer since 2025.

## Comparison

<!--
  1-2 paragraphs. Show you know the landscape.
  What exists? How is your approach different/better?
  Consider: Backstage (Spotify), CNCF governance, Apache Incubator, Linux Foundation tooling
-->

Existing approaches to multi-repository governance address parts of the problem but not the whole. **Service catalogs** (Backstage, Port, Cortex) track what repositories exist and who owns them. Backstage's `catalog-info.yaml` is the closest prior art to the seed contract format — both declare repository metadata in YAML — but Backstage does not enforce lifecycle transitions or validate dependency flows across organizational boundaries. Backstage Scorecards and Tech Insights provide maturity checks but not a formal state machine governing promotion decisions. **Foundation incubation processes** (Apache Incubator, CNCF Sandbox/Incubating/Graduated) implement promotion state machines, but as human-mediated committee processes, not as machine-enforceable tooling a project can adopt independently. **Maturity scoring tools** (CNCF CLOMonitor, OpenSSF Scorecard) assess project health against defined criteria but do not enforce transitions or model inter-repository dependency flows. **Public administration standards** (publiccode.yml from Developers Italia) declare software metadata for catalog purposes but do not include governance lifecycle or dependency validation.

Cvrsvs Honorvm combines the formal promotion lifecycle of a foundation incubation process with the dependency awareness of a graph validator and the declarative metadata of a service catalog — unified in a single library with configuration-driven rules. Governance policy is expressed as data (JSON for transitions, YAML for contracts, JSON Schema for validation), not as code or committee processes. A project writes its own `governance-rules.json` and `seed.yaml` contracts; the engine enforces them. No comparable open-source tool provides this combination of configurable lifecycle governance, dependency graph validation, and declarative ecosystem contracts in a single adoptable package.

## Technical Challenges

<!--
  1-2 paragraphs. Honest technical risk assessment.
  What's hard about this? What could go wrong?
-->

The primary technical challenge is **redesigning the interface layer for portability.** The current implementation has deep coupling to its host ecosystem: the dependency validator hardcodes organizational directory names as literal strings in its back-edge enforcement rules; the seed discovery system imports workspace layout conventions at module level; and the state machine's transition executor imports from 5 internal subsystems (CI audit, event spine, authorization, registry, and pulse emitter). Extracting a clean library API requires replacing these couplings with dependency injection and configurable organizational hierarchies. This is more than refactoring — it requires designing an abstract interface for "registry," making the organizational tier system pluggable, and restructuring the seed discovery to support arbitrary workspace layouts. The scope is well-understood (the coupling points are known and finite), but the interface design demands care: the extracted library must be simple enough for a new user to configure in minutes, while remaining expressive enough to model the governance policies that the engine's current users rely on.

A second challenge is **schema evolution.** The seed.yaml contract format will need to evolve as adopters encounter use cases not anticipated by the current implementation. Premature stabilization risks limiting the tool's applicability; insufficient stability risks breaking existing users. The mitigation strategy is to version all schemas explicitly (the seed format already carries a `schema_version` field), maintain backward-compatible readers for older versions, and publish the specification separately from the implementation so that format evolution is governed by community consensus, not by Python release cycles.

A third risk is **demonstrating generalizability.** The engine currently governs one ecosystem. The example project (Task T4) is specifically designed to prove the engine works outside its origin context, but the first external adoption always surfaces hidden assumptions. The budget accounts for this: T4 is sized for discovery and iteration, not just implementation.

## Ecosystem

<!--
  1-2 paragraphs. Community engagement, standards bodies, deployment.
  Who benefits? How will you reach them? Sustainability after the grant?
-->

The primary beneficiaries are **maintainers of multi-repository open-source projects** who have outgrown ad-hoc governance. European organizations are well represented in this category: KDE (800+ repos), GNOME (500+ repos), Matrix.org (100+ repos), Nextcloud (100+ repos), CERN (400+ repos), and the European Commission's Open Source Programme Office (200+ repos) each manage multi-repository ecosystems without formal lifecycle governance tooling. The engine also serves NGI-funded projects that grow into multi-repository ecosystems — projects like p2panda, Typed Nix, and GoActivityPub — by providing governance infrastructure they can adopt as they scale.

The project will engage with relevant actors through concrete actions during the grant period: publishing the seed.yaml specification and soliciting feedback from the Backstage community (which has the catalog but lacks governance enforcement), the CNCF CLOMonitor maintainers (who score project maturity but do not enforce transitions), and the publiccode.yml community (which shares the goal of standardized software metadata for public benefit). Dissemination will include a published tutorial ("Add formal governance to your multi-repo project in 15 minutes"), a presentation at a European open-source event (FOSDEM Infrastructure devroom or an NLnet/NGI community meeting), and direct participation in relevant GitHub discussions.

**Sustainability after the grant:** The governance engine's primary sustainability mechanism is dogfooding — the ORGANVM project depends on the engine in production for daily operations across 145 repositories, creating a strong incentive for ongoing maintenance independent of external funding. This is the same sustainability model that drives tools like Homebrew and rustfmt: maintained because their maintainers use them daily. The standalone package further reduces maintenance burden by decoupling from the parent project's release cycle.

**European Dimension.** While the applicant is based in the United States, the governance engine directly serves European digital sovereignty objectives. The seed contract format is designed for interoperability with European-originated standards: publiccode.yml (the Italian/EU public administration software descriptor) and REUSE (the FSFE license compliance specification). All funded deliverables will be published as open-source software (Apache 2.0) and open specifications (CC-BY-4.0), contributing directly to the European digital commons. The applicant commits to presenting the work at a European open-source event during the grant period (travel budgeted in T11).

## Requested Budget

<!--
  EUR 5K-50K (first-time applicants max 50K).
  Task-level breakdown with explicit rates.
  NLnet pays milestone-based via MoU.
-->

**Total requested: EUR 37,080**

Rate: EUR 80/hour (independent developer, EU-comparable rate for senior Python/infrastructure work). Rate reflects the project's open-source mission and commitment to cost-effective delivery; comparable NLnet-funded projects bill EUR 60-100/hour for senior systems programming work.

| # | Task | Hours | EUR | Milestone |
|---|------|-------|-----|-----------|
| T1 | **Core extraction and API design** — Redesign the interface layer for portability. Replace hardcoded organizational hierarchies with configurable tier systems. Define abstract registry interface. Restructure seed discovery for arbitrary workspace layouts. Replace module-level ORGANVM imports with dependency injection. Write unit tests for the standalone library. Sub-milestones: state machine extraction, dependency validator extraction, seed system extraction. | 120 | 9,600 | M1: Library passes independent test suite; no ORGANVM-specific imports |
| T2 | **Schema package** — Extract JSON Schema definitions (seed-v1, governance-rules) into standalone schema package. Add cross-language validation examples (Python, JavaScript). Publish to PyPI and npm. | 32 | 2,560 | M2: Schema package published with validation examples |
| T3 | **Documentation** — README with quickstart, API reference (auto-generated from docstrings), and narrative tutorial. WCAG 2.1 AA compliant HTML documentation site with semantic heading hierarchy, alt text for diagrams, and keyboard navigation. | 48 | 3,840 | M3: Documentation site live, accessibility statement published |
| T4 | **Example project and generalizability test** — Build a minimal 3-repository ecosystem (not ORGANVM) governed by the extracted engine. Demonstrates: seed contracts, promotion transitions, dependency validation, audit reporting. Serves as integration test, adoption template, and first proof of generalizability. Budget sized for discovery of hidden assumptions. | 64 | 5,120 | M4: Example project functional; engine proven outside origin context |
| T5 | **PyPI publishing and CI** — Automated release pipeline (GitHub Actions → PyPI). Semantic versioning, changelog generation, reproducible builds. CI for tests, linting, type checking, schema validation. | 20 | 1,600 | M5: Package on PyPI with automated releases |
| T6 | **Interoperability and open standards** — Publish seed.yaml contract format as a versioned specification (CC-BY-4.0). Implement import/export adapters for publiccode.yml (EU public administration standard) and Backstage catalog-info.yaml. Document how seed contracts complement (not replace) OpenSSF Scorecard, REUSE, and CodeMeta. | 56 | 4,480 | M6: Specification published; interop adapters for publiccode.yml and Backstage operational |
| T7 | **CLI accessibility** — Ensure CLI output and error messages meet WCAG 2.1 AA. Structured JSON output mode for all commands. Test with VoiceOver and NVDA. Publish accessibility conformance statement. | 20 | 1,600 | M7: Accessibility audit passed, conformance statement published |
| T8 | **Security review and hardening** — Dependency minimization, pinned dependencies, SBOM generation (CycloneDX format). Supply chain risk audit. Address findings. | 20 | 1,600 | M8: SBOM published, security review documented |
| T9 | **Community infrastructure** — CONTRIBUTING.md, code of conduct, issue templates, "good first issue" labels, contributor guide. Set up GitHub Discussions. Respond to early adopter feedback during the grant period. | 16 | 1,280 | M9: Community channels operational, 3+ "good first issue" items published |
| T10 | **Integration testing and release** — End-to-end testing of the full package (library + schemas + CLI + docs + example project). Apply engine to 1 real-world open-source ecosystem (outside ORGANVM) and publish evaluation report. Final v1.0 release and announcement. | 24 | 1,920 | M10: v1.0 released; evaluation report published |
| T11 | **Dissemination** — Present at a European open-source event (FOSDEM, NLnet/NGI community meeting). Publish blog post announcing the project and its NGI context. | 8 | 640 | M11: Presentation delivered, announcement published |
| | **Contingency** (reviewer feedback, unforeseen integration issues) | 20 | 1,600 | — |
| | **Travel** (1 European event — FOSDEM or NLnet/NGI meeting) | — | 1,240 | — |
| | | | | |
| | **TOTAL** | **448** | **EUR 37,080** | |

**Timeline:** 6 months from MoU signing.
- Month 1: M1 (core extraction — state machine, then dependency validator, then seed system)
- Month 2: M2 (schemas) + M3 (documentation)
- Month 3: M4 (example project and generalizability test)
- Month 4: M5 (PyPI release) + M6 (interoperability and specification)
- Month 5: M7 (accessibility) + M8 (security) + M9 (community)
- Month 6: M10 (integration testing and release) + M11 (dissemination)

Milestones within the same month are parallelizable. Each milestone produces a verifiable deliverable before payment.

## AI Disclosure

This application was drafted with assistance from Claude (Anthropic, Opus 4.6 model). The AI was used for: (1) researching the application process and form requirements, (2) structuring the draft according to NLnet's published evaluation criteria, (3) iterating on the abstract, framing, and technical accuracy through adversarial review. All substantive claims about the project — including technical architecture, capabilities, coupling analysis, and budget estimates — are authored by the applicant and verified against the actual codebase. Prompts and unedited outputs available on request.
