# 来源索引（sources-index）

> 生成：2026-09-13  
> 本索引列出写入 `classified-memory.md` 时实际阅读/引用的路径。

## Agent 目录（14）

| 显示名 | Agent ID | 使用的文件 |
|--------|----------|------------|
| SIVE | `4ba186e6-8409-40d7-8f5f-d1a75e52beb9` | `memory/profile.md`, `memory/log/2026-08.md`, `memory/log/2026-09.md`, `profile.json`, `automations/sive-daily-research-digest/automation.json` |
| X | `55a49dcf-1e7b-4f26-9ba5-2035a1741690` | `memory/profile.md`, `memory/log/2026-08.md`, `memory/log/2026-09.md`, `profile.json`, `automations/x/automation.json` |
| Trade | `a8ee710b-bc09-4245-8946-75cf0d5647e6` | `memory/profile.md`, `memory/log/2026-09.md`, `profile.json` |
| 光互连 | `e4a94e78-5384-42b4-acbb-1417fc731a9d` | `memory/profile.md`, `memory/log/2026-09.md`, `profile.json`, `automations/ecoc-2026/automation.json` |
| 认知学习 | `8b1144cd-aa15-4efe-9ed3-d9f25d4835b3` | `memory/profile.md`, `memory/log/2026-09.md`, `profile.json` |
| Trade Strategy | `8a253cfb-b7b1-4473-b08b-6ac709c650b6` | `memory/log/2026-09.md`, `profile.json`；（attachments/*.md 为 quantscience 抓取副本，与 workspace 重复，未整篇入库） |
| 美股 | `c5e37a16-bf66-475b-80ce-5a17fa1cb527` | `memory/log/2026-09.md`, `profile.json` |
| 加密货币 | `fa28746e-1eec-43be-9124-473d7341675e` | `memory/log/2026-09.md`, `profile.json` |
| Reddit | `e6f8bfc2-c472-4e0e-a6ad-46f594b19f61` | `memory/profile.md`, `memory/log/2026-09.md`, `profile.json` |
| AI | `13a65f19-9486-4581-829f-ca00be3f25c2` | `profile.json`；transcript `agent-transcripts/.../13a65f19-….jsonl`（仅确认无实质记忆） |
| 记忆系统 | `2adb4fd0-6eee-48fc-bf72-64dc3ecb8b30` | `profile.json`；对照 `/workspace/BotMemory/*` |
| Researchy | `65501f27-1c36-46fe-baeb-1eebe2ca489c` | `profile.json` only |
| 工具 | `a68ddb65-ade1-4309-ad4c-0febbbd73e0c` | `profile.json` only |
| New Bot | `c428f1c6-37f7-498d-9679-7cb9db71fdab` | `profile.json` only |

## 工作流 / 仓库

- `/home/box/agent-data/workflows/dan-koe/SKILL.md`
- `/home/box/agent-data/workflows/dan-koe-2/SKILL.md`（存在；框架同类，未逐字展开）
- `/workspace/BotMemory/README.md`
- `/workspace/BotMemory/memory/profile/role.md`
- `/workspace/BotMemory/memory/episodes/2026-09-13-setup.md`
- `/home/box/agent-data/source-map.json`
- `/home/box/agent-data/agents/active-agent.json`
- `/home/box/agent-data/settings.json`（时区 Asia/Shanghai、pinned agent=X）

## Workspace 佐证（轻量引用，非全文入库）

- `/workspace/quantscience_strategies_kb.md`（及同目录 posts/raw/web_sources）
- `/workspace/portfolio_tech_2026-09-06.json`（持仓技术快照存在性）
- `/workspace/guangxin/`（光芯前沿知识库存在性）
- `/workspace/x-digest-2026-*.json` / `*-summary.txt`（X 早报产物）
- `/workspace/sive/`、`/workspace/crealights/`、`/workspace/uw/`（专项工件目录）

## Transcripts

已确认存在与命名 agent 对应的 jsonl（各 1 主文件），本轮**未全文挖掘**（优先 memory markdown）。抽样：

- `/home/box/agent-data/agent-transcripts/13a65f19-9486-4581-829f-ca00be3f25c2/13a65f19-9486-4581-829f-ca00be3f25c2.jsonl`

另有大量 `sand-subagent-*` transcript 目录（子代理跑批），未纳入本分类记忆。

## 明确未使用 / 跳过

- `box-secrets.json`、`host-secrets.json`、`chrome-cookie-seed.json`、各类 token
- 各 agent `conversation-blobs.db` / `store.db*`（体量大；内容应已部分沉淀进 memory log）
- `audit.jsonl`（操作审计，非用户偏好）
- Trade Strategy attachments 图片与重复 md 全文
