# Internet Programmer Painkiller

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
[![Hermes Skill](https://img.shields.io/badge/Hermes-Skill-6f42c1)](./skill/internet-programmer-painkiller/SKILL.md)
[![English README](https://img.shields.io/badge/README-English-blue)](./README.md)
[![Last Commit](https://img.shields.io/github/last-commit/MengYanChenHub/internet-programmer-skill)](https://github.com/MengYanChenHub/internet-programmer-skill/commits/main)

[English](./README.md) | 简体中文

一个面向互联网程序员的、基于研究总结的 Hermes Skill。
它专门处理那些最常见、最耗时间、但又不只是“不会写代码”导致的问题：工具过多、反馈太慢、运行状态看不见、文档过期、上下文切换频繁。

这个仓库把这些痛点整理成了可复用的内容：
- 一个 Hermes Skill
- 一组实用模板
- 一套可直接复制的示例提示词
- 一组框架场景示例
- 一份研究来源汇总

## 目录

- [为什么要做这个 Skill](#为什么要做这个-skill)
- [仓库内容](#仓库内容)
- [适合谁用](#适合谁用)
- [这个 Skill 会做什么](#这个-skill-会做什么)
- [快速开始](#快速开始)
- [如何在 Hermes 中使用](#如何在-hermes-中使用)
- [可发现性与 `/internet` 别名](#可发现性与-internet-别名)
- [截图](#截图)
- [框架示例](#框架示例)
- [推荐使用流程](#推荐使用流程)
- [示例场景](#示例场景)
- [设计原则](#设计原则)
- [研究基础](#研究基础)
- [仓库结构](#仓库结构)
- [后续可扩展方向](#后续可扩展方向)
- [License](#license)

## 为什么要做这个 Skill

很多程序员的痛苦，不是语法不会写，而是工作流有摩擦：
- 意外复杂度太高
- edit-run-debug 反馈链路太慢
- 运行时行为不可见
- 工具、平台、流程割裂
- 文档过期或分散
- 安全/评审/CI 问题总在后期爆炸
- 维护性工作和杂活吞掉了真正的开发时间

这个仓库把这些高频问题收敛成一个可复用 Skill：`internet-programmer-painkiller`。

## 仓库内容

### 核心 Skill
- `skill/internet-programmer-painkiller/SKILL.md`

### 研究资料
- `research/sources.md` — YouTube 演讲、开发者调查、行业报告汇总

### 模板
- `templates/friction-log.md` — 记录重复性痛点并排序
- `templates/debugging-runbook.md` — 降低调试中的猜测成本
- `templates/golden-path-checklist.md` — 优化项目启动、文档与迭代体验
- `templates/incident-to-runbook.md` — 把事故沉淀成可复用知识
- `templates/ci-friction-checklist.md` — 排查 CI / Review 中的低效摩擦

### 示例
- `examples/example-prompts.md` — 可以直接给 Hermes 使用的提示词
- `examples/sample-output.md` — 一个完整输出示例
- `examples/frameworks/nextjs.md` — Next.js 常见摩擦与处理方式
- `examples/frameworks/python-backend.md` — Python 后端调试与可观测性示例
- `examples/frameworks/ci-cd.md` — CI/CD 慢、脆、反复失败的处理示例

## 适合谁用

适合以下角色：
- 被环境问题、调试问题、工具问题拖慢的独立开发者
- 在代码、基础设施、CI、文档之间来回切换的工程师
- 想减少团队内耗的 Tech Lead
- 做开发者体验 / DevOps / 平台工程的同学
- 一直在处理“同类问题反复出现”的维护者

## 这个 Skill 会做什么

加载后，它会帮助你：
1. 把问题归类到具体痛点桶里
2. 优先恢复可见性，停止盲猜
3. 选出今天最短路径的修复动作
4. 产出一个能防止复发的小型工件
5. 用可衡量指标验证是否真的变好了

覆盖的痛点桶包括：
- 反馈链路过慢
- 运行状态不可见
- 环境/依赖/启动漂移
- 工具碎片化
- 文档和可发现性差
- review / 安全 / 合规摩擦
- 维护性与运营性负担过重

## 快速开始

### 方式 1：把它当成参考仓库
直接阅读 Skill 和模板，应用到你自己的团队流程或 Agent 工作流里。

### 方式 2：作为本地 Hermes Skill 使用
把核心 Skill 和短别名一起复制到 Hermes 的 skills 目录：

```bash
mkdir -p ~/.hermes/skills/
cp -R skill/internet-programmer-painkiller ~/.hermes/skills/
cp -R skill/internet ~/.hermes/skills/
```

`internet` 这个别名不是必需的，但如果你希望在 Hermes 里输入 `/internet` 就更快看到提示，建议一起安装。

然后启动 Hermes 并加载它。

## 如何在 Hermes 中使用

### 1. 启动 Hermes
```bash
hermes
```

### 2. 在会话里加载 Skill
标准名称加载：
```text
/skill internet-programmer-painkiller
```

短别名加载：
```text
/skill internet
```

如果你的 Hermes 版本支持 slash suggestions，直接输入 `/internet` 通常就会把这个别名 Skill 提示出来。

或者启动时预加载：

```bash
hermes -s internet-programmer-painkiller
hermes -s internet
```

### 3. 给出你的问题
示例：

```text
Use internet-programmer-painkiller.
我的 Next.js 项目在一台机器能跑，在另一台机器上却会在 npm install 和 dev 启动阶段反复报错。请帮我判断痛点桶、给出最短路径修复方案，以及应该补什么预防性工件。
```

```text
Use internet-programmer-painkiller.
我们团队总是在 CI 等待、修 flaky check、反复解释环境配置这些事上浪费时间。请做一次 friction audit，按优先级列出问题，并给出投入最小但收益最高的改进建议。
```

```text
Use internet-programmer-painkiller.
我在调试后端时一直在猜，因为我看不见请求进入后到数据库写入前到底发生了什么。请给我 immediate fix、system fix，以及下一步该测量什么。
```

### 4. 理想输出结构
Hermes 的输出最好包含：
1. 识别出的 pain buckets
2. 当前最短路径修复动作
3. 防止复发的 system fix
4. 下一步要量化的指标

### 5. 常用 Hermes 命令
```bash
hermes skills list
hermes -s internet-programmer-painkiller
hermes -s internet
```

```text
/skill internet-programmer-painkiller
/skill internet
/internet
/help
```

## 可发现性与 `/internet` 别名

为什么要加这个别名目录？
- 核心 Skill 名称清晰，但偏长。
- 短别名能提升会话内的可发现性。
- 在支持 slash suggestions 的 Hermes 构建里，`/internet` 更短、更好记。

推荐方式：
- 保留 `skill/internet-programmer-painkiller/` 作为 canonical skill。
- 额外安装 `skill/internet/` 作为可发现性别名。
- 如果你在团队里共享这个 Skill，最好把这两个名字都写进内部文档。

## 截图

下面放了 3 张真实 Hermes 使用截图，同时也可以查看 [docs/screenshots.zh-CN.md](./docs/screenshots.zh-CN.md)。

### 1. 根因诊断
![根因诊断截图](./assets/screenshots/01-diagnosis.png)

### 2. 区分旧失败进程与新成功进程
![旧失败进程与新成功进程截图](./assets/screenshots/02-old-vs-new-process.png)

### 3. 修复完成并可运行
![修复完成并可运行截图](./assets/screenshots/03-fixed-and-running.png)

## 框架示例

如果你想直接看更贴近实际项目的案例，可以打开：
- `examples/frameworks/nextjs.md`
- `examples/frameworks/python-backend.md`
- `examples/frameworks/ci-cd.md`

这些文件里包含：
- 典型 pain buckets
- 可直接喂给 Hermes 的 prompt
- 常见 shortest-path fix
- 适合沉淀的 prevention artifact
- 建议追踪的指标

## 推荐使用流程

1. 先拿一个真实问题跑一次。
2. 把产出的 checklist / runbook / script 保存下来。
3. 把这个问题登记到 `templates/friction-log.md`。
4. 下次再出现同类摩擦时，重复使用这个 Skill。
5. 持续观察反馈时间、启动步骤、人工检查次数是否真的下降。

## 示例场景

### 场景 1：本地反馈太慢
问题：
- 测试太慢
- 大家懒得本地跑
- bug 都堆到 CI 才发现

可能输出：
- pain bucket: feedback-loop latency
- immediate fix: 拆出 smoke subset + watch mode
- prevention artifact: 一条本地快速测试命令
- measure: time to first useful feedback

### 场景 2：运行状态不可见
问题：
- 大家总说“按理应该可以”，但看不到真实 payload / 状态变化

可能输出：
- pain bucket: invisible state
- immediate fix: 加结构化日志 / request ID / state dump
- prevention artifact: debugging runbook
- measure: time to reproduce / isolate bug

### 场景 3：新同学环境搭建混乱
问题：
- 新贡献者启动项目必须靠口头指导

可能输出：
- pain bucket: environment/setup drift
- immediate fix: 提供 one-command bootstrap
- prevention artifact: golden path checklist + verified quickstart
- measure: setup steps 数量、onboarding 失败率

## 设计原则

- 先让运行行为可见。
- 优先缩短反馈回路。
- 尽量减少移动部件。
- 调试流程标准化。
- 文档写给“下一个焦虑中的开发者”。
- 把重复性安全检查自动化。

## 研究基础

这个 Skill 主要参考了：

### YouTube
- Rich Hickey — Simple Made Easy
- Bret Victor — Inventing on Principle
- Bret Victor — The Future of Programming
- Douglas Engelbart — The Mother of All Demos

### 其他来源
- Stack Overflow Developer Survey 2024
- JetBrains State of Developer Ecosystem 2024
- Stripe Developer Coefficient
- Google Cloud / DORA DevOps Research
- GitLab Developer Survey / DevSecOps Report

具体链接与汇总见 `research/sources.md`。

## 仓库结构

```text
.
├── README.md
├── README.zh-CN.md
├── assets/
│   └── screenshots/
│       ├── 01-diagnosis.png
│       ├── 02-old-vs-new-process.png
│       └── 03-fixed-and-running.png
├── docs/
│   ├── screenshots.md
│   └── screenshots.zh-CN.md
├── research/
│   ├── sources.md
│   └── sources.zh-CN.md
├── skill/
│   ├── internet/
│   │   ├── SKILL.md
│   │   └── SKILL.zh-CN.md
│   └── internet-programmer-painkiller/
│       ├── SKILL.md
│       └── SKILL.zh-CN.md
├── templates/
│   ├── ci-friction-checklist.md
│   ├── ci-friction-checklist.zh-CN.md
│   ├── debugging-runbook.md
│   ├── debugging-runbook.zh-CN.md
│   ├── friction-log.md
│   ├── friction-log.zh-CN.md
│   ├── golden-path-checklist.md
│   ├── golden-path-checklist.zh-CN.md
│   ├── incident-to-runbook.md
│   └── incident-to-runbook.zh-CN.md
└── examples/
    ├── example-prompts.md
    ├── example-prompts.zh-CN.md
    ├── sample-output.md
    ├── sample-output.zh-CN.md
    └── frameworks/
        ├── ci-cd.md
        ├── ci-cd.zh-CN.md
        ├── nextjs.md
        ├── nextjs.zh-CN.md
        ├── python-backend.md
        └── python-backend.zh-CN.md
```

