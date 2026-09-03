---
name: personal-second-brain
description: Use when a task may materially benefit from the user's documented experience, knowledge, decisions, preferences, projects, personal plans, career evidence, learning, or prior viewpoints.
---

# Personal Second Brain Router

Read `references/router.md` at the start of every task covered by this skill. It is the authoritative execution and routing protocol. The cross-platform collaboration policy is maintained in Notion; this skill implements that policy across AI clients.

## Required behavior

1. Classify the request before calling a substantive tool.
2. Search the connected Notion second brain when personal evidence, preferences, past work, documented learning, or prior decisions can materially improve the answer.
3. Use external tools directly for current facts, public research, or generic execution that does not need personal context.
4. Combine Notion and external tools when a task needs both personal context and current/public facts, and clearly distinguish the two.
5. Treat Notion as the source of truth for personal facts and knowledge. Do not copy concrete personal knowledge into this skill as a competing long-term source.
6. Apply knowledge-card confidence in this order: **已确认 > 待复盘 > 草稿 >>> 已废弃**. Draft cards remain usable as supporting context, but must not be presented as the user's confirmed final view. Deprecated cards are excluded by default.
7. When second-brain knowledge materially affects the answer, make the usage visible with a concise `🧠 第二大脑调用` section listing only the cards actually used and their status. Do not show this section when the second brain was not used.
8. After real work, decisions, learning, output, or reflection, check whether the interaction produced a **验证 / 修正 / 边界 / 升级 / 新知识** signal. If so, propose a concise `♻️ 知识反哺建议` identifying what should change and where.
9. Produce a draft by default. Do not write back merely because a feedback opportunity exists. Modify Notion only after the user explicitly approves writing, archiving, finalizing, saving, or an equivalent action.
10. Prefer knowledge evolution through use: 草稿 → 被调用 → 实践反馈 → 待复盘 → 多次验证/明确确认 → 已确认. Confirmed knowledge may return to review or be superseded when new evidence contradicts it.

## Platform adaptation

- ChatGPT, Codex, WorkBuddy, Trae, and other MCP-capable agents should connect to the same Notion workspace and load this skill or an equivalent project instruction.
- The skill is the portable execution layer; Notion remains the authoritative personal knowledge source.
- If Notion tools are unavailable, ask for the relevant Notion exports/pages or use only provided context; explicitly state that the personal knowledge base was not queried.
- Do not maintain platform-specific copies of personal facts or knowledge unless they are temporary runtime context.
