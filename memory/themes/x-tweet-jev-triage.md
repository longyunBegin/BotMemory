# X 推文 Jev 质检题库（跨 bot 共用）

## 政策
- (2026-09-21，Yun Long) 接入 **Jev**（TypeSafe System One）；各 bot 检索 X 推文时须能判断**主题、是否水文、质量**。 〔引用：用户指令 2026-09-21〕
- MCP：共享电脑上的 `user-jev`（`npx -y jev-mcp`）。密钥：`TYPESAFE_API_KEY` / `/home/box/.config/typesafe/key`（勿写入本仓库）。
- 配套 skill：[X 推文 Jev 质检](sand-workflow:x-tweet-jev-triage)（若 pill 未刷新，skill id 以 workflows 目录为准）。
- 仍禁止 Grok Build（见 `x-via-grok-build.md` / standing-policy）。

## 标准三题（一次 `jev_ask`）

### 1. theme（classify，`add_none: false`）
Question: Primary research theme of this X post for Yun Long's AI semiconductor / optical interconnect investing desk. Pick the single best fit.

| option | description |
|--------|-------------|
| memory_hbm | DRAM/HBM/NAND pricing, capacity, sold-out, or memory vendors (MU, SK hynix, SNDK, etc.) |
| optical_cpo | CPO, ELS/ELSFP, lasers, InP, optical interconnect, ECOC/CIOE, SIVE/COHR/LITE/AXTI optics |
| foundry_packaging | Foundry, advanced packaging, CoWoS, TSMC capacity, OSAT |
| networking | Ethernet/InfiniBand/switch/NIC/DSP, Arista/CIEN/MRVL networking angle |
| servers_power_storage | Servers, power, enterprise storage, data-center physical layer |
| macro_markets | Macro, rates, positioning, crowding, ETF flows, broad market tape |
| company_specific | Single-name fundamental update not mainly one of the above themes |
| other_noise | Off-topic, meme, pure engagement, or not useful for this desk |

### 2. is_shuiwen（check）
Question: Is this post 水文 / low-substance filler for research purposes?
- yes_means: Mostly vibes, recycled slogans, engagement bait, no new number/claim/source, or empty takes.
- no_means: Has a concrete claim, number, timeline, named source, or falsifiable thesis worth remembering.
- 默认：`yes_at_or_above=0.7`，`no_at_or_below=0.3`

### 3. quality（score）
Question: Research quality for an AI hardware / optical interconnect investor who wants hard points, not vibes.

Levels（低→高，index 0–3）:
0. Noise or misleading. Skip.
1. Thin. Soft opinion or already-known narrative without new evidence.
2. Useful. Clear claim with some number, source, or structure.
3. High value. Hard data, primary source, or sharp falsifiable thesis worth filing.

## 默认门槛
- **丢弃**：`is_shuiwen` yes（≥0.7）或 `quality` 加权分 &lt; 1.5 或 theme=`other_noise`
- **优先引用/入库**：`quality` ≥ 2.0 且非水文
- Choice/Score 的 `action=review|abstain`：不当铁板结论

## 冒烟结果（2026-09-21）
样例文：`$MU 2026 HBM largely sold out; SK hynix … 2030. NVDA CFO … extreme … 2028.`
- theme=`memory_hbm`（conf 1.0, act）
- is_shuiwen noul≈0.14（非水文）
- quality≈1.68（review；偏 Useful）
- 模型：`jev-1.13.0`（`jev-latest`）

## 用法提示
- 拉帖仍走浏览器或有额度时的 X MCP；**拉完用 Jev 过滤**再写早报/入库。
- 大批量：`jev_triage`（path/text 逐条）。
