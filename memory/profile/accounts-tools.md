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

## 2026-10-10（周六）Grok Bot 原生邮箱 + 发信路径切换
- (2026-10-10，工具·共享用户记忆) Yun Long 的 Grok Bot 原生邮箱 **`lyatomic@mail.grokbot.com`** 由「工具」认领；要求**云服务机器人**与**新想法**以后用该地址给他发邮件。 〔引用：共享用户记忆 2026-10-10 via 工具；非凭据〕
- (2026-10-10，新想法 / trade commit **`b44ebb4`**) 观察池日报发信改走 **`lyatomic@mail.grokbot.com`**（显示名「新想法」），收件仍为个人 Gmail（不写进公开仓）：`scan.yml` 扫描步骤改为 `python scanner/scan.py --no-email`；`scanner/README.md` 写明日常不再用 Gmail SMTP / Actions cron 发信，由 Grok Bot 例程 SendEmail。Gmail Secrets 可留作备用。 〔引用：github.com/longyunBegin/trade `b44ebb4`；`.github/workflows/scan.yml`；`scanner/README.md`「发信方式（2026-10-10 起）」〕
- (2026-10-10，新想法·发信载荷) 本机 `trade/scanner/out/SENDEMAIL_NOW.json` 等：`from=lyatomic@mail.grokbot.com`，`from_name=新想法`，`to=ly1653812264@gmail.com`，`subject=观察池日报 2026-10-09`（数据日期 10/9 周五收盘，周六晨处理）。本轮**未**从对话正文确认 SMTP/SendEmail 送达回执；只记载荷与仓库约定。 〔引用：`/workspace/trade/scanner/out/SENDEMAIL_NOW.json`〕
- (2026-10-10，云服务机器人·发信载荷) `/workspace/final_send.json`：`from=lyatomic@mail.grokbot.com`，`from_name=云服务机器人`，`to=longyundevelopment@163.com`，`subject=[Portfolio Brief] 2026-10-09 P&L EUR -43.45% · USD +20.06%`；正文称 8 positions、Sent from Grok Bot (server)。本轮同样只记载荷，不臆测送达。 〔引用：`/workspace/final_send.json`；对照 `portfolio-brief-2026-10-09.html`〕
- (对照) 10/9 对话补录曾记：盒子 SMTP 不通、观察池临时走 Actions `scan.yml` 发信、claim eden 无法代申请——被本条 **`b44ebb4` + lyatomic** 路径部分取代。 〔引用：`episodes/2026-10-10-transcript-catchup.md`；本文件上一节〕

## 2026-10-10 对话补录（交叉午夜 `85c5282`）
- (2026-10-10，工具) 认领流程：试 **`eden` / `si` / `ly`** 均占用；用户给 **`lyAtomic`** → **`lyatomic@mail.grokbot.com`**（系统小写）。已 SendToAgent 转告云服务/新想法 + 共享用户记忆。用户原话「**收件箱不用变**」。 〔引用：工具对话 2026-10-10；交叉午夜认领硬点〕
- (同上·自发自收) 测试成功：云服务「测试-云服务机器人」message id **44346** / thread **b69a7d84**；新想法「测试-新想法」message id **44374**。显示名不同、地址同为 lyatomic。 〔引用：同上〕
- (同上) Mac SMTP 正式持仓邮件亦进 lyatomic（主题含 EUR −43.45% · USD +20.06%，发件 1653812264@qq.com）。数字见午夜 / `trading-holdings.md`。 〔引用：同上〕
- (2026-10-10，云服务机器人) IBKR 重授权：远程 Shell 后台监听会被杀（**8765** 回调拒绝）；须 Mac **Terminal.app** 常驻 **`ibkr-oauth-local.js`**。token 同步 Mac `pbb-run` 与 box。凭据不入库。 〔引用：云服务机器人对话 2026-10-10〕
- (同上) 盒子 QQ SMTP **465 ETIMEDOUT**；SendEmail from lyatomic（显示名「云服务机器人」）→ longyundevelopment@163.com，交易日 2026-10-09，message id **45372**（优先于失败 `$file:` **45079**）。日常例程仍定 Mac SMTP。 〔引用：同上〕
- (2026-10-10，新想法) `b44ebb4` 确认信 message id **44462**；例程「观察池日报」提示已更新。用户「你现在发送一份」：Yahoo 全员限流 → 用已有 10/09 `scan.md` SendEmail，message id **45302**（junk `$file:` **45230** 作废）；`email.html` 仍标 10/08 模板、正文为正确 10/09。`/workspace/se_html.html` = 发信临时副本（md5=email.html），非仓库文件。 〔引用：新想法对话 2026-10-10〕
