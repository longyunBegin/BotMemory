# SIVE 研究看板

- slug：`sive-yan-jiu-kan-ban`
- 名称：SIVE 研究看板
- kind：web_static
- 创建日：2026-11-15
- 最后更新：2026-11-27
- 当前版本：v15
- 最后编辑者：Muse

## 当前状态

收入模型三档总表与柱状图（集团 2026E 熊/基/牛 204/226/248、2027E 220/355/550、2028E 310/590/985，单位 SEK m；基线分部光子 69/145/330、无线 157/210/260）+ 分部拆解可切换情景（LiDAR、Jabil、CPO/ELS、NRE、ALL.SPACE、Tachyon 逐年计入）+ 盈亏平衡、现金跑道、格拉斯哥产能检验、Q2 2026 已验证基数；客户线六张状态卡（LiDAR、Jabil、Ayar、ALL.SPACE、Tachyon、SemiNex/GF/POET），区分「带金额订单」与「合作公告」；验证记录区（NINGI 做空报告核查、ImportYeti 海运复核及口径局限、瑞典官方无公司级贸易数据、年报 Note 6 分地区收入与 Ayar 42.2m 条件推算、CHIPS 拨款交叉核对、内部人买入、四条模型纠错日志、未核实清单）；末尾验证点清单（最近裁决点 2026-11-30 Q3 报告）与敏感假设/证伪条件。数据截止 2026-11-26（最新价 12.10 SEK，较前收涨 9.80%，当日无公司公告；Q3 报告 11 月 30 日 18:00 CET 发布；FI 登记做空总量 7.29%，GSA 1.35%、Arrowstreet 0.82%、Millennium International 0.73% 均于 11-25 上调；Section 301 后续：11-26 中国商务部表态坚决反对、保留采取必要措施的权利，书面意见截至 2027-01-05、听证会自 2027-01-25 起）；公司 11 月 16 日公告成立 2027 年股东大会提名委员会（例行治理事项）；验证记录补入 WT Microelectronics 全球分销协议（2026-11-11 公告）；未核实项在页面上单独标注。光子线 2026-11-23 起按 0–8 层供应链重画（Sivers 第 4 层 ELS 争议卡点，第 7 层 InP 衬底为真卡点、涨价利空，验证走 3→4→5：认证、格拉斯哥爬坡、毛利率自 Q2 -36.6% 回升）；真机视觉验收待用户在 Mac 上确认。v2 起分部拆解的光子/无线驱动表改为静态预渲染（首屏不依赖脚本填充）；v3 起图表颜色改走 CSS 类（修复 iPhone WebKit 不解析 SVG presentation attribute 里 var() 的问题）；v4 起底色与文字、图表颜色全部加字面色兜底（修复 Mac 端 WebView 文档未绘制导致的面板空白）。

## 变更记录

