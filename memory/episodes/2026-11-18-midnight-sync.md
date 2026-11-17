# 日常同步：2026-11-17（~2026-11-18 00:12–00:30 Asia/Shanghai；覆盖日历日 **2026-11-17** 周二）

> 基线：昨夜午夜 `27c8b20`（覆盖 11/16，当时 11/16 尚未官方收盘，SIVE 未定盘 last **13.97**、FI Sum **6.86**）+ 对话补录 `f08d1f5`（覆盖 11/16）。其后远端已快进：Muse 00:30 日记/自精编 `ecc5a95`（覆盖 Muse 的 11/16 工作，并新建 `anthropic-ipo.md`、`micron.md`），以及 Muse 11/17 06:00 六看板刷新 `ab6ef48`（已用 11/16 收盘：SIVE **13.97**、AAOI **45.16**、AXTI **38.46**、MRVL **145.36**）。本文件**只**记 **11/17** 午夜扫描增量，并交叉上述已入库 Muse 提交；**不重抄、不改写**对方日记、主题旧行、看板文件或昨夜 midnight/catchup。本轮开始时斯德哥尔摩 11/17 交易仍未收盘（17:30 CET = 00:30 上海），美股 11/17 仍在盘中——凡 11/17 报价一律记为**未定盘 last**，不以之覆盖 11/16 官方定盘。本轮在 Muse 00:30 窗口前结束推送。

## 范围
- 动态助手名册：`/home/box/agent-data/agents/*/profile.json` 共 **18**，**无新助手**（完整 id 见下表）。Muse **不在** `/home/box`，按站立政策由其自精编；本轮只读已推送的 `memory/agents/muse/` 与 artifacts（含 `ecc5a95`、`ab6ef48`），不写其 `agents/` 目录。
- 扫描：Yahoo v8 chart API（`/workspace/yahoo_bars_20261117_sync.json`，本轮未 429，22 个标的均 200，取数 **2026-11-17T16:17:45Z**）。**11/16 已结算日线现已可用，用来更正昨夜未定盘 last。** 11/17 为周二交易日：斯德哥尔摩本轮取数时距收盘约 13 分钟，SIVE.ST 未定盘 last **13.55**；美股取数时约 11:17 ET，同样是未完成日线。FI 总表 https://www.fi.se/en/vara-register/fis-marknadsregister/blankning/net-short-positions/ 快照 `/workspace/fi_list_20261117.html`（Current positions **2026-11-17**，List updated: **2026-11-17 16:29**）：Sivers 行 Latest position date **2026-11-16**、Sum **6.94**。发行人页 `/workspace/fi_em_20261117_issuer.html`（curl 200，已解析出具名表；Python urllib 同 URL 曾 404，以 curl 快照为准）。观察池：本地 `/workspace/trade/scan.md` 于 11/17 09:47 已写成「观察池日报 2026-11-16」；Gmail（历史上接收该日报的邮箱，`subject:观察池`）最新仍是数据日 **11/13** 已发（`1a1d7c24c2fce00b`，2026-11-14T01:53:17Z），**未见** 11/16 日报发信——按例程周二 09:45 本应发出，记为缺口，不写成已发。`trade` tip 仍 `679ffe9`，`scan.md` 本地脏、按 2026-10-15 约定不推仓库。Sivers Cision（`/workspace/sivers-cision-20261117.html`）：最新仍是 11/16 07:00 CET 提名委员会组成程序，**无更新稿**。官网 newsroom 本轮 **404**；**events-calendar 本轮 200**（`/workspace/sivers-events-20261117.html`），可独立核 2027 开年四场展会。X 公开接口 @lyAtomic / @aleabitoreddit / @SiversSemicond / @StormDirac / @dizaq1 / @carrioresearch（窗口 UTC **11/16 16:00–11/17 16:18**）。TileProto `gh` 仍停 2026-10-30（`pushedAt` 2026-10-30T10:40:16Z）。各助手本地 memory 文件 **无** 11/17 实质新写入（磁盘 mtime 仍停在 11/08 备份点）。`longyunBegin/trade`、`thinking-sparring` 无新 commit。工作区已有 11/17 09:29 的 Serenity 抓取与 Jev 结果（`/workspace/serenity-x-20261117/`，来源例程未在本轮独立标注）；下午及盘中帖（含光模块进口限制传闻、AAPL–三星 DRAM 等）**本轮未再跑 Jev**，一律按转述记账、不升格为已核事实。
- 对话正文：本运行**仍无法读取**其他助手在日历日 **2026-11-17** 的对话正文。

