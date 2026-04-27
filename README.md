<div align="center">

# Persona Distill Skills

**精选公众人物思维操作系统，可直接安装到 Claude Code Agent 中使用。**

每一个 skill 都基于大量公开资料系统蒸馏：著作、访谈、演讲、学术论文、博客。<br>
不是语录合集，是可运行的思维框架。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skills-blueviolet)](https://claude.ai/code)
[![Skills](https://img.shields.io/badge/Skills-1-brightgreen)](#skill-目录)

</div>

---

## 快速开始

### 安装单个 skill

```bash
# 下载到全局 skill 目录（所有项目可用）
curl -o ~/.claude/skills/xiangshuai.md \
  https://raw.githubusercontent.com/fxp/persona-distill-skills/main/skills/xiangshuai.md
```

### 安装所有 skill

```bash
# 克隆整个 repo，批量安装
git clone https://github.com/fxp/persona-distill-skills
cp persona-distill-skills/skills/*.md ~/.claude/skills/
```

### 也可以安装蒸馏工具本身

```bash
# 安装 persona-distill 工具 skill（用于蒸馏新人物）
cp persona-distill-skills/SKILL.md ~/.claude/skills/persona-distill.md
```

安装后重启 Claude Code，或在对话中说「加载 skill」即可生效。

---

## Skill 目录

| 人物 | 领域 | 触发词 | 擅长 | 文件 |
|------|------|--------|------|------|
| [香帅（唐涯）](#香帅唐涯) | 金融学·中国经济 | `香帅` `唐涯` `用香帅的视角` | 宏观经济判断、家庭财富配置、金融底层逻辑 | [skills/xiangshuai.md](skills/xiangshuai.md) |

---

## 食用方法

### 1. 激活 Skill

安装后，在 Claude Code 对话中直接说出触发词即可激活：

```
用香帅的视角，帮我分析一下现在该不该卖房
```

```
香帅，我想了解一下中国出海企业的机会
```

Skill 激活后，Claude 会以该人物的**第一人称**回应，应用其思维框架和决策逻辑。

### 2. 首次激活

首次激活时，Claude 会简短说明：
> 「我以香帅视角和你聊，基于公开资料推断，非本人」

之后的对话**不再重复**免责声明，直接以角色身份回应。

### 3. 退出角色

说「退出」「切回正常」即可恢复 Claude 正常模式。

### 4. 混合使用

可以在同一对话中调用多个 skill：

```
先用香帅的视角分析中国经济，再用巴菲特的框架看资产配置
```

### 5. 每个 Skill 的能力边界

每个 skill 文件都有明确的「**擅长**」和「**不擅长**」说明，以及「**诚实边界**」——
包括调研截止时间、已知盲区和推断说明。使用前建议快速浏览。

---

## Skill 详情

### 香帅（唐涯）

> 金融学者、前北大教授、中国经济年度观察者

**蒸馏来源**：年度演讲《共潮生》2022/2024/2025全文、《香帅金融学讲义》、《熟经济》、《钱从哪里来》系列、36氪/虎嗅访谈

**核心心智模型**：
- **金融三体**：时间×资金×风险——理解一切金融现象的元框架
- **熟经济**：中国从创富时代进入守富时代的结构性判断
- **纺锤型守富**：家庭资产配置的底线思维（底层保底·中层稳健·上层冒险）
- **叙事经济学**：不确定性高时市场跟叙事走，不跟基本面走
- **三个集装箱**：中国产业出海三代演进框架

**适合问她的问题**：
- 「现在中国经济到底怎么了？」
- 「我手里有钱，该怎么配置？」
- 「什么是复利/杠杆/信用？」
- 「中国出海企业的机会在哪里？」
- 「普通人在守富时代该怎么办？」

**不适合问她的问题**：短期股市预测、具体个股推荐、地缘政治内幕

**安装**：
```bash
curl -o ~/.claude/skills/xiangshuai.md \
  https://raw.githubusercontent.com/fxp/persona-distill-skills/main/skills/xiangshuai.md
```

---

## 蒸馏工具

本 repo 附带一个**人格蒸馏工具** ([SKILL.md](SKILL.md))，可以对任意公众人物执行蒸馏：

```bash
# 安装蒸馏工具
cp SKILL.md ~/.claude/skills/persona-distill.md
```

安装后，在 Claude Code 中说：

```
蒸馏 Paul Graham
帮我做黄仁勋的 skill
distill Sam Altman
```

工具会自动搜索多类公开来源，生成符合本 repo 规范的 SKILL.md，可直接提交 PR 收录。

蒸馏工具支持：
- 企业家、投资人（有大量访谈、博客）
- 学者、研究者（有论文、讲座）
- 作家、思想家（有著作、文章）
- 公众人物（有新闻报道、演讲）

---

## Skill 文件格式

每个 skill 文件是标准 Markdown，包含 YAML frontmatter：

```markdown
---
name: person-perspective
description: |
  [人名]的思维框架，基于[来源]蒸馏。
  触发词：「[人名]」「用[人名]的视角」
type: perspective
调研时间: YYYY-MM-DD
---

# [人名] 思维操作系统

## 使用说明（擅长/不擅长）
## 角色扮演规则
## 回答工作流（Agentic Protocol）
## 身份卡
## 核心心智模型（3-7个）
## 决策启发式（5-10条）
## 表达DNA
## 人物时间线
## 价值观与反模式
## 内在张力
## 智识谱系
## 诚实边界
## 调研来源
```

---

## 贡献

**想要新增某位人物？** 提 [Issue](https://github.com/fxp/persona-distill-skills/issues/new) 告诉我名字和理由，我会安排蒸馏。

**想自己蒸馏后提交？** 见 [CONTRIBUTING.md](CONTRIBUTING.md)。

**发现 skill 有错误或过时？** 直接提 PR 或 Issue。

---

## License

MIT — skill 内容基于公开资料，仅供学习和思维工具使用，不代表当事人本人。
