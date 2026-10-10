# 交易想法仓库 · TradingView 指标 · 观察池自动扫描（来源：「新想法」助手）

来源助手：**新想法**（agent id `bd5520eb-8931-488a-8d85-231d2f6d4da5`，2026-10-06 新建）。以下事实均取自该助手 2026-10-06 对话 transcript（约 18:00–23:26 Asia/Shanghai）。

## 仓库 `longyunBegin/trade`
- (2026-10-06，新想法) 新建**公开** GitHub 仓库 [longyunBegin/trade](https://github.com/longyunBegin/trade)，用于分享个人交易想法：技术指标、观点、复盘。公开是因为 Yun Long 说用来分享。 〔引用：新想法 2026-10-06 对话〕
- 结构：`README.md`（说明 + 免责声明）、`indicators/`（**每个指标一个文件夹：`panel.pine` 代码 + `README.md` 详细讲解**，讲解里每项都标对应代码变量）、`ideas/`（交易观点，暂空）。Yun Long 明确要求「一段指标代码要关联上对这段指标的详细讲解」。 〔引用：新想法 2026-10-06 对话 / commit `4e4d5d8`〕
- 提交身份：`longyunBegin` / `longyunBegin@users.noreply.github.com`（该仓库内使用）。

## 指标 1：第一性原理面板（`indicators/first-principles-panel/`）
- (2026-10-06) 思路：不用 RSI/MACD/KDJ 等二次加工指标，只看**价格、成交量、相对板块表现**；看清当前状态，不预测涨跌。 〔引用：README / commit `4e4d5d8`〕
- 内容：MA20/50/200（SMA）位置与排列（价在三线上方/下方/夹在均线间；多头/空头排列/均线纠缠）；结构（收盘 vs 前 20 根高低：突破近高/跌破近低/区间内）；量能（量 ÷ 20 日均量）；ATR14；相对强弱（个股/基准 vs 其 20 日均，默认基准 `NASDAQ:SOXX`）；近 20 根高低（阶梯线）。表在右下角。
- Yun Long 自行把基准输入显示名改为 `NASDAQ:SOXX`，已按其要求提交（commit `dc50ee6`）。
- 非美元股票兼容：均线/结构/量能不受币种影响；ATR 单位为当地货币；**相对强弱应换本地基准**（如 SIVE 用瑞典指数），否则混入汇率与时差。 〔引用：新想法 2026-10-06 对话〕
- 排错经验：法兰克福副本 `2DG`（Sivers）成交稀疏，量能读数无参考价值，应看斯德哥尔摩主上市 `SIVE`。TradingView 指标若出现 A/B 两根价格轴、线与 K 线错位，是指标挂在独立刻度上，需「…」→「固定至坐标」→ 选 A（`scale=scale.right` 无效，已撤回该建议）。 〔引用：新想法 2026-10-06 对话〕
- 示例读数（MRVL，约 10/5）：收 ~271；MA20 248.56 / MA50 228.27 / MA200 167.85；近高 280.00 / 近低 213.63；价在三线上方 · 多头排列 · 区间内。 〔引用：新想法 2026-10-06 对话〕

## 指标 2：位置与风险面板（`indicators/position-risk-panel/`）
- (2026-10-06) Yun Long 要求六项全部做成新指标（commit `828da77`）：
  1. 离 MA20/MA50 的 % 与 ATR 倍数（≤1 ATR 贴近；≥3 ATR 偏离大）
  2. 一年位置（252 根日线高低之间百分位；≥80% 高位，≤20% 低位）
  3. 量价配合：20 日上涨日量合计 ÷ 下跌日量合计（≥1.2 买盘主导，≤0.8 卖盘主导）
  4. 波动：ATR 在近 120 根中的分位（≤20% 收缩，≥80% 扩张）
  5. 止损 = max(近 20 根低, 现价 − 2×ATR)；目标 = 近 20 根高（已突破则按 2R）；风险收益比 ≥2 划算、1–2 一般、<1 不划算
  6. 未回补跳空缺口（方块标注，默认保留 10 个）
- 表在左下角，可与面板 1 同图使用。助手提示：未在 TradingView 实测编译，首次导入报错需截图回报。

## 观察池自动扫描 + 每日邮件（`scanner/`）
- (2026-10-06) Yun Long 要求观察池接入自动化、**不每次调用 AI**：GitHub Actions 定时跑 `scanner/scan.py`（Python + yfinance，固定公式，与两个 Pine 面板同口径），按 `watchlist.txt` 扫描，结果写 `scan.md` 并发邮件。 〔引用：新想法 2026-10-06 对话 / commit `dba97d3`、`fef84ae`〕
- 数据源：TradingView 无公开数据接口，不作自动化源；选 **Yahoo Finance**（免费日线，偶有延迟）。备选：IBKR（需常开 IB Gateway）、Polygon / EODHD 付费 API。先用 Yahoo，与 TradingView 对数后再决定。 〔引用：新想法 2026-10-06 对话〕
- 观察池初始：MU、SNDK、SIVE.ST（基准 ^OMX）、NVDA、MSFT、MRVL、IBKR、AAOI、DRAM（上市约半年，无 MA200）。默认基准 SOXX。
- 邮件：Gmail `ly1653812264@gmail.com` 自己发给自己；GitHub Secrets 设 `GMAIL_USER`、`MAIL_TO`、`GMAIL_APP_PASSWORD`（应用专用密码，用户经安全输入框提供）。邮箱不写入代码。2026-10-06 23:22 手动跑通，首封「观察池日报 2026-10-05」已发送。
- gh token 已加 `workflow` scope（Yun Long 设备授权）。
- **进行中（截至 2026-10-06 23:26）**：
  - 邮件改为**苹果高级设计风格 + uselayout 风格**（浅灰底白卡片、每股一卡、手机不横滑）。
  - **交易日判断**：用户在亚洲有时差，只有上一个美股交易日确实开市且有新数据才发；同日数据不重复发（workflow_dispatch `force` 可强发）。
  - **发送时间改为北京时间周二至周六 09:45**（cron `45 1 * * 2-6` UTC），取代原 06:15。
- 10/5 收盘示例（scan.md）：MRVL 离 MA50 +18.8%（+3.3ATR 偏离大）、量价 2.62 买盘主导；SIVE.ST 一年位置 30%、波动 4% 收缩；NVDA 一年位置 98%；AAOI 风险收益比 1:0.0（收盘略低于前 20 根高）。

## 其他想法清单（新想法 2026-10-06 对话，待选）
观察池扫描（已做）、板块轮动（存储/光模块/GPU/代工相对 SOXX）、财报前后规律统计、交易复盘模板（放 `ideas/`）、仓位计算器（接止损价）、把指标读法做成 X 内容系列（对接半导体深度分享定位）。

## 2026-10-06 晚 ~ 10-07 00:11 增量（trade 仓库提交）
- (2026-10-06 23:29，新想法/trade commit `7d329c9`) 已落地：邮件改 Apple 风格卡片；**休市 / 无新数据 / 重复发送时跳过**（用 `exchange_calendars` XNYS 判断；scan.md 已是同一数据日期即不发；手动 `force` / `--force` 可强发；跳过仍显示绿色成功）；定时 **北京时间周二至周六 09:45**（cron `45 1 * * 2-6` UTC），理由：美股收盘为北京时间 04:00（夏令时）/ 05:00（冬令时）。 〔引用：scanner/README.md；commit 7d329c9〕
- (23:51，`1493092`) 邮件 v2：useLayouts 风格（暖米白底、渐变头图、Bento 小格、等宽标签）+ 超大邮件自动精简卡片；(23:59，`170c887`) 邮件 **v3：苹果式极简 + 信息层级「今日变化 → 总览 → 明细」**，少量 useLayouts 点缀（预览图在 /workspace/trade-email-preview/）。
- (10/7 00:02，`14c1ecd`、`3585a22`) 移植位置与风险面板第 6 项 **未回补缺口**：邮件明细卡片 + `scan.md` 新列。
- (10/7 00:11，`44e137e`) `ideas/` 首篇：**SIVE 第一性原理基本面拆解**（收入→利润率→现金→能赚多久→有多确定→反推现价），详见 `sive-investment.md` 10/6 节。
- 未决：Pine 两个面板仍未在 TradingView 实测编译；Yahoo 数据与 TradingView 对数未做。

## 2026-10-07 增量（10/8 午夜同步）
- (10/7 00:27，`099d399`) 新增想法 `ideas/sive-serenity-comparison.md`：SIVE Serenity 建模 vs 第一性原理拆解对照，README 与 `sive-fundamentals.md` 互链（新增「延伸」节）。要点见 `sive-investment.md` 与 `serenity-aleabitoreddit.md` 10/7 节。
- (10/7 10:31，`70f724d`) 观察池日报 2026-10-06 写入 `scan.md`（MRVL 突破近高、IBKR 上穿 MA20/MA50、DRAM 下穿 MA20，详见 `trading-holdings.md`）。
- (10/7 10:32，`66c7b3a`) **观察池日报定时改由 Grok Bot 例程「观察池日报」触发**（北京时间周二至周六 09:45，本机跑 `scanner/scan.py`），**删掉 GitHub Actions cron `45 1 * * 2-6`**；仓库仍保留 `workflow_dispatch` 可在 Actions 页手动运行。README 与 `scanner/README.md` 同步改写。 〔引用：github.com/longyunBegin/trade 提交 `66c7b3a`〕

## 2026-10-08–10/09 增量（10/10 午夜 catchup）
- (2026-10-08，新想法/trade commit **`c289624`**) `scanner/scan.py`：Yahoo **最新日线收盘为空**时，用**当天 1h K 线**最后一根收盘补齐——修 **SIVE.ST 落后一天**（北欧收盘后 Yahoo 日线偶空）。改动 +29 行。 〔引用：github.com/longyunBegin/trade `c289624`〕
- (2026-10-08，`3061324` / `521adea`) 观察池日报 **2026-10-07** 写入（`521adea` 补 SIVE.ST 10/7 行，配合 1h 补齐逻辑）。 〔引用：trade 提交日志〕
- (2026-10-09 晨，`9486edd`) 观察池日报 **2026-10-08** 写入 `scan.md`（变化与收盘见 `trading-holdings.md` / `sive-investment.md`）。 〔引用：trade `9486edd`；`scan.md` 标题「观察池日报 2026-10-08」〕
- (2026-10-09，新想法/trade commit **`3e14e14`**) `watchlist.txt` 新增 **`GOOGL, QQQ`**——基准为 **QQQ**（非默认 SOXX）。当前观察池：MU、SNDK、SIVE.ST(^OMX)、NVDA、MSFT、MRVL、IBKR、AAOI、DRAM、**GOOGL(QQQ)**。 〔引用：trade `3e14e14`；`watchlist.txt`〕
- (2026-10-09，同步注) 截至 10/10 ~00:26，`scan.md` 仍为 10/8 日报；**无** 10/9 日报行（例程尚未写出或本轮未跑到含 GOOGL 的下一报）。

## 2026-10-08–10/09 对话补录（新想法）
- (2026-10-08，新想法) scanner **`c289624`**（Yahoo 日线 Close 空 → 当天 1h 补齐）与 10/7 日报重发：见上一节「2026-10-08–10/09 增量」，不复写。10/7 重发日报中 SIVE **34.28**。 〔引用：新想法对话；trade `c289624`〕
- (2026-10-09，新想法) 盒子 SMTP 不通 → **观察池日报例程改为触发 GitHub Actions `scan.yml`** 发信（不再依赖盒子本地 SMTP）；补发「观察池日报 2026-10-08」（Actions run **37876246552**）。与 10/7「例程本机跑 scan.py」路径并存演进——以当前例程配置为准。 〔引用：新想法对话 2026-10-09；对照 `66c7b3a`〕
- (2026-10-09，新想法) watchlist 加 **GOOGL, QQQ**（`3e14e14`）：见上一节，不复写。用户问 @mail.grokbot.com / claim eden：无法代申请（见 `accounts-tools.md`）。 〔引用：同上〕

## 2026-10-10（覆盖日历日 10/10；数据多为 10/9 收盘）
- (2026-10-10 09:47 Asia/Shanghai，trade commit **`ec6357d`**) 观察池日报 **2026-10-09** 写入 `scan.md`（含 **GOOGL**）。今日变化：**MU** 下穿 MA20；**SNDK** 下穿 MA50；**SIVE.ST** 下穿 **MA200**；**AAOI** 相对 SOXX 转强。 〔引用：github.com/longyunBegin/trade `ec6357d`；`scan.md` 标题「观察池日报 2026-10-09」〕
- (同上·收盘表) MU **1,029.00**（−0.66%）；SNDK **1,581.82**（−1.72%）；**SIVE.ST 30.04**（−3.35%）；NVDA **229.28**（−0.52%）；MSFT **535.07**（+2.38%）；MRVL **275.28**（+0.23%）；IBKR **87.87**（+1.62%）；AAOI **109.64**（+3.53%，放量 **1.59×**）；DRAM **57.19**（+0.46%）；**GOOGL 351.66**（+0.97%，偏弱 vs QQQ）。数据日期均为 2026-10-09。 〔引用：同上 `scan.md`〕
- (同上·位置与风险要点) SIVE.ST：价在三线下方、均线纠缠、一年位置 **25%**、ATR14 **2.82**、止损 **26.68**（−11.2%）、目标 **36.34**、RR **1:1.9**。AAOI：一年 **42%**、止损 93.62、目标 131.15、RR 1:1.3。MSFT 一年位置 **91%**、RR 1:0.1（不划算）。GOOGL：止损 335.51、目标 364.17、RR 1:0.8。DRAM 仍仅 132 根 K、MA200 不足。 〔引用：同上〕
- (2026-10-10 11:28，trade **`b44ebb4`**) 发信改 **`lyatomic@mail.grokbot.com`** + `--no-email` 扫描；详见 `accounts-tools.md`。Actions run **38020927666**（workflow_dispatch，`head_sha=b44ebb4`，2026-10-10T03:32:33Z≈北京 11:32，success）出现在本机 agent-tools 拉取结果中——与「只生成 scan、不发信」配置一致。 〔引用：trade `b44ebb4`；`/workspace/agent-tools/3fe9d9f6-…txt`〕

## 2026-10-10 对话补录（交叉午夜 `85c5282` / `b44ebb4`）
- (2026-10-10，新想法) 发信路径确认信 message id **44462**；例程「观察池日报」提示已更新（`--no-email` + lyatomic SendEmail）。仓库改动见午夜，不重抄。 〔引用：新想法对话 2026-10-10〕
- (同上·手动发) 用户「你现在发送一份」：本机 Yahoo **全员限流**失败；改用已有 **`scan.md`（观察池日报 2026-10-09）** 经 SendEmail，message id **45302**（junk `$file:` **45230** 作废）。`scanner/out/email.html` 当时仍是 **10/08** 苹果风模板，正文用了正确 **10/09** scan.md。收盘/下穿 MA200 等数字见午夜 `ec6357d` 节。 〔引用：同上〕
- (同上) `/workspace/se_html.html` = 发信临时副本，md5 等同 `scanner/out/email.html`（内容仍标 10/08），**非**仓库正式文件。 〔引用：同上〕
