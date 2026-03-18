# 🫐 OpenClaw Mac mini 备份

Mac mini 上 OpenClaw 的配置和记忆文件备份。

## 内容结构

```
├── openclaw-config/
│   └── openclaw.json    # 主配置文件（敏感信息已脱敏）
├── crons/
│   └── jobs.json        # 定时任务配置
├── workspace/
│   ├── AGENTS.md        # 工作区引导文件
│   ├── SOUL.md          # 身份/灵魂文件
│   ├── TOOLS.md         # 本地工具笔记
│   ├── USER.md          # 用户信息
│   ├── IDENTITY.md      # AI身份
│   ├── MEMORY.md        # 长期记忆
│   ├── HEARTBEAT.md     # 心跳任务
│   ├── memory/          # 每日记忆日志
│   ├── docs/            # 文档
│   └── skills-config/
│       └── index.txt    # 已安装技能列表
└── .gitignore
```

## 备份时间

自动备份（由 OpenClaw 定时任务执行）

## 注意

- `openclaw.json` 中的 API Key 和 Secret 已脱敏为 `***REDACTED***`
- 不包含 node_modules 和扩展文件
