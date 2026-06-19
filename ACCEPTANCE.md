# Acceptance Tests - AI Research Trail Organizer

## Overview
- **Skill:** AI Research Trail Organizer
- **Slug:** ai-research-trail-organizer
- **Priority:** P1
- **Project:** daily-50-skills-2026-05-08
- **Total Tests:** 10

## AT-1: User-provided scope is explicit.
- **Check:** Output states the trail is built only from pasted or supplied snippets, notes, and links.
- **Expected:** No implication that the assistant accessed files, chats, folders, accounts, or the web.
- **Pass:** Scope boundary is visible in the final output.

## AT-2: Fragments are normalized.
- **Check:** Pasted material is broken into labeled fragments or equivalent traceable units.
- **Expected:** Each fragment has a short summary and any provided source clues.
- **Pass:** The user can trace output back to their supplied material.

## AT-3: Topic clusters are created.
- **Check:** Related fragments are grouped by topic.
- **Expected:** Each cluster has a name, included fragments, and a concise summary.
- **Pass:** Clustering is coherent and does not force unrelated items together.

## AT-4: Claims are extracted clearly.
- **Check:** Key claims are separated from questions and interpretations.
- **Expected:** Claims are concise and understandable.
- **Pass:** Claims can be reviewed independently.

## AT-5: Support level is labeled.
- **Check:** Each claim is marked supported, partially supported, unsupported, or question.
- **Expected:** Labels reflect only the supplied evidence.
- **Pass:** Unsupported claims are not presented as facts.

## AT-6: Evidence is linked to claims.
- **Check:** Claims reference fragment numbers, source names, or links supplied by the user.
- **Expected:** Missing evidence is marked as missing rather than invented.
- **Pass:** Evidence mapping is traceable.

## AT-7: Source gaps and conflicts are flagged.
- **Check:** Weak sources, missing primary sources, conflicts, and AI-only claims are identified.
- **Expected:** Gaps are concrete enough to guide follow-up.
- **Pass:** Risky research areas are visible.

## AT-8: Privacy risks are flagged.
- **Check:** Personal, sensitive, proprietary, or identifying details are noted when present.
- **Expected:** The skill recommends redaction or separation from shareable output.
- **Pass:** The final trail does not unnecessarily expose private details.

## AT-9: Next actions are prioritized.
- **Check:** The output ends with 3 to 8 concrete next actions.
- **Expected:** The first action can be completed quickly.
- **Pass:** The user knows what to do next.

## AT-10: No-code compliance.
- **Check:** The skill remains prompt-only.
- **Expected:** `requires_api` is false, `no_code_execution` is true, and no executable steps are required.
- **Pass:** Skill has no scripts, tools, API calls, credentials, or network dependency.

## Clean Scan Evidence

Verify the skill directory contains exactly these files with no unexpected artifacts:

| File | Expected | Check |
|---|---|---|
| SKILL.md | Present, valid YAML frontmatter, English-only | [x] |
| skill.json | Present, valid JSON, version 1.0.1, license MIT-0 | [x] |
| ACCEPTANCE.md | Present, English-only | [x] |
| Extra files | None — no scripts, logs, screenshots, build outputs, temp files, or hidden artifacts | [x] |
| Secrets scan | No API keys, tokens, passwords, credentials, or PII | [x] |
| Executable scan | No executable code, package files, automation hooks, or network handlers | [x] |

## Install-First Success Path

1. **Input:** User says "I've been pasting AI chat outputs into a notes file for a month and it's chaos. Help me organize these snippets into a research trail with claims, evidence, and next actions."
2. **Steps:** The skill guides the assistant to: (a) confirm scope — trail is built only from user-supplied snippets, (b) normalize pasted material into labeled fragments with source clues, (c) group fragments into 3-7 topic clusters, (d) extract claims and label support level — supported, partially supported, unsupported, or question, (e) link claims to supplied evidence fragments, (f) flag source gaps, conflicts, unsupported claims, and private data, (g) produce a compact research trail with open questions and prioritized next actions.
3. **Output:** A Research Trail document with research question, topic clusters, claim-and-evidence map with support labels, open questions, source gaps, privacy flags, and 3-8 prioritized next actions — built only from user-provided snippets with no file access, web browsing, or invented citations.

Expected first-run outcome: The user receives a clean, organized research trail from their scattered AI chat snippets, with claims clearly labeled by evidence support and concrete next steps to fill gaps.