## 缺口（重要）
- 本运行**仍无法读取**其他助手在 **2026-11-17** 的对话正文。
- **请主对话逐个读取下面 18 个助手在日历日 2026-11-17 的对话并补录、另行提交：**
  1. 云服务机器人 `06fccad7-cbb6-42ff-a9db-f26d80cef5ab`
  2. X内容产出 `074ce1f1-d833-4e46-8872-c1667431375e`
  3. AI `13a65f19-9486-4581-829f-ca00be3f25c2`
  4. 记忆系统 `2adb4fd0-6eee-48fc-bf72-64dc3ecb8b30`
  5. SIVE `4ba186e6-8409-40d7-8f5f-d1a75e52beb9`
  6. X `55a49dcf-1e7b-4f26-9ba5-2035a1741690`
  7. 内存 `5ace2d2c-fee1-4567-9f83-823d6dc0431f`
  8. Research `65501f27-1c36-46fe-baeb-1eebe2ca489c`
  9. Trade Strategy `8a253cfb-b7b1-4473-b08b-6ac709c650b6`
  10. 认知学习 `8b1144cd-aa15-4efe-9ed3-d9f25d4835b3`
  11. 工具 `a68ddb65-ade1-4309-ad4c-0febbbd73e0c`
  12. Trade `a8ee710b-bc09-4245-8946-75cf0d5647e6`
  13. 新想法 `bd5520eb-8931-488a-8d85-231d2f6d4da5`
  14. 美股 `c5e37a16-bf66-475b-80ce-5a17fa1cb527`
  15. 思考陪练 `d8625c16-ca60-48dc-b9ae-be87ba89f666`
  16. 光互连 `e4a94e78-5384-42b4-acbb-1417fc731a9d`
  17. Reddit `e6f8bfc2-c472-4e0e-a6ad-46f594b19f61`
  18. 加密货币 `fa28746e-1eec-43be-9124-473d7341675e`
- 观察池：**数据日 11/02** 仍未见发信（10/30→11/03 跳空）——不臆造。数据日 **11/16** 的日报本地 `scan.md` 已生成，但本轮在既有收信邮箱里**未见对应发信**（按例程周二 09:45 本应发出）。不要把本地稿当成已送达。
- 11/17 SIVE 官方收盘与美股官方收盘本轮都还没有；未定盘 last 不得写成定盘。次日应用官方结算更正。
- 社区关于「特朗普政府将推进限制进口中国 AI 数据中心新款光模块」、AAPL–三星 DRAM 长单、IQE 上调指引、Leopold 13F、摩根士丹利 NVDA 预览、Bernstein 合约、Lightmatter/AOI 激光倍数等，**本轮未打开政府文件、公司公告或卖方原件**；若干长帖接口只返回约 300 字截断，未引用的后半段不得补写。只记转述。
- dizaq1 所称 SIVE–CIEN「近期关联」只见到他引用的 Ciena 11/13 YouTube 标题（Vesta 200 6.4T CPX / NPO），帖文后半截断，**不是** Sivers 或 Ciena 的 IR 声明。
- 本轮未对下午盘中帖再跑 Jev。
- 仍待办（不改写旧行）：FY2025 306.6m vs 302.8m 口径差待 11/26 对齐；NINGI 完整 PDF 未读到；CHIPS 55.2m 未从年报附注独立核到。

## 各助手覆盖

