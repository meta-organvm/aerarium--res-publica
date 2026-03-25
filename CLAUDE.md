# CLAUDE.md

## What This Is

**Aerarium Res Publica** — "Treasury of the Public Thing." ORGANVM's institutional wing. Manages the legal, financial, and governance infrastructure required to transform the system from open-source software into a fundable institution.

**Organ:** META-ORGANVM (constitutional layer)
**Parent workspace:** `~/Workspace/meta-organvm/`

## Why This Exists

ORGANVM operates at institutional scale (117 repos, 8 organs, formal governance, internal university) but lacks the legal and financial entity that makes it fundable. This repo manages:

1. **Entity formation** — LLC (commercial arm), fiscal sponsorship (nonprofit arm), eventual 501(c)(3)
2. **Grant applications** — NLnet, Creative Capital, Sloan, NSF POSE, residencies/fellowships
3. **Donor infrastructure** — Candid profile, GitHub Sponsors, Every.org, Benevity
4. **IP policy** — Open-core model: open-source base (Apache 2.0) + proprietary extensions (LLC)
5. **Institutional strategy** — Phased roadmap: fiscal sponsor + LLC → PBC → Foundation (Mozilla model)

## Commands

```bash
# This is primarily a documentation/strategy repo — no build system
# Navigate and edit directly

# Check deadline proximity
grep -r "Deadline\|deadline\|DEADLINE" applications/*/README.md

# List all application statuses
grep -r "Status:" applications/*/README.md
```

## Directory Structure

| Directory | Purpose |
|-----------|---------|
| `applications/` | Active grant/fellowship application drafts |
| `entity-formation/` | LLC, Candid, GitHub Sponsors setup tracking |
| `strategy/` | Master institutional strategy + org structure research |
| `research/` | Funder-specific research (application requirements, deadlines) |
| `docs/` | Templates, governance documents |

## Key Documents

| File | Purpose |
|------|---------|
| `strategy/2026-03-24-organvm-institutional-strategy-master.md` | Master strategy — the synthesis |
| `strategy/2026-03-24-hybrid-org-structure-research.md` | 12 legal models analyzed |
| `research/2026-03-24-organvm-grant-funding-landscape.md` | 40+ funding sources |
| `research/2026-03-24-fiscal-sponsorship-research.md` | 13 fiscal sponsors compared |
| `entity-formation/ip-policy.md` | Open-core organ-to-license mapping |

## Application Identity Framing

Each funder sees ORGANVM through a different lens:

| Funder | Frame |
|--------|-------|
| NLnet | Infrastructure Builder — governance tooling for the digital commons |
| Creative Capital | Systems Artist — 117-repo living artwork |
| Aspiration Tech | Creative Technologist — open tech for ethical automation |
| Sloan | Independent Scholar — emerging digital infrastructure |
| NSF POSE | Ecosystem Builder — open-source ecosystem sustainability |

## Constraints

- **This is not a personal repo.** It governs ORGANVM-the-system, not a person's career. Personal job/consulting applications remain in `4444J99/application-pipeline/`.
- **Research docs are canonical here** but also mirrored in `organvm-corpvs-testamentvm/docs/` for the historical record.
- **IRF items** for this repo use the `IRF-INST-NNN` prefix (14 items as of S37).
- **Deadlines are hard.** NLnet: April 1, 2026. Creative Capital: April 2, 2026.
