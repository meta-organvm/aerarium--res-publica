# Agent Handoff: claude → gemini

**Session:** 2026-03-30-dispatch-grant-cascade
**Phase:** BUILD
**Organ:** META-ORGANVM | **Repo:** aerarium--res-publica
**Scope:** Grant application drafting
**Timestamp:** 2026-03-30

## Summary

Two drafting tasks in this repo. Both benefit from Gemini's fresh context and velocity.

## Task 1: Draft Creative Capital Application

Read these files first:
- `research/2026-03-24-creative-capital-application-research.md`
- `research/2026-03-30-creative-capital-winners-analysis.md` (NEW — Perplexity research just landed)
- `applications/creative-capital-2027/bio.md`
- `applications/creative-capital-2027/work-sample-notes.md`
- `governance-rules.json` (the `entailment_flows` section)

Then draft all `[DRAFT]` fields in `applications/creative-capital-2027/draft.md`.

**Framing directives:**
- The eight-organ model IS the artwork
- AX-6 signal closure IS the formal innovation
- The consulting-to-research pipeline IS the practice
- Stay within character limits documented in the comments

## Task 2: (If capacity permits — lower priority)

This task is in a DIFFERENT repo (`organvm-v-logos`). Skip if focused on Task 1.

**Work Type:** content_generation

**CROSS-VERIFICATION REQUIRED** — Do not trust the originating agent's self-assessment. Verify all output.

## Locked Constraints (DO NOT OVERRIDE)

- Character limits in draft.md comments are hard limits — do not exceed
- The framing (eight-organ = artwork, AX-6 = innovation, pipeline = practice) is locked
- Do not modify governance-rules.json
- Do not add dependencies or change project structure

## Locked Files (DO NOT MODIFY)

- `governance-rules.json`
- `seed.yaml`
- `package.json` (if exists)
- Any `*.config.*` file

## Work Already Completed (DO NOT REPEAT)

- Perplexity research on Creative Capital winners (landed at research/2026-03-30-creative-capital-winners-analysis.md)
- Perplexity research on Sovereign Tech Fellowship (landed at research/2026-03-30-sovereign-tech-research.md)
- Perplexity research on ZKM Rauschenberg (landed at research/2026-03-30-zkm-rauschenberg-research.md)
- Perplexity research on Aspiration Tech (landed at research/2026-03-30-aspiration-tech-research.md)
- Prior Creative Capital research exists at research/2026-03-24-creative-capital-application-research.md

## Active Conventions

- **writing_voice**: Orchestrator Voice Constitution — system-first, precision, ontological coherence
- **formatting**: Markdown, conventional commits

## Receiver Restrictions

Files you MUST NOT touch:
- `governance-rules.json`
- `seed.yaml`
- `*.config.*`
- `.env*`