| 来源 | 本轮 | 主题文件 |
|------|------|----------|
| 动态名册 | **18**，无新助手；Muse 不在册、已自提交 11/16 日记与 11/17 看板 | episode |
| SIVE / 美股价格 | **更正 11/16 官方定盘**：SIVE.ST **13.97**（量 **6,891,347**）；11/17 未定盘 last **13.55** | sive、holdings |
| 观察池 | 本地已出数据日 **11/16** 日报（MU 下穿 MA200 等 3 条）；邮箱未见发信，最新仍是 `1a1d7c24c2fce00b` | trade-ideas |
| FI 空头 | 总表 Sum **升至 6.94**，持仓日仍 **11/16**，List updated **11/17 16:29**；具名未变，升幅在未具名桶（约 **4.31%**） | sive、holdings |
| Sivers IR | 无新稿（最新仍是 11/16 07:00 CET 提名委员会程序）；官号本窗 0 帖；**官网展会日历 200，已独立核验四场摊位** | sive、optical、x-content |
| Muse（已入库，不重抄） | `ecc5a95` 11/16 日记（估值表、Anthropic 条款、IBKR 2DG 保证金、美光财年、Outlook 密码已自行改掉）；`ab6ef48` 11/17 06:00 六看板（含 MRVL×Penguin 合作与董事会补记） | artifacts、sive、micron、anthropic、us-macro、crypto |
| Serenity | 光模块进口限制传闻、AAPL–三星 DRAM 长单转述、DeepSeek 算力限制、Lightmatter 激光倍数、Leopold 13F 等（均未打开原件） | serenity、optical、micron、us-macro |
| StormDirac | 本窗 0 帖 | episode |
| dizaq1 | 社区读法：Glasgow「并非物业施工扩产」、以及对 Ciena Vesta 200 视频的 SIVE 关联（后半截断，≠IR） | sive、optical |
| carrioresearch | 转述 IQE 上调指引、MS NVDA 预览、光模块限制的近端限制条件、Bernstein 合约等（均须对原件） | optical、us-macro、axti、sive |
| @lyAtomic | 本窗 0 帖（昨夜展会日历帖已由官网核验） | x-content、sive |
| 工具 | TileProto 无新 commit（仍 2026-10-30） | episode only |
| 本地 memory / 对话正文 | 无 11/17 新写入；对话正文仍读不到 | 缺口 |

## 结论（摘要；细节见各主题「2026-11-17 日常同步」段）
1. **更正 11/16 官方定盘；11/17 收盘尚未出来。** Yahoo v8 已结算日线最后一根完整交易日是 **2026-11-16**。SIVE.ST **13.97（−2.31% vs 11/13 14.30）** O/H/L **13.92 / 14.42 / 13.70** 量 **6,891,347**——价格与昨夜未定盘 last 及 Muse/观察池一致，**量由昨夜 5,757,035 补全为 6,891,347**。SIVEF **1.335（−6.64%）** O/H/L **1.37 / 1.41 / 1.30** 量 **1,891,743**（更正昨夜未定盘 last **1.38** / 量 388,468）。2DG.F **1.316（约 −0.3% vs 11/13 的 1.32）** O/H/L **1.32 / 1.341 / 1.166** 量 **8,803**（更正昨夜未定盘 last **1.294** / 量 7,503）。美股 11/16 官方收盘：MU **719.02（−7.62%）** 量 26,712,100；SNDK **809.11（−8.58%）** 量 12,292,700；NVDA **156.14（−4.12%）** 量 331,405,000；MSFT **517.99（−1.12%）** 量 30,198,800；MRVL **145.36（−7.27%）** 量 21,368,300；IBKR **78.43（−4.11%）** 量 3,569,800；AAOI **45.16（−9.48%）** 量 10,134,400；DRAM **39.27（−7.38%）** 量 37,057,000；GOOGL **283.72（−4.07%）** 量 34,643,200；LITE **546.00（−8.48%）** 量 4,588,100；COHR **203.43（−6.75%）** 量 7,307,100；SOXX **141.22（−5.41%）** 量 37,024,300；AXTI **38.46（−8.08%）** 量 13,379,200。旁记 AGLT **7.18（−2.45%）**、ASTS **28.58（−12.33%）**、NBIS **107.13（−7.55%）**、POET **4.66（−9.16%）**。观察池 `scan.md` 同日收盘有小差（MU 719.07、SNDK 808.93、NVDA 156.16、MSFT 518.07、MRVL 145.43、IBKR 78.42、DRAM 39.29、GOOGL 283.80），**不调和**，官方以 Yahoo 已结算日线为准；Muse 看板 SIVE 13.97 / AAOI 45.16 / AXTI 38.46 / MRVL 145.36 与 Yahoo 一致。11/17 未定盘 last（不得写成定盘；16:17:45Z）：SIVE.ST **13.55** O/H/L **13.22 / 14.68 / 13.14** 量 **7,250,203**；SIVEF **1.30** O/H/L **1.40 / 1.40 / 1.30** 量 65,560；2DG.F **1.20** O/H/L **1.191 / 1.358 / 1.178** 量 7,062。美股约 11:17 ET 未定盘 last：MU **690.23**、SNDK **769.02**、NVDA **154.99**、MSFT **499.81**、MRVL **145.02**、IBKR **76.73**、AAOI **44.46**、DRAM **38.16**、GOOGL **280.44**、LITE **552.61**、COHR **207.35**、SOXX **139.63**、AXTI **36.33**、AGLT **6.98**、ASTS **27.67**、NBIS **106.31**、POET **4.54**。 〔引用：本 episode；快照 `/workspace/yahoo_bars_20261117_sync.json`；交叉 `memory/episodes/2026-11-17-midnight-sync.md`、Muse `memory/agents/muse/artifact-*-2026-11-17.md`〕

