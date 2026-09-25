# X 推文 Jev 质检题库（跨 bot 共用）

## 政策
- (2026-09-21，Yun Long) 接入 **Jev**（TypeSafe System One）；各 bot 检索 X 推文时须能判断**主题、是否水文、质量**。 〔引用：用户指令 2026-09-21〕
- MCP：共享电脑上的 `user-jev`（`npx -y jev-mcp`）。密钥：`TYPESAFE_API_KEY` / `/home/box/.config/typesafe/key`（勿写入本仓库）。
- 配套 skill：[X 推文 Jev 质检](sand-workflow:x-jev)（若 pill 未刷新，skill id 以 workflows 目录为准）。
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

## 2026-09-21 午/晚公开 PR 质检样例（X内容产出）
- (2026-09-21，X内容产出) MACOM ECOC demo PR 摘录 → theme=`optical_cpo`、非水文、quality≈**2.55**（保留）。 〔引用：/workspace/x-drafts/2026-09-21-noon.md〕
- (2026-09-21，X内容产出) OIF/Converge Digest EEI 摘录 → theme=`optical_cpo`、非水文、quality≈**2.05**（保留）。 〔引用：同 noon draft〕
- (2026-09-21，X内容产出) SIVE/Electronics Weekly 100 mW 摘录 → theme=`optical_cpo`、非水文、quality≈**2.61**（保留）。 〔引用：同 noon draft〕
- (2026-09-21，X内容产出) `$MRVL` ECOC 2nm demos PR 摘录 → theme=`optical_cpo`、shuiwen≈**0.11**、quality≈**2.33**（≥1.5 门槛，保留）。 〔引用：/workspace/x-drafts/2026-09-21-evening.md〕

## 2026-09-22 早/午/晚公开 PR 质检样例（X内容产出）
- (2026-09-22，X内容产出·早) `$LITE` ELSFP PR 摘录 → theme=`optical_cpo`、shuiwen≈0.06、quality≈**2.74**（保留）。 〔引用：/workspace/x-drafts/2026-09-22-morning.md〕
- (2026-09-22，X内容产出·早) Genuine Optics 6.4T NPO → `optical_cpo`、0.10、**2.51**（保留）。 〔引用：同 morning〕
- (2026-09-22，X内容产出·早) @cherryPayment INTC Agentic → `servers_power_storage`、0.12、**1.92**（≥1.5 保留）。 〔引用：同 morning〕
- (2026-09-22，X内容产出·午) `$COHR` 周二议程 → `optical_cpo`、0.10、**2.51**；CUbIQ×COHR QKD → 0.11、**2.34**；VCSEL/UHP/FlexConnect → 0.14、**2.28**（均保留）。 〔引用：/workspace/x-drafts/2026-09-22-noon.md〕
- (2026-09-22，X内容产出·晚) OIF 周三议程 → `optical_cpo`、0.08、**2.66**；`$AXTI`–Lumentum InP → 0.08、**2.78**；`$SIVE` booth 2106 双钟 → 0.08、**2.73**（均保留）。 〔引用：/workspace/x-drafts/2026-09-22-evening.md〕


## 2026-09-23 早/午/晚公开 PR 质检样例（X内容产出）
- (2026-09-23，X内容产出·早) Lessengers glass NPO → theme=`optical_cpo`、shuiwen≈0.15、quality≈**2.13**（保留）。 〔引用：/workspace/x-drafts/2026-09-23-morning.md〕
- (2026-09-23，X内容产出·早) `$COHR` 周三 PIC/VCSEL 议程 → `optical_cpo`、0.07、**2.94**（保留）。 〔引用：同 morning〕
- (2026-09-23，X内容产出·早) OIF 现场互通墙 → `optical_cpo`、0.07、**2.65**（保留）。 〔引用：同 morning〕
- (2026-09-23，X内容产出·午) Lightmatter Open CPX → `optical_cpo`、0.05、**2.95**；GF×SMART → 0.12、**2.40**；NewPhotonics×Tower → 0.07、**2.78**（均保留）。 〔引用：/workspace/x-drafts/2026-09-23-noon.md〕
- (2026-09-23，X内容产出·晚) `$MRVL` ECOC PR → `optical_cpo`、shuiwen≈**0.14**、quality≈**2.28**；`$COHR` PhotonLink → **0.09**、**2.75**；`$SIVE` CW DFB 公开事实 → **0.09**、**2.48**（均保留）。 〔引用：/workspace/x-drafts/2026-09-23-evening.md〕

## 2026-09-24 午/晚公开 PR 质检样例（X内容产出；缺 morning）
- (2026-09-24，X内容产出·午) Photon Bridge DWDM → `optical_cpo`、shuiwen≈**0.10**、quality≈**2.60**；`$COHR` 周四会场日历 → **0.08**、**2.70**；FlexConnect 光纤装配 → **0.16**、**2.06**（均 ≥1.5 保留）。 〔引用：/workspace/x-drafts/2026-09-24-noon.md〕
- (2026-09-24，X内容产出·晚) `$MRVL` 400G/lane 摘录 → `optical_cpo`、**0.11**、**2.62**；Furukawa Snap-Beam → **0.08**、**2.55**；`$SIVE` 100 mW → **0.09**、**2.69**（均保留）。 〔引用：/workspace/x-drafts/2026-09-24-evening.md〕


## 2026-09-25 早/午/晚公开 PR 质检样例（X内容产出）
- (2026-09-25，X内容产出·早) `$MU` HBM 产能摘录 → theme=`memory_hbm`、shuiwen≈**0.05**、quality≈**2.81**（保留）。 〔引用：/workspace/x-drafts/2026-09-25-morning.md〕
- (2026-09-25，X内容产出·早) `$SNDK` NBM → `memory_hbm`、**0.08**、**2.16**（action=abstain；≥1.5 保留并标 IR）。 〔引用：同 morning〕
- (2026-09-25，X内容产出·早) HBM 晶圆税 → `memory_hbm`、**0.08**、**2.49**（保留）。 〔引用：同 morning〕
- (2026-09-25，X内容产出·午) EMIB-T/Humufish → theme=`foundry_packaging`、shuiwen≈**0.10**、quality≈**2.03**（action=review；≥1.5 保留并标行业转述）。 〔引用：/workspace/x-drafts/2026-09-25-noon.md〕
- (2026-09-25，X内容产出·午) `$AMKR` Arizona PR → `foundry_packaging`、**0.05**、**2.84**；SPIL 斗六+`$TSM` CoWoS → **0.05**、**2.86**（均保留）。 〔引用：同 noon〕
- (2026-09-25，X内容产出·晚) `$AVGO` Davisson → theme=`optical_cpo`、shuiwen≈**0.06**、quality≈**2.85**；`$CRDO` ZeroFlap → **0.05**、**2.85**（theme action=review，仍 ≥1.5）；`$SIVE` Q2/Glasgow → **0.06**、**2.84**（均非水文、保留）。 〔引用：/workspace/x-drafts/2026-09-25-evening.md〕
