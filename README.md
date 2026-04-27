<div align="center">

# Persona Distill Skills

**精选公众人物思维操作系统，可直接安装到 Claude Code Agent 中使用。**

每一个 skill 都基于大量公开资料系统蒸馏：著作、访谈、演讲、学术论文、博客。<br>
不是语录合集，是可运行的思维框架。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skills-blueviolet)](https://claude.ai/code)
[![Personas](https://img.shields.io/badge/Personas-1-brightgreen)](#persona-目录)

</div>

---

## 快速开始

```bash
# 安装单个 skill（以香帅为例）
curl -o ~/.claude/skills/xiangshuai.md \
  https://raw.githubusercontent.com/fxp/persona-distill-skills/main/personas/xiangshuai/SKILL.md

# 安装蒸馏工具（用于自行蒸馏新人物）
curl -o ~/.claude/skills/persona-distill.md \
  https://raw.githubusercontent.com/fxp/persona-distill-skills/main/SKILL.md
```

安装后在 Claude Code 里说出触发词即可激活。

---

## Persona 目录

### 公众人物与方法论视角

| Persona | 领域 | 触发词 | 简介 |
|---------|------|--------|------|
| [**香帅（唐涯）**](personas/xiangshuai/) | 金融·中国经济 | `香帅` `唐涯` | 前北大金融学副教授，中国经济年度观察者。蒸馏自年度演讲《共潮生》系列、《香帅金融学讲义》等。 |

---

## 食用方法

### 1. 激活 Skill

安装后，直接在 Claude Code 对话中说出触发词：

```
香帅，现在中国经济到底怎么了？
用香帅的视角帮我分析一下这次关税战
```

### 2. 首次激活说明

首次激活时，Claude 会简短声明：
> 「我以香帅视角和你聊，基于公开资料推断，非本人」

之后的对话直接以角色身份回应，不再重复。

### 3. 退出角色

说「退出」「切回正常」即可恢复正常模式。

### 4. 每个 Skill 都有明确边界

每个 persona 页面都列出了「**擅长**」和「**不擅长**」，以及调研截止时间。使用前建议快速浏览。

---

## 蒸馏工具

本 repo 附带一个**人格蒸馏工具** ([SKILL.md](SKILL.md))，可以对任意公众人物自动执行蒸馏：

```bash
# 安装蒸馏工具
curl -o ~/.claude/skills/persona-distill.md \
  https://raw.githubusercontent.com/fxp/persona-distill-skills/main/SKILL.md
```

安装后说：

```
蒸馏 Paul Graham
帮我做黄仁勋的 skill
distill Sam Altman
```

工具会自动搜索多类公开来源（博客/著作/访谈/论文/演讲），生成符合本 repo 规范的完整 SKILL.md，可直接提交 PR 收录。

---

## 贡献

**想要新增某位人物？** 提 [Issue](https://github.com/fxp/persona-distill-skills/issues/new) 告诉我名字和理由。

**想自己蒸馏后提交？** 见 [CONTRIBUTING.md](CONTRIBUTING.md)。

每个 persona 需要独立目录：

```
personas/
└── your-persona/
    ├── README.md          # 介绍页：签名引语、效果示例、安装说明、蒸馏清单
    ├── SKILL.md           # 可直接安装的 skill 文件
    └── examples/          # 真实对话示例（至少 2 个）
        ├── example-1.md
        └── example-2.md
```

---

## License

MIT — skill 内容基于公开资料，仅供学习和思维工具使用，不代表当事人本人。
