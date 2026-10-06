# 交易想法仓库 · TradingView 指标 · 观察池自动扫描（来源：「新想法」助手）

来源助手：**新想法**（agent id `bd5520eb-8931-488a-8d85-231d2f6d4da5`，2026-10-06 新建）。以下事实均取自该助手 2026-10-06 对话 transcript（约 18:00–23:26 Asia/Shanghai）。

## 仓库 `longyunBegin/trade`
- (2026-10-06，新想法) 新建**公开** GitHub 仓库 [longyunBegin/trade](https://github.com/longyunBegin/trade)，用于分享个人交易想法：技术指标、观点、复盘。公开是因为 Yun Long 说用来分享。 〔引用：新想法 t14s1〕
- 结构：`README.md`（说明 + 免责声明）、`indicators/`（**每个指标一个文件夹：`panel.pine` 代码 + `README.md` 详细讲解**，讲解里每项都标对应代码变量）、`ideas/`（交易观点，暂空）。Yun Long 明确要求「一段指标代码要关联上对这段指标的详细讲解」。 〔引用：新想法 t17u / commit `4e4d5d8`〕
- 提交身份：`longyunBegin` / `longyunBegin@users.noreply.github.com`（该仓库内使用）。

## 指标 1：第一性原理面板（`indicators/first-principles-panel/`）
- (2026-10-06) 思路：不用 RSI/MACD/KDJ 等二次加工指标，只看**价格、成交量、相对板块表现**；看清当前状态，不预测涨跌。 〔引用：README / commit `4e4d5d8`〕
- 内容：MA20/50/200（SMA）位置与排列（价在三线上方/下方/夹在均线间；多头/空头排列/均线纠缠）；结构（收盘 vs 前 20 根高低：突破近高/跌破近低/区间内）；量能（量 ÷ 20 日均量）；ATR14；相对强弱（个股/基准 vs 其 20 日均，默认基准 `NASDAQ:SOXX`）；近 20 根高低（阶梯线）。表在右下角。
- Yun Long 自行把基准输入显示名改为 `NASDAQ:SOXX`，已按其要求提交（commit `dc50ee6`）。
- 非美元股票兼容：均线/结构/量能不受币种影响；ATR 单位为当地货币；**相对强弱应换本地基准**（如 SIVE 用瑞典指数），否则混入汇率与时差。 〔引用：新想法 t19s0〕
- 排错经验：法兰克福副本 `2DG`（Sivers）成交稀疏，量能读数无参考价值，应看斯德哥尔摩主上市 `SIVE`。TradingView 指标若出现 A/B 两根价格轴、线与 K 线错位，是指标挂在独立刻度上，需「…」→「固定至坐标」→ 选 A（`scale=scale.right` 无效，已撤回该建议）。 〔引用：新想法 t20s0–t23s0〕
- 示例读数（MRVL，约 10/5）：收 ~271；MA20 248.56 / MA50 228.27 / MA200 167.85；近高 280.00 / 近低 213.63；价在三线上方 · 多头排列 · 区间内。 〔引用：新想法 t18s0〕

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
- (2026-10-06) Yun Long 要求观察池接入自动化、**不每次调用 AI**：GitHub Actions 定时跑 `scanner/scan.py`（Python + yfinance，固定公式，与两个 Pine 面板同口径），按 `watchlist.txt` 扫描，结果写 `scan.md` 并发邮件。 〔引用：新想法 t28u–t31u / commit `dba97d3`、`fef84ae`〕
- 数据源：TradingView 无公开数据接口，不作自动化源；选 **Yahoo Finance**（免费日线，偶有延迟）。备选：IBKR（需常开 IB Gateway）、Polygon / EODHD 付费 API。先用 Yahoo，与 TradingView 对数后再决定。 〔引用：新想法 t29s0〕
- 观察池初始：MU、SNDK、SIVE.ST（基准 ^OMX）、NVDA、MSFT、MRVL、IBKR、AAOI、DRAM（上市约半年，无 MA200）。默认基准 SOXX。
- 邮件：Gmail `ly1653812264@gmail.com` 自己发给自己；GitHub Secrets 设 `GMAIL_USER`、`MAIL_TO`、`GMAIL_APP_PASSWORD`（应用专用密码，用户经安全输入框提供）。邮箱不写入代码。2026-10-06 23:22 手动跑通，首封「观察池日报 2026-10-05」已发送。
- gh token 已加 `workflow` scope（Yun Long 设备授权）。
- **进行中（截至 2026-10-06 23:26）**：
  - 邮件改为**苹果高级设计风格 + uselayout 风格**（浅灰底白卡片、每股一卡、手机不横滑）。
  - **交易日判断**：用户在亚洲有时差，只有上一个美股交易日确实开市且有新数据才发；同日数据不重复发（workflow_dispatch `force` 可强发）。
  - **发送时间改为北京时间周二至周六 09:45**（cron `45 1 * * 2-6` UTC），取代原 06:15。
- 10/5 收盘示例（scan.md）：MRVL 离 MA50 +18.8%（+3.3ATR 偏离大）、量价 2.62 买盘主导；SIVE.ST 一年位置 30%、波动 4% 收缩；NVDA 一年位置 98%；AAOI 风险收益比 1:0.0（收盘略低于前 20 根高）。

## 其他想法清单（新想法 t27s0，待选）
观察池扫描（已做）、板块轮动（存储/光模块/GPU/代工相对 SOXX）、财报前后规律统计、交易复盘模板（放 `ideas/`）、仓位计算器（接止损价）、把指标读法做成 X 内容系列（对接半导体深度分享定位）。
