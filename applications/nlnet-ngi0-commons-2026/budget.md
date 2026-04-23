# NLnet NGI0 Commons Fund — Budget

**Requested:** EUR 37,080 (max 50,000 for first-time applicants)
**Rate:** EUR 80/hour (independent developer, EU-comparable rate for senior Python/infrastructure work)

## Task Breakdown

| # | Task | Hours | Rate (EUR/hr) | Cost (EUR) | Deliverable |
|---|------|-------|---------------|------------|-------------|
| T1 | Core extraction and API design | 120 | 80 | 9,600 | M1: Library passes independent test suite; no ORGANVM-specific imports |
| T2 | Schema package | 32 | 80 | 2,560 | M2: Schema package published with validation examples |
| T3 | Documentation (WCAG 2.1 AA) | 48 | 80 | 3,840 | M3: Documentation site live, accessibility statement published |
| T4 | Example project and generalizability test | 64 | 80 | 5,120 | M4: Example project functional; engine proven outside origin context |
| T5 | PyPI publishing and CI | 20 | 80 | 1,600 | M5: Package on PyPI with automated releases |
| T6 | Interoperability and open standards | 56 | 80 | 4,480 | M6: Specification published; interop adapters for publiccode.yml and Backstage operational |
| T7 | CLI accessibility | 20 | 80 | 1,600 | M7: Accessibility audit passed, conformance statement published |
| T8 | Security review and hardening | 20 | 80 | 1,600 | M8: SBOM published, security review documented |
| T9 | Community infrastructure | 16 | 80 | 1,280 | M9: Community channels operational, 3+ "good first issue" items published |
| T10 | Integration testing and release | 24 | 80 | 1,920 | M10: v1.0 released; evaluation report published |
| T11 | Dissemination | 8 | 80 | 640 | M11: Presentation delivered, announcement published |
| | Contingency (reviewer feedback, unforeseen integration issues) | 20 | 80 | 1,600 | — |
| | Travel (1 European event — FOSDEM or NLnet/NGI meeting) | — | — | 1,240 | — |
| | **TOTAL** | **448** | | **EUR 37,080** | |

## Timeline

6 months from MoU signing.

- Month 1: M1 (core extraction — state machine, then dependency validator, then seed system)
- Month 2: M2 (schemas) + M3 (documentation)
- Month 3: M4 (example project and generalizability test)
- Month 4: M5 (PyPI release) + M6 (interoperability and specification)
- Month 5: M7 (accessibility) + M8 (security) + M9 (community)
- Month 6: M10 (integration testing and release) + M11 (dissemination)

Milestones within the same month are parallelizable. Each milestone produces a verifiable deliverable before payment.

## Notes

- All deliverables will be released under Apache 2.0 license (compatible with MIT provenance of existing engine)
- WCAG 2.1 AA compliance included in T3 (documentation) and T7 (CLI accessibility)
- Security hardening in T8: dependency minimization, pinned deps, SBOM (CycloneDX), supply chain audit
- Milestone-based payments per NLnet MoU structure
- Rate reflects open-source mission commitment; comparable NLnet-funded projects bill EUR 60-100/hour
