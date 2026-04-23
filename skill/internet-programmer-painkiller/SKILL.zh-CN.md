---
name: internet-programmer-painkiller
description: 通过诊断工作流摩擦、缩短反馈回路、提升运行时可见性、简化工具链，为互联网程序员提供可执行的止痛方案。
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [developer-experience, debugging, workflow, docs, focus, devops, internet]
    aliases: [internet]
---

# Internet Programmer Painkiller

当互联网程序员卡住的根因不是“不会写代码”，而是工作流混乱、反馈太慢、状态不可见、工具碎片化时，使用这个 Skill。

典型触发场景：
- 反复调试但总在盲猜
- 本地环境或启动流程经常出问题
- build / test / reload 反馈太慢
- 工具和平台切换太多
- 运行时行为不透明
- 文档过期或 runbook 缺失
- 上下文切换疲劳
- CI / review / 安全检查反复拖慢节奏

## 产出目标

在合适场景下，最终应输出：
1. 用户当前最主要的摩擦点排序
2. 今天最短路径的修复动作
3. 一个防止复发的 system fix
4. 一个轻量的 runbook 或 checklist 更新
5. 一个可衡量的验证步骤

## 基本假设

- 大多数程序员的痛苦，不是能力问题，而是反馈延迟、隐藏状态、工具割裂造成的。
- 第一目标不是优雅，而是恢复可见性和推进速度。
- 先修复最高频的问题，而不是声音最大的抱怨。
- 优先选择默认路径、模板和 golden path，而不是额外复杂度。

## 工作流

### 阶段 1：摩擦信息采集
尽量用最少信息判断当前问题：
- 失败的任务是什么？build、debug、deploy、review、setup、docs、onboarding
- 最短可复现路径是什么？
- 延迟卡在哪里？等待、盲猜、搜索、切换、审批、工具不稳定
- 什么问题是每周都会重复出现的？

将痛点归类到一个或多个桶：
- feedback-loop latency
- invisible state
- environment/setup drift
- tooling fragmentation
- docs/discoverability gap
- review/security/compliance drag
- maintenance/operational overload

### 阶段 2：先稳定反馈回路
在提出大改造前，先停止当前混乱：
1. 用最小复现路径复现问题
2. 移除无关工具、标签页和步骤
3. 记录精确命令、输入、日志、预期与实际结果
4. 至少补一个可见探针：
   - structured log
   - timestamp
   - request ID
   - failing test
   - state dump
   - screenshot 或 trace

规则：如果程序员说“我在猜”，就先加可见性，不要继续猜。

### 阶段 3：选择今天最短路径修复
只选一个 immediate fix，按优先级排序：
1. 先让行为可见
2. 缩短反馈回路
3. 减少移动部件
4. 记录已知可行路径
5. 自动化重复检查

示例：
- 不讨论理论，先补一个最小复现测试
- 开启 watch mode / hot reload / 更窄的测试选择
- 把 5 步 setup 收敛成 1 条脚本
- 为最高频故障补 troubleshooting 文档
- 为重复失误加 pre-commit 或 CI 校验

### 阶段 4：产出防复发工件
当 immediate fix 生效后，再选择一个最小可维护的预防工件：
- troubleshooting note
- setup script
- make / task 命令
- runbook
- checklist
- test case
- CI guardrail
- docs example

选择未来的你真的会维护的最小工件。

### 阶段 5：验证改进
至少测量以下一项：
- time to reproduce
- time to first useful feedback
- number of steps to local setup
- number of tools/tabs needed
- number of manual checks replaced
- frequency of the recurring failure

如果没有任何指标变好，说明修复还不完整。

## 按痛点桶给默认干预

### 1. Feedback-loop latency
症状：
- build / test / reload 很慢
- 每次学习都要先等待

干预方式：
- 拆出最小 failing test
- 使用 watch mode
- 缓存依赖和构建产物
- 区分快速 smoke checks 和慢速全量套件
- 提供 one-command dev 启动路径

### 2. Invisible runtime state
症状：
- 总说“理论上应该能跑”
- 对输入、状态、网络调用全靠猜

