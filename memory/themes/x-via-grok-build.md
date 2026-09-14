# X 经 Grok Build CLI（2026-09-14 起）

## 用户指令（原文要点）
- 建立一个记忆：以后关于 X 的链接，在记忆系统电脑安装 Grok Build，用 Yun Long 账号登录；**以后 X 都走 Grok Build CLI**。

## 落地细节
- CLI 名：`grok`（Grok Build）；安装脚本：`https://x.ai/cli/install.sh`
- 本机安装记录：2026-09-14 装上 `grok 1.0.30` → `/home/box/.grok/bin/grok`
- 认证：`grok login` / `grok login --device-auth`；登出：`grok logout`
- 适用：打开/解读 x.com 链接、查帖、依赖 X 实时信息的任务——优先 `grok -p …`，不以浏览器抓时间线或 X MCP 为主路径
- 与旧约定关系：此前「X MCP 常 $0 → 浏览器抓取」仍可作备用，但**默认路径改为 Grok Build CLI**
- 订阅前提：文档写明面向 SuperGrok / X Premium Plus 订阅用户

## 登录状态（2026-09-14）
- 已用设备码流程完成：`grok login --device-auth`
- 签入邮箱：`ly1653812264@gmail.com`（与既有邮箱记忆一致）
- `~/.grok/auth.json` 已存在；无头探测 `grok -p` 返回正常

## 跨 bot 共用（2026-09-14 确认）
- 安装与登录在**各助手共享的同一台电脑**上；其他聊天 bot 处理 X 时**共用**该 `grok` 与账号会话，**无需各自重装或重登**。