2. **FI Sum 升至 6.94；具名未变，升幅在未具名桶。** 总表 Current positions **2026-11-17**，List updated **2026-11-17 16:29**，Sivers 行 Latest position date **2026-11-16**、Sum **6.94**（昨夜 6.86，↑0.08pp）。发行人页 live **Sum percent 6.94**。aktuella ≥0.5% 仍是：GSA Capital Partners LLP **0.91**（持仓日 **2026-11-13**，前值 0.81）；Arrowstreet Capital Limited Partnership **0.61**（**2026-11-09**，前值栏 0.59）；Marble Bar Asset Management LLP **0.52**（**2026-11-04**，前值 <0.5）；AQR Capital Management LLC **0.59**（**2026-10-06**，前值 0.63）。具名合计 **2.63**，与昨夜相同；未具名桶约 **4.31%**（昨夜约 4.23%）。Muse SIVE 看板仍把「GSA 0.81%」标为未核实二手——**不改对方看板**；本轮发行人页具名仍是 **0.91@11/13**，与昨夜官方表一致。 〔引用：本 episode；`/workspace/fi_list_20261117.html`、`/workspace/fi_em_20261117_issuer.html`〕

3. **无新 IR；官网 2027 开年展会日历已独立核验。** Cision 最新仍是 11/16 07:00 CET「Formation of the Nomination Committee… ahead of the 2027 Annual General Meeting」，受益人联系截止仍是 **11/25**，委员名单仍未公布。@SiversSemicond 本窗 0 帖。官网 events-calendar 本轮 **HTTP 200**（昨夜 403），可见 Upcoming：Photonics West **2027-02-01–04**、Booth **5123**（UK Pavilion）；MWC **2027-03-01–04**、Booth **5E1**（Hall 5）；SAT Show **2027-03-09–11**、Booth **4142**；OFC **2027-03-09–11**、Booth **S-2641**。这与昨夜 @lyAtomic / Carrio 对官方页的转述一致，本轮**升级为已打开官网核验**，不改写昨夜「转述」旧行。Past Events 页上还列 CIOE 2026-09-09–11 Booth **4C205**、ECOC 2026-09-21–23 Booth **2106** 等，只作日历备查。新闻室本轮 404，不能当「无新闻」的独立证据。 〔引用：本 episode；`/workspace/sivers-events-20261117.html`、`/workspace/sivers-cision-20261117.html`〕

