---
name: internet
description: internet-programmer-painkiller 的别名技能，用于让你在 Hermes 里输入 /internet 时更容易看到技能提示。
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [developer-experience, debugging, workflow, docs, focus, devops, internet]
    canonical_skill: internet-programmer-painkiller
---

# Internet

这是 `internet-programmer-painkiller` 的短别名版本。

当互联网程序员卡住的原因不是代码知识不足，而是工作流摩擦、反馈太慢、状态不可见、工具碎片化时，使用这个 Skill。

典型触发场景：
- 反复调试但总在盲猜
- 本地环境经常出问题
- build / test / reload 太慢
- 工具和平台切换太多
- 运行时行为不透明
- 文档过期或 runbook 缺失
- 上下文切换疲劳
- CI / review / 安全检查频繁拖慢节奏

## 产出目标

在合适场景下，最终应输出：
1. 当前最主要摩擦点的排序
2. 今天最短路径的修复动作
3. 一个防止复发的 system fix
4. 一个轻量 runbook 或 checklist 更新
5. 一个可衡量的验证步骤

## 工作流

### 阶段 1：采集摩擦信息
尽量用最少信息判断：
- 哪个任务失败了？
- 最短可复现路径是什么？
- 延迟卡在哪里？
- 哪些问题每周都会重复？

把问题归类到一个或多个 pain bucket：
- feedback-loop latency
- invisible state
- environment/setup drift
- tooling fragmentation
- docs/discoverability gap
- review/security/compliance drag
- maintenance/operational overload

### 阶段 2：先稳定反馈回路
在做大改前先止住混乱：
1. 用最小路径复现问题
2. 去掉无关工具、标签页、步骤
3. 记录精确命令、输入、日志、预期与实际
4. 补一个可见探针

规则：如果程序员说“我在猜”，就先提升可见性。

### 阶段 3：选择最短路径修复
只选一个 immediate fix：
1. 先让行为可见
2. 缩短反馈回路
3. 减少移动部件
4. 记录已知可行路径
5. 自动化重复检查

### 阶段 4：产出 system fix
当 immediate fix 生效后，沉淀一个最小预防工件：
- troubleshooting note
- setup script
- make/task command
- runbook
- checklist
- test case
- CI guardrail
- docs example

### 阶段 5：验证改进
至少测量以下一项：
- time to reproduce
- time to first useful feedback
- number of steps to local setup
- number of tools/tabs needed
- number of manual checks replaced
- frequency of the recurring failure

## 输出格式

应用这个 Skill 时，回复应包含：
1. Pain buckets detected
2. Immediate shortest-path fix
3. System fix to prevent recurrence
4. What to measure next

## 在 Hermes 中的可发现性

如果你希望在 Hermes 中输入 `/internet` 就看到明显的技能提示，请把这个目录和 `skill/internet-programmer-painkiller/` 一起安装。

## 示例调用

- "Use internet. 我的本地环境只能在一台机器上工作。请判断 pain buckets，并给出 shortest-path fix。"
- "Use internet. CI 很慢而且 flaky。请按优先级列出摩擦点，并给出高杠杆修复方案。"
- "Use internet. 我在调试时一直盲猜，因为运行时状态不清楚。请给我 immediate fix、system fix，以及下一步该测量什么。"
