# Personal Second Brain: Routing Protocol

## 1. Decide the route first

| Request signal | Route |
|---|---|
| Resume, JD, interview, career narrative, work achievements, self-introduction | Search the second brain first. |
| Personal view, product/AI/data/management analysis, article in the user's voice | Search the second brain first. |
| Summarize or organize a user-provided Notion page, reading note, course, book highlights, journal | Search the named material first. |
| Weekly review, next actions, project progress, habit reflection | Search Todo List and Daily Tasks first. |
| Current news, laws, product specs, public market data, web research | Use external research first. Add second-brain search only when the answer should reflect the user's context, decisions, or past work. |
| Simple generic transformation (translation, formatting, code explanation) with no personal context | Answer or use the relevant tool directly; do not search the second brain. |
| Ambiguous request where personal context may help | Ask one concise question, or search the most likely relevant layer and state the assumption. |

## 2. Notion map and retrieval order

### Career output

Use this order: **职业资产 → 个人观点与输出（已定稿） → 个人简历 / 项目原页 → Todo List 相关项目**.

Use only assets marked `可对外使用` or `已验证` for external resumes, JD matches, interviews, and recruiter messages. List missing evidence instead of inventing it.

### Knowledge, viewpoints, and articles

Use this order: **知识卡片 → 个人观点与输出（已定稿） → 学习笔记 / 微信读书同步 → 收藏笔记**.

Separate: (a) the user's confirmed view, (b) external source claims, and (c) AI inference.

### Action and reflection

Use this order: **Todo List → 每日任务 → linked career/knowledge/raw material**.

Todo List is the sole task and project system. Daily Tasks is for habits, diary, reading, and reflection. Do not create a parallel task store.

### Raw inputs

- 收藏笔记: Folo → WeChat → SendToNotion articles. These are external raw material, not personal views.
- 学习笔记: books, courses, training notes.
- 微信读书同步: bookshelf, highlights, notes, chapters, and reading statistics. Use as evidence for synthesis, not as a license to reproduce books.

## 3. Draft and write-back gate

Default to a draft. Before any write-back, show or describe: target database, title, key fields, source links, and any uncertain facts.

Write only if the user explicitly says one of: “写入”, “归档”, “定稿”, “保存到 Notion”, or equivalent clear approval.

Write targets:

| Confirmed item | Database |
|---|---|
| Verified work, projects, metrics, credentials | 职业资产 |
| Reusable concept, method, case, or insight | 知识卡片 |
| Confirmed viewpoint, article, resume version, JD matching, outreach, interview material | 个人观点与输出 |
| Follow-up work | Todo List |
| Habit, reading log, diary, daily reflection | 每日任务 |

Never bulk move, overwrite, or delete historical notes. Preserve legacy tags in 收藏笔记.

## 4. Cross-platform setup

Keep this skill folder in a Git repository or synced folder. In every AI platform, configure a startup/project instruction equivalent to:

> Before handling a task that may benefit from my experience, knowledge, decisions, preferences, projects, or personal plans, read `SKILL.md` and `references/router.md` from the Personal Second Brain skill. Follow its routing decision and write-back gate. Use my connected Notion workspace as the source of truth for personal facts.

MCP-capable platforms should receive a Notion connector with read access by default. Grant write access only for explicit confirmation flows.

## 5. Prompt patterns

- “根据这个 JD，仅使用可对外使用的职业资产，生成匹配分析、简历草稿和打招呼语；列出缺失证据。”
- “整理这个 Notion 页面，提炼不超过三张知识卡片草稿，区分来源观点和我的理解。”
- “基于我的知识卡片和已定稿观点，写一篇关于 X 的文章；标注个人判断和外部事实。”
- “复盘本周 Todo List 和每日任务，给出完成情况、卡点和下周三项优先行动。”
