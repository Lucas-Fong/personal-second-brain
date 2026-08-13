---
name: personal-second-brain
description: "Route a user's task before answering: determine whether to search their Notion-based personal second brain, use external tools directly, or combine both. Use for career materials, product/AI/data/management viewpoints, learning synthesis, writing, personal planning, weekly reviews, and any task that may benefit from the user's documented experience, knowledge, decisions, or preferences."
---

# Personal Second Brain Router

Read `references/router.md` at the start of every task covered by this skill. It is the authoritative operating protocol.

## Required behavior

1. Classify the request before calling a substantive tool.
2. Use the prescribed Notion retrieval order when personal evidence, preferences, past work, or documented learning materially improves the answer.
3. Use external tools directly for current facts, public research, or generic execution that does not need personal context.
4. Combine Notion and external tools when a task needs both personal context and current/public facts. Clearly distinguish them in the result.
5. Treat Notion as the source of truth for personal facts. Do not invent career facts or present external material as the user's view.
6. Produce a draft by default. Write back only after the user explicitly says to write, archive, or finalize.

## Platform adaptation

- In Codex, use the connected Notion tools after reading the router.
- In WorkBuddy, Trae, or another MCP-capable agent, connect the same Notion workspace and load this folder as a skill/project instruction. Follow the same route and write-back gate.
- If Notion tools are unavailable, ask for the relevant Notion exports/pages or use only provided context; state that the personal knowledge base was not queried.

