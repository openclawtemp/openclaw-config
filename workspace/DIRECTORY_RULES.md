# OpenClaw 目录结构规范

## 目录规则

```
~/.openclaw/
│
├── agent-workspaces/       # 🔴 Agent专属工作空间
│   ├── workspace-{agent-id}/   # 每个Agent一个独立目录
│   └── ...
│
├── projects/              # 🔴 独立项目目录
│   ├── {project-name}/      # 项目名
│   └── ...
│
├── workspace/             # 🔴 主工作空间（仅存放共享配置）
│   ├── AGENTS.md            # Agent定义
│   ├── HEARTBEAT.md         # 心跳任务
│   ├── workflows.js         # 工作流
│   ├── memory/              # 共享记忆
│   ├── scripts/             # 共享脚本
│   └── archive/            # 归档（临时文件）
│
├── skills/                # Skills（自动管理）
├── agents/                # Agent会话数据（自动生成）
├── memory/                # 长期记忆
├── logs/                  # 日志
├── credentials/           # 凭证
├── media/                 # 媒体文件
├── plugins/               # 插件
└── openclaw.json         # 主配置
```

## 规则说明

| 规则 | 说明 |
|------|------|
| **禁止在根目录创建workspace-*** | 必须放在 agent-workspaces/ |
| **禁止在workspace/放项目代码** | 项目必须放在 projects/ |
| **临时文件放archive/** | 测试脚本、截图等 |
| **配置文件用.bak备份** | 最多3个备份 |
