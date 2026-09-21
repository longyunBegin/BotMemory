# 账号与工具

## X 工具路径（2026-09-18 起强制）
- (2026-09-18，Yun Long) **全 bot 停用 Grok Build**；X 改走浏览器 / X MCP（有额度时）/ 其他非 Grok Build 路径。 〔引用：用户指令 2026-09-18〕
- 详见 `memory/themes/x-via-grok-build.md`（文件名保留，内容已改为停用说明）。

- X：当前登录会话显示 @lyAtomic（显示名 Eden）；曾记录 @longyun5201314
- 邮箱：ly1653812264@gmail.com（X 晨报不用邮件，只在本聊天交付）
- Unusual Whales：浏览器已登录，目前免费档（数据约延迟 2 天）；Flow History 等需付费档
- TradingView：曾开 Premium 做 SIVE Volume Footprint；Basic 档仅 2 指标，约定先读读数再轮换指标
- X MCP 常无额度（$0），SIVE/X 摘要优先用已登录浏览器抓取，不用 X API
- 记忆落库：GitHub 私有库 `longyunBegin/BotMemory`

## 已启用的例程（摘要）
- SIVE：工作日 09:00 Asia/Shanghai 日研摘要
- X：工作日 09:00 关注人投资研究早报（仅聊天交付）
- 光互连：ECOC 2026 日报，9/20–24 每晚 20:00 Asia/Shanghai（有限期限）

## X 访问路径（强制，2026-09-14）
- **以后凡涉及 X（Twitter）链接与查询**：在记忆系统电脑安装 **Grok Build**（`grok` CLI），用 Yun Long 的账号登录；**（已废止 2026-09-18）曾要求一律走 Grok Build CLI；现改走浏览器/X MCP。**
- 安装：`curl -fsSL https://x.ai/cli/install.sh | bash`（本机已装 `grok 1.0.30`，路径 `/home/box/.grok/bin/grok`）
- 登录：`grok login`（默认 OAuth）或无浏览器环境用 `grok login --device-auth`
- 凭据存于 `~/.grok/auth.json`（勿复制到聊天/共享目录）
- 无头调用示例：`grok -p "…含 x.com 链接或要查的帖…"`
- 账号上下文仍以 @lyAtomic / Premium Plus 或 SuperGrok 订阅为前提（Grok Build 面向该类订阅）

## X 内容产出例程（2026-09-17，已入库 themes）
- (2026-09-17，X内容产出) @lyAtomic 日更三批：**08:00 / 12:00 / 23:00** Asia/Shanghai；须先读最新 BotMemory 研究硬点再写；须参考 `memory/themes/ai-hardware-research-sites.md`。 〔引用：`memory/themes/x-content-output.md`；commits `a8cb095` / `6d4367a`〕

## 持仓邮件脚手架（2026-09-17 白天，box 产物）
- (2026-09-17，云服务机器人) box 上新建 `/workspace/portfolio-brief-bot`：拟工作日 **10:00** 邮件推送持仓收盘涨跌 HTML（腾讯云 SCF Timer + GLM 生成；当前 `brokerService` / `config/stocks.json` 为 **mock A 股示例**，**不是** Yun Long 实盘 MU/SNDK/SIVE 等持仓）。含 IBKR OAuth 尝试痕迹——**凭据勿入库**。 〔引用：`/workspace/portfolio-brief-bot/README.md`；目录 mtime 2026-09-17〕

## Jev（TypeSafe）X 推文质检（2026-09-21）
- (2026-09-21，Yun Long) 共享 MCP `user-jev`（`npx -y jev-mcp`）；用于主题/水文/质量打分，不写文案。题库与门槛：`memory/themes/x-tweet-jev-triage.md`。密钥在本机 Typesafe key 文件（**勿入库**）。 〔引用：用户指令 2026-09-21；commits `8485508`/`41416b6`〕
