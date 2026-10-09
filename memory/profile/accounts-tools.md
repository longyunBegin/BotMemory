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

## 持仓邮件 IBKR 授权（2026-10-06，云服务机器人）
- IBKR refresh token 距 9/26 授权约 10 天再次过期；用户在 Mac 上重新授权（`~/portfolio-brief-bot-oauth`），token 与 .env 拷回 `/workspace/portfolio-brief-bot`；`--force` 补发 10/5 邮件成功（8 只持仓，交易日 2026-10-05，收件 longyundevelopment@163.com，SMTP 250 OK）；每日 10:00 定时照旧。预计约 10 天一过期，届时需再授权。凭据不入库。 〔引用：云服务机器人对话 2026-10-06〕

## 2026-10-07 工具与账号变动（对话补录）
- (新想法) 用户 10/6 晚开启 Google 两步验证；10/7 18:09 用存好的 Gmail 应用专用密码测 SMTP 登录 **LOGIN_OK**，观察池日报不受影响；只有改 Google 密码或撤销该应用密码才失效。 〔引用：新想法对话 2026-10-07〕
- (云服务机器人) 10/7 持仓邮件照常发出（8 只，交易日 10/6，SMTP 250 OK）。 〔引用：云服务机器人对话 2026-10-07〕
- (Research) 例程「Serenity X 监听」用登录 @lyAtomic 的浏览器只读查 @aleabitoreddit，10/7 09:36–15:31 正常（基线 status/2107534129780920682，10/7 02:11），17:34 那轮 X 报错「Something went wrong」没查成，按规则未改用 Grok 或 X API。 〔引用：Research 对话 2026-10-07〕
- (Reddit) 仓库 **longyunBegin/reddit-intel**：Python 标准库 CLI，从 Arctic Shift（主）/PullPush（备）拉 Reddit 数据给 AI 用。实测问题：不带 --subs 静默返回空、--since 窗口实际只覆盖最近约 20 帖、429 重试过快、PullPush 已全面 429 等；发现 Arctic Shift 帖子 score/评论数约 36 小时后才回填，但评论接口近实时（约 30 秒延迟）。已派云端编程代理 bc-c0acfe4a-e641-524c-ba63-d16be2d8c420 修复并加「按实时评论数排热度」功能，开 PR 不合并。新想法确认 reddit-intel 不是它建的。 〔引用：Reddit 对话、新想法对话 2026-10-07 23:45〕

## 2026-10-08–10/09 工具与账号（对话补录）
- (2026-10-09，云服务机器人·portfolio-brief) 本地分支 `fix/data-accuracy` commit **d5d1e6b**，用户确认预览后 **ff 合并进 master 并 push**（origin/master = d5d1e6b）。改动要点：IBKR 限流当错误（isError/−32300/429）、限速队列、日K **TWO_WEEKS**、昨收严格对齐交易日、缺数据 **N/A**、盈亏按 EUR/USD 分币种、过滤 0 股、2027 假期。README 更新日志 push：**140ab75**。 〔引用：云服务机器人对话 2026-10-09〕
- (同上) 盒子 SMTP **465/587 不通**；在 Mac `~/pbb-run/portfolio-brief-bot` 用 `--force` 发出交易日 **2026-10-08** 持仓邮件，收件 **longyundevelopment@163.com**，SMTP 250 OK；token 轮换后拷回盒子。每日发信方式（Resend / 改 Mac 例程）用户**未最终选定**。凭据不入库。 〔引用：同上〕
- (2026-10-09，新想法) 观察池日报：盒子 SMTP 不通 → 例程改为触发 GitHub Actions **`scan.yml`** 发信；补发「观察池日报 2026-10-08」（Actions run **37876246552**）。 〔引用：新想法对话 2026-10-09〕
- (2026-10-09，新想法) 用户问 @mail.grokbot.com / claim **eden**：助手说明**无法代申请** claim。 〔引用：同上〕
- (2026-10-08，Reddit) reddit-intel PR#1 已合并 **59a5944**：`--subs` 必填、真实 `--since` 窗口、429 按 Reset 等待、`--engagement`/`hot`。（10/7 开 PR 未合并状态已关闭。） 〔引用：Reddit 对话 2026-10-08〕
- (待办) BotMemory 仓库是否公开（10/7 已问）至本对话窗口仍未答复。 〔引用：新想法对话〕
