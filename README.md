> **注意：** 本仓库包含 Anthropic 为 Claude 实现的技能（Skills）。有关 Agent Skills 标准的信息，请参阅 [agentskills.io](http://agentskills.io)。

[![skills.sh](https://skills.sh/b/anthropics/skills)](https://skills.sh/anthropics/skills)

# 技能（Skills）

技能是由指令、脚本和资源组成的文件夹，Claude 可以动态加载它们以提升在特定任务上的表现。技能教会 Claude 如何以可重复的方式完成特定任务，无论是按照你公司的品牌指南创建文档、根据你组织的特定工作流分析数据，还是自动化个人任务。

更多信息，请参阅：
- [什么是技能？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [用 Agent Skills 为真实世界装备智能体](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# 关于本仓库

本仓库包含展示 Claude 技能系统能力的各种技能。这些技能涵盖从创意应用（艺术、音乐、设计）到技术任务（测试 Web 应用、MCP 服务器生成），再到企业工作流（沟通、品牌塑造等）。

每个技能都独立存放在各自的文件夹中，包含一个 `SKILL.md` 文件，其中含有 Claude 使用的指令和元数据。浏览这些技能可以为你创建自己的技能提供灵感，或帮助你理解不同的模式和方法。

本仓库中的许多技能是开源的（Apache 2.0）。我们还在 [`skills/docx`](./skills/docx)、[`skills/pdf`](./skills/pdf)、[`skills/pptx`](./skills/pptx) 和 [`skills/xlsx`](./skills/xlsx) 子文件夹中包含了驱动 [Claude 文档功能](https://www.anthropic.com/news/create-files) 的文档创建和编辑技能。这些是源码可用（source-available）而非开源，但我们希望与开发者分享这些技能，作为在生产级 AI 应用中实际使用的更复杂技能的参考。

## 免责声明

**这些技能仅供演示和教育目的。** 虽然其中某些功能可能在 Claude 中可用，但从 Claude 获得的实现和行为可能与本仓库所展示的有所不同。这些技能旨在展示模式与可能性。在依赖它们处理关键任务之前，请务必在自己的环境中充分测试。

# 技能集合
- [./skills](./skills)：创意与设计、开发与技术、企业与沟通、以及文档技能等技能示例
- [./spec](./spec)：Agent Skills 规范
- [./template](./template)：技能模板

# 在 Claude Code、Claude.ai 和 API 中试用

## Claude Code
你可以通过以下命令将此仓库注册为 Claude Code 插件市场：
```
/plugin marketplace add anthropics/skills
```

然后，安装特定技能集：
1. 选择 `Browse and install plugins`
2. 选择 `anthropic-agent-skills`
3. 选择 `document-skills` 或 `example-skills`
4. 选择 `Install now`

或者，直接通过以下命令安装插件：
```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

安装插件后，你只需提及技能名称即可使用。例如，如果你从市场安装了 `document-skills` 插件，可以这样让 Claude Code 执行任务："使用 PDF 技能从 `path/to/some-file.pdf` 中提取表单字段"

## Claude.ai

这些示例技能均已在 Claude.ai 的付费计划中可用。

要使用本仓库中的任何技能或上传自定义技能，请按照 [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b) 中的说明操作。

## Claude API

你可以通过 Claude API 使用 Anthropic 预构建的技能，也可以上传自定义技能。详情请参阅 [Skills API 快速入门](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

# 创建基础技能

创建技能非常简单——只需一个包含 `SKILL.md` 文件的文件夹，文件中包含 YAML 前置元数据和指令。你可以将本仓库中的 **模板技能** 作为起点：

```markdown
---
name: my-skill-name
description: 对该技能功能和使用场景的清晰描述
---

# 我的技能名称

[在此添加 Claude 在该技能激活时将遵循的指令]

## 示例
- 示例用法 1
- 示例用法 2

## 指南
- 指南 1
- 指南 2
```

前置元数据仅需要两个字段：
- `name` — 技能的唯一标识符（小写字母，用连字符代替空格）
- `description` — 对技能功能和使用场景的完整描述

下方的 Markdown 内容包含 Claude 将遵循的指令、示例和指南。更多详情请参阅 [如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

# 合作伙伴技能

技能是教会 Claude 更好地使用特定软件的好方法。当我们看到来自合作伙伴的优秀示例技能时，可能会在这里重点介绍：

- **Notion** — [适用于 Claude 的 Notion 技能](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