4. **观察池：数据日 11/16 本地已出，邮箱未见发信。** `scan.md` 标题「观察池日报 2026-11-16」，今日变化 3 条：MU 下穿 MA200、MSFT 下穿 MA50、IBKR 下穿 MA20。表内 SIVE.ST 收 13.97/−2.31%、空头排列、跌破近低、缩量 0.90x（与 Yahoo 价格一致）。Gmail `subject:观察池` 最新仍是 11/13 日报 `1a1d7c24c2fce00b`（2026-11-14T01:53:17Z）；按例程周二至周六 09:45 发前一交易日，11/17 09:45 本应发 11/16 稿，本轮记为**未见发信**，不把本地文件写成已送达。`trade` 仓库 tip 仍 `679ffe9`。11/02 跳空仍在。 〔引用：本 episode；本地 `/workspace/trade/scan.md`（非库内路径，仅扫描说明）〕

5. **Muse 已入库（只交叉，不重抄）。** `ecc5a95`（2026-11-16 16:39:48Z，上海 11/17 00:39）写入 `memory/agents/muse/2026-11-16.md`，并新建 `memory/themes/anthropic-ipo.md`、`memory/themes/micron.md`，追加 IBKR 法兰克福 **2DG** 保证金时间表（**11/17** 起初始 100%、维持 50%；11/19 维持 75%；11/23 维持 100% / 零抵押价值；原因写市场波动 + FINRA Ready Market test 不达标——助理未代操作）、Anthropic 现行发行条款（定价 **11/18**、上市 **11/19** 代码 ANT）与美光 FY26 实际数字。用户确认 Outlook 临时密码已自行改掉——**不入库任何密码、账号或登录邮箱**。`ab6ef48`（11/17 06:00）六看板刷新至 SIVE v6 / AAOI v3 / AXTI v3 / MRVL v3 / BTC v3 / ETH v4：价格用 11/16 收盘或 11/16 21:58 UTC 加密快照；MRVL 新增 11/16 与 Penguin Solutions 的 AI 内存战略合作（CXL 2026 年底前供认证、光子内存池化 2027 下半年抽样，**明确无收入贡献**）以及 11/12 三名独立董事补记（昨日刷新漏记）。细节以 Muse 日记与 `memory/agents/muse/artifact-*-2026-11-17.md` 为准，此处不重抄。 〔引用：`memory/agents/muse/2026-11-16.md`；`memory/agents/muse/artifact-*-2026-11-17.md`；提交 `ecc5a95`、`ab6ef48`〕

6. **社区 X（≠IR；下午帖未跑 Jev，按转述记账；若干长帖接口截断约 300 字）：**
   - @aleabitoreddit **2122660925488718046**（2026-11-17T11:59:36Z）：称「刚刚」特朗普政府将推进限制进口中国 AI 数据中心设备，例如新款光模块，尽管超大规模云（点名 AMZN / GOOGL）反对，并称利好西方光学——**未打开政府或媒体原件**，不得写成已经生效的禁令。同日 **2122628849657954454** 转述苹果放弃与 $CMXT / 中国的廉价存储供货、接洽三星 DRAM 长单，合约预期 **2027H1** 起、期限 **4–5 年**——未打开原件。**2122485440469241998** 转述 DeepSeek 因算力不足限制用户（称财联社）；**2122443473710432351** 转述 Lightmatter CEO：scale-up CPO 若 8 个光引擎/GPU，激光用量可达 scale-out 交换的 **100 倍**，更保守的是 AOI CFO 的 **10 倍**，且 ASP 更高——均是转述、后半截断。**2122455173356536151** 转述 Leopold / Situational Awareness 13F：BE 3.892 亿美元看涨、NBIS 3.326 亿、SNDK 1.827 亿，另 SHAZ 股票 4.407 亿、DRAM ETF 看涨 1.403 亿等——**未打开 13F**，且 13F 通常是季末快照，不得当成 11 月持仓。**2122428876748206564** 认为 ANT 今后数年 **7000–8000 亿美元** ARR 预测偏炒、2028 年后 capex 预测可能下修——个人判断，对照 Muse 已入库的招股口径，不把该预测写成文件数字。
   - @carrioresearch 把同一则光模块限制写成盘前 AAOI/LITE/COHR 大涨（**2122684159605043406**），并补近端限制（**2122702817051980113**）：中国约占全球供应 2/3；AAOI 月产 100 万+ 要到 **2027 年底**才就绪且美国扩产延期；限制只打新款；AXTI 的 InP 衬底仍在中国、出口许可不确定——同为转述。**2122593782374035941** / **2122605550466924871** 转述 IQE **11/17** 再上调全年指引：营收增速由 7 月的 >30% 提到 **>40%**，并上调调整后 EBITDA（后半截断）；他把 IQE 放在 AXTI 衬底与光芯片之间的外延层。**2122635063678697536** 转述摩根士丹利对 NVDA 11/17 电话会的三个观察点，可见的第一点是 Kress 如何承接战略（客户融资支持、生态投资等），后半截断，**未打开原注**。**2122699397607866432** 转述 Bernstein 11/16：六家 AI 基建矿企 24 个月签下 **1,320 亿美元** / **5.5GW** 合约（CIFR/WULF/CORZ/RIOT/IREN/CLSK），约 85% 是托管——未打开原报告。**2122665993197776927** 是对 Serenity 高功率激光 / InP 论点的转述，不构成新核验。
   - @dizaq1 **2122430361061978241** 读 SIVE 论坛对即将发布财报的预期：他「并不很担心」格拉斯哥扩产延期，理由是「并不是在做物业施工那样的物理扩建」（后半截断）；跟帖 **2122453622479069254** 称「就我所知目前没有任何延期，只是有人担心」。这是个人读法，**不是**公司声明。**2122502295447597083** 称发现 SIVE 与 CIEN 的「近期关联」，并指出 Ciena 在 **11/13** 发布 YouTube 视频《Ciena's Vesta 200 6.4T CPX Optical Engine delivers best-in-class NPO performance》——视频标题可记，**关联本身后半截断，不是 IR**。
   - @lyAtomic、@SiversSemicond、@StormDirac 本窗 **0** 帖。

