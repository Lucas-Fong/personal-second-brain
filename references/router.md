# Personal Second Brain: Routing Protocol

## 1. Decide the route first

| Request signal | Route |
|---|---|
| Resume, JD, interview, career narrative, work achievements, self-introduction | Search the second brain first. |
| Personal view, product/AI/data/management analysis, article in the user's voice | Search the second brain first. |
| Summarize or organize a user-provided Notion page, reading note, course, book highlights, journal | Search the named material first. |
| Weekly review, next actions, project progress, habit reflection | Search Todo List and Daily Tasks first. |
| Current news, laws, product specs, public market data, web research | Use external research first. Add second-brain search when the answer should reflect the user's context, decisions, or past work. |
| Simple generic transformation with no personal context | Answer or use the relevant tool directly; do not search the second brain. |
| Ambiguous request where personal context may help | Search the most likely relevant layer when that can resolve the ambiguity; otherwise ask one concise question. |

## 2. Notion is the single source of truth

Notion is the authoritative store for the user's personal facts, knowledge, decisions, and durable outputs. AI clients and this skill are execution and routing layers, not competing knowledge stores.

### Career output

Use this order: **任职经历 / 项目与成果等可核验职业证据 → 个人观点与输出（已定稿） → 简历 / 项目原页 → Todo List 相关项目**.

For external resumes, JD matches, interviews, and recruiter messages, use only evidence explicitly recorded as verified or suitable for external use. List missing evidence instead of inventing it.

### Knowledge, viewpoints, and articles

Use this order: **知识卡片 → 个人观点与输出（已定稿） → 学习笔记 / 微信读书同步 → 收藏笔记**.

Knowledge cards use `所属知识主题` as their sole formal knowledge-system relation. Do not recreate a parallel coarse topic taxonomy in the skill.

Separate: (a) the user's confirmed view, (b) provisional/draft personal knowledge, (c) external source claims, and (d) AI inference.

### Action and reflection

Use this order: **Todo List → 每日任务 → linked career/knowledge/raw material**.

Todo List is the sole task and project execution system. Daily Tasks is for habits, diary, reading, and reflection. Do not create a parallel task store.

### Raw inputs

- 收藏笔记: external/raw collected material. It is not automatically the user's view.
- 学习笔记: books, courses, training notes.
- 微信读书同步: bookshelf, highlights, notes, chapters, and reading statistics. Use as evidence for synthesis, not as a license to reproduce books.

## 3. Knowledge confidence and retrieval

A knowledge-card status represents **confidence/maturity, not permission to use it**.

Default priority: **已确认 > 待复盘 > 草稿 >>> 已废弃**.

- **已确认**: primary basis for analysis, judgment, and output.
- **待复盘**: usable; disclose its provisional status when it materially affects a key judgment.
- **草稿**: usable as supporting context, hypotheses, or inspiration. Never present it as the user's confirmed final position. If it conflicts with confirmed knowledge, confirmed knowledge wins.
- **已废弃**: exclude by default. Use only for explicit historical/version analysis.

If confirmed knowledge is insufficient, progressively expand retrieval to 待复盘 and 草稿 rather than treating drafts as unusable.

## 4. Make second-brain usage visible

When retrieved second-brain knowledge materially affects the response, append a compact section such as:

**🧠 第二大脑调用**
- 「卡片名称」｜已确认
- 「卡片名称」｜草稿

Rules:
- List only cards or durable personal assets actually used in the reasoning/output, not every search hit.
- Preserve each item's maturity/status.
- Do not render this section when the second brain was not actually used.
- If the platform supports source citations, cite the underlying Notion item as well.

This visible trace is the user's evidence that the second brain is being actively used rather than merely stored.

## 5. Practice feedback and knowledge evolution

After a task involving real work, a decision, learning, output, or reflection, check whether the interaction generated one of these signals:

1. **验证** — an existing idea/method was supported in a real situation.
2. **修正** — evidence suggests an existing judgment needs adjustment.
3. **边界** — a new applicability or non-applicability condition emerged.
4. **升级** — a more mature model, method, or judgment emerged.
5. **新知识** — a durable insight is not adequately covered by existing cards.

If there is a meaningful signal, append a concise section such as:

**♻️ 知识反哺建议**
- 建议更新「卡片名称」：补充……
- 原因：本次实践验证 / 修正 / 补充了……

Do not force a feedback suggestion when nothing durable was learned.

Knowledge should mature through use rather than administrative cleanup alone. Typical evolution:

**草稿 → 被调用 → 实践反馈 → 待复盘 → 多次验证或明确确认 → 已确认**

Confirmed knowledge can return to review or be superseded when new evidence contradicts it. Preserve meaningful historical versions as 已废弃 when useful for traceability.

## 6. Draft and write-back gate

Default to a draft. Before write-back, show or describe the target database/page, intended change, source/evidence, and uncertain facts when relevant.

Write only after the user clearly approves writing, archiving, finalizing, saving to Notion, or an equivalent action. A feedback suggestion alone is not approval to write.

Typical write targets:

| Confirmed item | Destination |
|---|---|
| Verified work, projects, metrics, credentials | 任职经历 / 项目与成果 or the current formal career-evidence store |
| Reusable concept, method, case, or insight | 知识卡片 |
| Confirmed viewpoint, article, resume version, JD matching, outreach, interview material | 个人观点与输出 |
| Follow-up work | Todo List |
| Habit, reading log, diary, daily reflection | 每日任务 |

Never bulk move, overwrite, or delete historical notes without explicit approval. Preserve raw sources.

## 7. Cross-platform setup

Keep this skill folder in GitHub or another synchronized location. ChatGPT, Codex, WorkBuddy, Trae, and other clients should use the same Notion workspace and the same protocol version.

Startup/project instruction:

> Before handling a task that may materially benefit from my experience, knowledge, decisions, preferences, projects, or personal plans, read `SKILL.md` and `references/router.md` from the Personal Second Brain skill. Use my connected Notion workspace as the source of truth. Apply knowledge confidence as 已确认 > 待复盘 > 草稿 >>> 已废弃. When second-brain knowledge materially affects the answer, show the knowledge actually used and its status. After real practice, identify meaningful validation, correction, boundary, upgrade, or new knowledge and propose a write-back; do not modify Notion without my approval.

MCP-capable platforms should connect to the same Notion workspace. Prefer read access by default and explicit confirmation for writes where the platform supports permission separation.

## 8. Prompt patterns

- “根据这个 JD，仅使用可核验的职业证据，生成匹配分析、简历草稿和打招呼语；列出缺失证据。”
- “整理这个 Notion 页面，提炼不超过三张知识卡片草稿，区分来源观点和我的理解。”
- “基于我的知识卡片和已定稿观点写一篇关于 X 的文章；告诉我实际调用了哪些知识卡片。”
- “复盘本周 Todo List 和每日任务，给出完成情况、卡点和下周三项优先行动；如果产生可复用的新认知，提出知识反哺建议。”
