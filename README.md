# AI Research Trail Organizer

Turn scattered AI chat excerpts, snippets, and links into a clean research trail with claims, evidence, questions, and next actions.

## What it does
- Cluster research fragments by topic and extract key claims from pasted material
- Label every claim by support level: supported, partially supported, or unsupported
- Flag source gaps, private data risks, and produce prioritized next-action lists

## Example scenarios

**1. 查论文资料做到一半就找不到方向了**
> 👤 我在做毕业论文，查了50篇文献后完全迷失了。怎么整理我的研究过程不会乱？
> 🤖 毕业论文文献管理体系——第一步：用Zotero/知网研学把所有文献导入并标注标签（理论依据/方法参考/数据来源/争议讨论）；第二步：每读一篇写200字摘要+3个关键词+1条引用理由；第三步：创建"问题树"——核心研究问题→3个子问题→每个子问题下5-10篇相关文献；第四步：每周做一次"路线图更新"用思维导图画出来。

**2. Start a new research trail**
> 👤 Start a new research trail on 'carbon capture scalability 2024-2026'. I'll feed you Q&A pairs.
> 🤖 Trail created with topic metadata. Each subsequent prompt-response is logged with timestamp, model version, and source references.

**3. Export trail as structured bibliography**
> 👤 Export trail #42 as a structured markdown bibliography for my paper.
> 🤖 Markdown export with numbered citations, hyperlinked sources, inline prompt-response callouts, and a BibTeX appendix.
