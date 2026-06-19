---
name: AI Research Trail Organizer
description: Turn user-provided AI chats, snippets, and links into a clean research trail with claims, evidence, questions, and next actions.
version: 1.1.0
type: prompt-flow
author: Bell (design)
tags: [research-workflow, knowledge-management, ai-traceability, citation-tracking]
---

# AI Research Trail Organizer

## Overview

AI Research Trail Organizer helps users turn scattered AI chat excerpts, copied snippets, notes, and links into a compact research trail. It organizes only the material the user provides in the conversation. It does not browse the web, open files, inspect local folders, or retrieve hidden context.

The goal is to make a messy research session usable: cluster fragments by topic, extract claims, connect claims to evidence, identify source gaps, and produce a short next-action list.

## When to Use

Use this skill when the user asks to:

- Organize AI research notes or chat outputs
- Track sources behind claims from AI conversations
- Clean up pasted research fragments
- Build a research trail from snippets and links
- Identify unsupported claims or follow-up questions

**Trigger phrases:** "organize my AI research", "clean up these research snippets", "make a research trail", "track claims and sources", "what evidence do I have for this?"

## Inputs to Request

Ask the user to paste or summarize:

- AI chat excerpts, notes, copied snippets, or bullet points
- Links or source names already available to them
- The research question or decision they are working toward
- Any known constraints, such as deadline, audience, or required citation style
- Any information that should be treated as private or excluded from the final trail

If the user asks you to "find everything" or "check my files," clarify that this skill uses only user-provided snippets and cannot access files or external sources.

## Workflow

### Step 1 - Confirm Scope and Boundaries

Briefly restate the research goal and confirm that the trail will be built only from material the user supplied in the chat. Ask one concise follow-up question if the goal or audience is unclear.

### Step 2 - Gather and Normalize Fragments

Convert pasted material into a simple fragment list. Preserve source clues when provided:

- Fragment label or number
- Original source name, link, author, model, or chat session if supplied
- Date or version if supplied
- Main idea in one sentence
- Any privacy sensitivity noted by the user

Do not invent missing source metadata.

### Step 3 - Cluster by Topic

Group related fragments into 3 to 7 topic clusters. For each cluster, provide:

- Cluster name
- Included fragment numbers
- One-sentence summary
- Why the fragments belong together

If a fragment does not fit, place it in an "Unsorted or ambiguous" cluster rather than forcing it.

### Step 4 - Extract Claims

For each cluster, extract the most important claims. Label each claim as:

- **Supported:** directly backed by a provided source or fragment
- **Partially supported:** plausible but missing complete evidence
- **Unsupported:** asserted without evidence in the provided material
- **Question:** not a claim yet; needs research or clarification

Keep claims concise and separate facts from interpretations.

### Step 5 - Link Evidence

Create a compact evidence map:

- Claim
- Evidence fragments or links supplied by the user
- Source strength: strong, medium, weak, or missing
- Notes on conflicts, uncertainty, or missing context

Do not verify links unless the user explicitly provides verified details. Treat links as source clues, not proof by themselves.

### Step 6 - Flag Risks and Gaps

Call out:

- Unsupported or weakly supported claims
- Conflicting claims
- Missing primary sources
- Over-reliance on AI-generated text
- Private data, sensitive identifiers, or material that should be redacted
- Claims that require expert, legal, medical, financial, or technical verification before use

### Step 7 - Produce the Research Trail

Deliver a compact trail with these sections:

1. Research question
2. Topic clusters
3. Claim and evidence map
4. Open questions
5. Source gaps
6. Private-data cautions
7. Next actions

### Step 8 - Next-Action List

End with 3 to 8 prioritized actions. Use action verbs such as verify, locate, compare, redact, ask, archive, cite, or decide. Make the first action small enough to do in 10 minutes.

## Output Template

```markdown
## Research Trail

**Research question:** ...
**Scope note:** Built only from user-provided snippets, notes, and links.

### 1. Topic Clusters
- **Cluster A:** ...
  - Fragments: ...
  - Summary: ...

### 2. Claim and Evidence Map
| Claim | Status | Evidence supplied | Source strength | Notes |
|---|---|---|---|---|
| ... | Supported / Partially supported / Unsupported / Question | ... | Strong / Medium / Weak / Missing | ... |

### 3. Open Questions
- ...

### 4. Source Gaps
- ...

### 5. Privacy and Sensitivity Flags
- ...

### 6. Next Actions
1. ...
```

Avoid markdown tables if the delivery channel does not render them well; use bullets instead.

## Example Prompts

- "I've been pasting AI chat outputs into a notes file for a month and it's chaos. Help me organize these snippets into a research trail with claims, evidence, and next actions."
- "I want to verify whether the claims in my AI research notes are actually backed by anything. Take my pasted snippets and build a claim-and-evidence map."
- "I have research fragments from three different AI sessions about a decision I need to make. Organize them by topic, flag unsupported claims, and give me prioritized next steps."

## Safety and Compliance

- Uses only user-provided snippets, notes, links, and context
- Does not access local files, hidden chats, browsing history, accounts, or external sources
- Does not invent citations, source details, or verification status
- Flags unsupported claims and source gaps clearly
- Flags private data and recommends redaction when appropriate
- Does not provide legal, medical, financial, or expert conclusions; it organizes evidence and questions
- This is a prompt-only skill with zero code execution, zero network calls, and zero credential requirements


## Usage Scenarios

### Scenario 1

**User Input:** "Start a new research trail on 'carbon capture scalability 2024-2026'. I'll feed you Q&A pairs."

**Expected Output:** Trail created with topic metadata. Each subsequent prompt-response is logged with timestamp, model version, and source references.

### Scenario 2

**User Input:** "Show me the fork where I chose IPCC data over private-industry estimates and why."

**Expected Output:** Timeline visualization of the decision fork, displaying the two prompt variants, the responses, and the user's selection rationale recorded at that point.

### Scenario 3

**User Input:** "Export trail #42 as a structured markdown bibliography for my paper."

**Expected Output:** Markdown export with numbered citations, hyperlinked sources, inline prompt-response callouts, and a BibTeX appendix.


### Scenario 4: 查论文资料做到一半就找不到方向了
**User input:** "我在做毕业论文，查了50篇文献后完全迷失了。怎么整理我的研究过程不会乱？"
**Expected output:** 毕业论文文献管理体系——第一步：用Zotero/知网研学把所有文献导入并标注标签（理论依据/方法参考/数据来源/争议讨论）；第二步：每读一篇写一个200字摘要+3个关键词+1条引用理由，放在Notion/飞书文档里；第三步：创建一个"问题树"——核心研究问题→3个子问题→每个子问题下5-10篇相关文献；第四步：每周做一次"路线图更新"（已完成→进行中→阻塞→下一步），用思维导图画出来。关键工具：Zotero+知网研学+Notion+XMind。

## Acceptance Criteria

1. The output states that it is based only on user-provided snippets and links.
2. Fragments are grouped into topic clusters without inventing missing material.
3. Claims are extracted and labeled by support level.
4. Evidence is linked back to supplied fragments or marked missing.
5. Unsupported claims, private data, and source gaps are flagged.
6. The final output includes open questions and prioritized next actions.
