# 账号与工具

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
- **以后凡涉及 X（Twitter）链接与查询**：在记忆系统电脑安装 **Grok Build**（`grok` CLI），用 Yun Long 的账号登录；**一律走 Grok Build CLI**，不再优先用浏览器抓取或 X API/MCP。
- 安装：`curl -fsSL https://x.ai/cli/install.sh | bash`（本机已装 `grok 1.0.30`，路径 `/home/box/.grok/bin/grok`）
- 登录：`grok login`（默认 OAuth）或无浏览器环境用 `grok login --device-auth`
- 凭据存于 `~/.grok/auth.json`（勿复制到聊天/共享目录）
- 无头调用示例：`grok -p "…含 x.com 链接或要查的帖…"`
- 账号上下文仍以 @lyAtomic / Premium Plus 或 SuperGrok 订阅为前提（Grok Build 面向该类订阅）