- 2026-11-15，Muse，v1 新建：用户要求建 SIVE 研究看板（研究看板选项）；内容如上。构建审计通过（无控制台错误、无破损资源、手机端零横向溢出，情景切换按钮经点击探针验证生效）。
- 2026-11-15，Muse，v1 → v2 修复重发：用户反馈看板打不开；排查为已发布构建快照/客户端打开层故障（源码与已部署文件无损坏），重新构建发布替换旧快照；分部拆解驱动表改为静态预渲染，内容不变。
- 2026-11-15，Muse，v2 → v3 深层修复：v2 后用户端仍打不开，定位到 iPhone WebKit 差异——图表 22 处 SVG 颜色用 fill/stroke="var(--…)" 写法，WebKit 不解析 presentation attribute 里的 var()；另修一处旧 WebKit 会整条丢弃的 :not() 选择器列表；脚本加空值守卫与 try/catch。内容、数据、布局未改动。
- 2026-11-15，Muse，v3 → v4 Mac 面板空白修复：用户反馈 Mac 端打开看板面板一片空白；诊断为 Mac WebView 里文档根本没有绘制（截图右侧是宿主 App 空状态径向渐变底色、非页面深色背景），属加载失败而非渲染错误；底色与文字、图表颜色全部加字面色兜底（字面色在前、var() 在后），正常引擎视觉零变化；同时重新构建发布全新快照替换旧缓存。内容、数据、脚本逻辑未动。若 Mac 上仍纯黑，剩余嫌疑在客户端侧（Clash Verge 规则代理可能拦截/误路由看板网关域名，或 App 缓存了旧构建的失败加载），待用户关代理/换网络或重启 App 后复测。
- 2026-11-16，Muse，v4 → v5 每日刷新：最新价 14.30 SEK（11-13 收盘，−10.29%），数据截至改为 2026-11-13；新增 11-13 板块普跌说明（费城半导体指数跌约 6%，Q3 日期 2026-11-26 未变）。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-16.md。
- 2026-11-17，Muse，v5 → v6 每日刷新：最新价 13.97 SEK（11-16 收盘，−2.31%）；新增提名委员会公告（11-16，例行治理事项）与 11-16 板块普跌说明；同版修正页脚数据截至日与页首统一为 2026-11-16。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-17.md。
- 2026-11-18，Muse，v6 → v7 每日刷新：最新价 13.51 SEK（11-17 收盘，−3.29%）；新增英伟达盘后 Q3 财报超预期与 Q4 指引上调（板块情绪）；验证记录补入 WT Microelectronics 全球分销协议（2026-11-11 公告，建板时漏记）。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-18.md。
- 2026-11-19，Muse，v7 → v8 每日刷新：最新价 13.36 SEK（11-18 收盘，−1.11%）；新增英伟达财报后股价收跌 2.89%、美联储 10 月纪要偏鹰、Anthropic IPO 定价 $83/股（11-19 以 ANT 上市）。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-19.md。
- 2026-11-20，Muse，v8 → v9 每日刷新：最新价 13.69 SEK（11-19 收盘，+2.47%）；新增英伟达再跌 3.30% 至 $145.98（六连跌）与 Anthropic 上市首日收 $97.17。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-20.md。
- 2026-11-21，Muse，v9 → v10 每日刷新：最新价 11.41 SEK（11-20 收盘，−16.65%）；Q3 报告改期至 11 月 30 日；新增市场暴跌背景、Millennium 做空披露（待核实）与 Seeking Alpha Sell 评级（第三方观点）。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-21.md。
- 2026-11-23，Muse，v10 → v11 结构改版：光子线按 Serenity 卡点框架重画为 0–8 层供应链（Sivers 第 4 层 ELS 争议卡点，第 7 层 InP 衬底为真卡点、涨价利空，验证走 3→4→5）；原「光子 = 增长」表述替换。用户点头安装，构建方报告成功；价格与收入模型数字未动；真机视觉验收待用户确认。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-23.md。
- 2026-11-24，Muse，v11 → v12 每日刷新：最新价 13.53 SEK（11-23 收盘，+18.58%）；新增英伟达恢复黄仁勋 CEO 职务带动板块普涨一条。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-24.md。
- 2026-11-25，Muse，v12 → v13 每日刷新：最新价 11.78 SEK（11-24 收盘，-12.93%）；新增周二反弹回吐背景一条；FI 做空登记更新为总量 7.38%（主编辑先写缓存旧值 7.18%，直读 FI 官网后二次修正）；LiDAR 生产订单传闻与 Sell 评级未核实、不入库。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-25.md。
- 2026-11-26，Muse，v13 → v14 每日刷新：最新价 11.02 SEK（11-25 收盘，-6.45%）；新增 Section 301 关税提案背景一条；FI 做空登记更新为总量 7.13%（新增 Millennium Capital (DIFC) 0.53%）；ad-hoc 二手文章无新增事实、不入库。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-26.md。
- 2026-11-27，Muse，v14 → v15 每日刷新：最新价 12.10 SEK（11-26 收盘，+9.80%）；FI 做空登记更新为总量 7.29%（GSA 1.35%、Arrowstreet 0.82%、Millennium International 0.73% 均上调）；新增 Section 301 后续（中方 11-26 表态）。详见 memory/agents/muse/artifact-sive-yan-jiu-kan-ban-2026-11-27.md。
