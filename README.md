# 复利复盘 Skill（Revival Retrospective Skill）

一个复盘对话 Skill，帮用户把日常经验压缩成可复用原则。

> **核心价值**：每次对话只给一个 24 小时可执行的行动指南，
> 并记住你提炼的原则，下次对话继续深化。

## 🚀 快速开始

### 1. 选择你的平台

| 平台 | 配置方式 |
|------|----------|
| Claude | [配置指南](#claude) |
| GPT | [配置指南](#gpt) |
| DeepSeek | [配置指南](#deepseek) |
| Gemini | [配置指南](#gemini) |

### 2. 复制通用 System Prompt

打开 [system-prompt.md](./system-prompt.md)，复制全部内容。

### 3. （可选）复制平台补丁

如果使用特定平台，额外复制对应补丁：
- [Claude 补丁](./patches/claude.md)
- [GPT 补丁](./patches/gpt.md)
- [DeepSeek 补丁](./patches/deepseek.md)
- [Gemini 补丁](./patches/gemini.md)

### 4. 粘贴到 AI 平台

将 System Prompt + 补丁粘贴到平台的 System Prompt / Custom Instructions 区域。

### 5. 开始复盘

对 AI 说：
- "最近状态不太好"
- "帮我复盘一下今天的一件事"
- "试试复利复盘"

## 📖 用户使用说明

参见 [memory-protocol.md](./memory-protocol.md) 了解记忆文件的用法。

## 🧪 部署后自测

参见 [test-checklist.md](./test-checklist.md) 进行基础验证。

## 📁 仓库结构

```
.
├── README.md                    ← 本文件
├── system-prompt.md             ← 通用 System Prompt
├── memory-protocol.md           ← 用户使用协议
├── test-checklist.md            ← 自测清单
├── CHANGELOG.md                 ← 版本变更日志
└── patches/                     ← 各平台适配补丁
    ├── claude.md
    ├── gpt.md
    ├── deepseek.md
    └── gemini.md
```

## 📋 配置指南

### Claude

1. 打开 Claude → Settings → Custom Instructions（或通过 API 设置 system message）
2. 粘贴 [system-prompt.md](./system-prompt.md) 全部内容
3. 在末尾追加 [patches/claude.md](./patches/claude.md) 内容
4. 保存

### GPT

1. 打开 ChatGPT → GPTs → Create（或 Custom Instructions）
2. 在 "Instructions" 区域粘贴：
   - [system-prompt.md](./system-prompt.md) 全部内容
   - [patches/gpt.md](./patches/gpt.md) 内容（追加在末尾）
3. 保存并测试

### DeepSeek

1. 打开 DeepSeek Chat → 系统提示设置（或通过 API 设置 system role message）
2. 粘贴 [system-prompt.md](./system-prompt.md) 全部内容
3. 在末尾追加 [patches/deepseek.md](./patches/deepseek.md) 内容
4. 保存

### Gemini

1. 打开 Google AI Studio → System Instruction（或通过 API 设置）
2. 粘贴 [system-prompt.md](./system-prompt.md) 全部内容
3. 在末尾追加 [patches/gemini.md](./patches/gemini.md) 内容
4. 保存

### 补丁使用原则

- 补丁是**追加**到主 System Prompt 末尾的，不是替换
- 每个平台只用自己的补丁，不混用
- 如果在某平台上发现新的行为偏差，在对应补丁文件中追加规则

## 🔄 记忆机制

本 Skill 采用用户自持记忆方案：

1. AI 每次收尾会生成一段结构化记忆条目
2. 用户保存到自己的文件（备忘录 / Notion / txt 都行）
3. 下次对话时，把记忆条目粘贴给 AI
4. AI 会读取并继续深化之前的复盘

详见 [memory-protocol.md](./memory-protocol.md)

## 📝 变更日志

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.0.0 | 2026-05-28 | 初始版本：核心 Prompt + 记忆机制 + 4 平台补丁 + 自测清单 |

详见 [CHANGELOG.md](./CHANGELOG.md)