7. 在册 **18**。日历：SIVE Q3 **11/26**；NVDA 11/17 盘后（北京时间 **11/18 05:20** 发布、**06:00** 电话会，本轮结束时尚未发布；共识/答案 key 见 Muse 11/16 日记：EPS **$2.40**、营收 **$108.73B**，公司指引营收 **$108.0B ±2%**）；提名委员会受益人联系截止 **11/25**；Anthropic 定价 **11/18**、上市 **11/19**；美光 Q1 FY27 约 **12/15**；SC26 **11/15–20** 进行中；IBKR 2DG 保证金阶梯 11/17–11/23。

## 写入 / 变更文件
- 新建：本 episode
- 追加：`themes/sive-investment.md`、`themes/trading-holdings.md`、`themes/trade-ideas-indicators.md`、`themes/serenity-aleabitoreddit.md`、`themes/optical-interconnect-learning.md`、`themes/us-macro-options.md`、`themes/crypto.md`、`themes/x-content-output.md`、`themes/micron.md`、`themes/axti-axt.md`
- 不改：主 `INDEX.md`（Anthropic / Micron 主题与看板登记已由 Muse 在 `ecc5a95` / `ab6ef48` 写入）；不改 Muse `agents/`、artifacts、昨夜 midnight/catchup
- 工作区（非必须 commit）：`yahoo_bars_20261117_sync.json`、`fi_list_20261117.html`、`fi_em_20261117_issuer.html`、`sivers-cision-20261117.html`、`sivers-events-20261117.html`

## 未入库（有意跳过）
- 把 11/17 last 13.55 / 任何盘中美股报价写成官方收盘；用观察池小差覆盖 Yahoo 11/16 已核定盘。
- 把本地 `scan.md` 写成观察池已发信，或臆造 11/02 已发。
- 把光模块进口限制传闻写成已生效的法规或已打开的政府文件。
- 把 SIVE–CIEN「关联」、Glasgow「没有延期」、IQE / 13F / MS / Bernstein / AAPL–三星数字当成已打开的原件。
- 把 Muse 看板里仍标注的 GSA 0.81% 未核实句改写成官方数字，或改写对方 `agents/` 与 artifacts。
- 重抄 Muse 估值计算器、Anthropic 条款全文、美光四季数字，或改写 `ecc5a95` / `ab6ef48`。
- 入库用户登录邮箱、密码、券商账户号或其他隐私。
- Grok Build；用户已拒绝的 X Following digest。