干预方式：
- 增加 structured logs
- 打印或检查中间状态
- 加 correlation IDs
- 对比 expected 与 actual payload
- 保留 traces 或可复现快照

### 3. Environment/setup drift
症状：
- 只能在一台机器上工作
- onboarding 很脆弱
- 版本不一致带来大量问题

干预方式：
- pin 版本
- 写 bootstrap script
- 增加 preflight checks
- 文档化一个 golden path
- 只有在整体复杂度更低时再考虑 devcontainers / Nix / Docker

### 4. Tooling fragmentation
症状：
- 标签页、App、CLI 来回切换太多
- 任务归属和入口不清晰

干预方式：
- 把常见流程收敛到一个 task runner
- 每个工作流只保留一个 source of truth
- 删除重复仪表盘和脚本
- 建立清晰的升级/求助路径

### 5. Docs/discoverability gap
症状：
- setup 文档过期
- 依赖口口相传
- 相同问题在群聊里重复被问

干预方式：
- example-first docs
- 标记 last-verified date
- 增加 troubleshooting section
- 提供可直接复制的安全命令
- 尽量从错误信息或 CI 直接链接到文档

### 6. Review/security/compliance drag
症状：
- 问题总在最后阶段爆炸
- review 成为瓶颈
- 大量手动重复检查

干预方式：
- 轻量 pre-commit checks
- 在 CI 中增加依赖扫描
- 使用带风险提示的 PR 模板
- 提供 secure-by-default 模板
- 尽量把策略检查前移自动化

### 7. Maintenance/operational overload
症状：
- 修修补补挤占功能开发
- 同一个 flaky failure 一直反复出现

干预方式：
- 维护 friction log
- 按 recurrence × severity 排序
- 预留明确的技术债预算
- 给 flaky tests 指定 owner 和清理期限
- 把 incident 沉淀成 runbooks

## 反模式

避免这些陷阱：
- 在缩小当前问题前，先上新平台或大重构
- 加没人会看的 observability
- 写巨大的流程文档，而不是一个能用的 checklist
- 在修通主路径前先优化边缘场景
- 把所有摩擦都归因于“人不行”

## 输出格式

应用这个 Skill 时，回复应包含：
1. Pain buckets detected
2. Immediate shortest-path fix
3. System fix to prevent recurrence
4. What to measure next

## 推荐配套工件

- `references/templates/friction-log.md`
- `references/templates/debugging-runbook.md`
- `references/templates/golden-path-checklist.md`
- `references/templates/incident-to-runbook.md`
- `references/templates/ci-friction-checklist.md`

## 这个 Skill 自带的 linked files

这个 Skill 已把配套文件放进 skill 目录下，Hermes 可以直接把它们作为 linked files 展示出来：
- `references/docs/screenshots.md`
- `references/docs/github-description.md`
- `references/examples/example-prompts.md`
- `references/examples/sample-output.md`
- `references/examples/frameworks/nextjs.md`
- `references/examples/frameworks/python-backend.md`
- `references/examples/frameworks/ci-cd.md`
- `references/research/sources.md`
- `references/templates/*.md`
- `references/assets/screenshots/*.png`

你可以用 `skill_view(name="internet-programmer-painkiller", file_path="...")` 直接打开它们。

## 在 Hermes 中的可发现性

如果你安装了可选别名目录 `skill/internet/`，那么在 Hermes 中输入 `/internet` 时，更容易在命令建议里直接看到这个 Skill；同时完整名称 `internet-programmer-painkiller` 仍然可用。

## 示例调用

你可以这样用：
- "Use internet-programmer-painkiller. 我的本地环境只能在一台机器上工作。请判断 pain buckets，并给出 shortest-path fix。"
- "Use internet. 我的本地环境只能在一台机器上工作。请判断 pain buckets，并给出 shortest-path fix。"
- "Use internet-programmer-painkiller. CI 很慢而且经常 flaky。请按优先级列出摩擦点，并给出最小但高杠杆的修复方案。"
- "Use internet-programmer-painkiller. 我在调试时一直盲猜，因为运行时状态不清楚。请给我 immediate fix、system fix，以及下一步该测量什么。"
