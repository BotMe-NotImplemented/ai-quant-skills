---
name: ai-quant-strategy-workflow
description: Guide a beginner from a vague quantitative-strategy idea to an approved task brief and one-at-a-time indicator, strategy, risk, backtest, review, and paper-simulation stages with observable evidence and mandatory human gates, ending before live trading. Use when a user asks to plan, build, validate, backtest, simulate, troubleshoot, or advance a quantitative trading strategy project, especially when requirements, risk choices, acceptance criteria, or stage status are unclear.
---

# AI 量化策略项目工作流

## 目标

把模糊的量化策略想法整理成用户可审核的任务单，再按阶段完成开发和验收。始终以行为正确和证据充分为先，不用盈利、无报错或 Agent 的口头声明代替验收。V1 停在实盘门前。

## 加载参考

- 理解需求、创建或更新任务单时，读取 [任务单模板](references/task-brief-template.md)。
- 冻结阶段计划、执行阶段或判断能否推进时，读取 [阶段验收合同](references/stage-acceptance.md)。

## 坚守规则

1. 让用户决定策略目标、交易和风险参数、验收标准以及是否考虑实盘。可以解释选项并推荐保守起点，不得静默代选。
2. 将每个决定标记为 `confirmed`、`waiting_for_confirmation` 或 `not_in_this_project`。把未解决的交易或风险决定视为阻塞输入。
3. 涉及 TqSdk API、函数、账户类型或产品行为时，调用已安装的 TqSdk 官方文档 Skill、查阅源码或查阅当前官方文档。记录核验来源；无法核验时把事实标为未解决并暂停相关实现。不得把本 Skill 当成 TqSdk 事实来源，也不得复制或冒充官方文档 Skill。
4. 一次只推进一个阶段。上一阶段未通过或用户未批准下一阶段时，不得越级。
5. 只报告实际执行得到的文件、命令、输出、日志和交易域记录。保留失败证据，不得编造执行、平台状态、行情或测试结果。
6. 将回测盈利与行为正确分开。盈利不证明实现正确，模拟运行也不证明可以实盘。
7. 不自动切换真实账户，不执行实盘放行。到达实盘门时停止，并要求建立一个新的、由用户批准的项目阶段。

## 执行工作流

### 1. 先理解策略

- 让用户用自己的话说明策略观察什么、何时交易、为什么可能产生结果。
- 对不清楚的概念先查证并用白话解释；区分已核验事实、假设和用户选择。
- 如果用户仍无法说明策略意图，将状态设为 `waiting_for_strategy_understanding`，列出最少待确认问题，不写策略代码。
- 得到用户明确的理解确认后再创建任务单。

### 2. 创建并批准任务单

- 按任务单模板确认品种、行情周期、指标和参数、信号与动作、持仓状态、风险限制、测试方法和预期停止阶段。
- 解释每个重大选择的影响，不以默认值掩盖未确认决定。
- 展示完整任务单和未决项。未决交易或风险项存在时保持阻塞。
- 只有用户明确批准任务单后，记录 `confirm_start` 及其原始批准语句；不得替用户生成批准。

### 3. 冻结阶段计划

按以下顺序建立计划：

1. 指标验证；
2. 基础策略逻辑；
3. 持仓与风险处理；
4. 历史回测；
5. 日志与成交记录复盘；
6. TqKq 模拟；
7. 模拟验收；
8. 实盘门。

为每个阶段预先声明目标、允许修改的范围、检查方法、验收证据和人工转换门。根据用户批准的任务单裁剪阶段内容，但不得颠倒依赖关系或跳过适用的安全门。

### 4. 每次只运行一个阶段

1. 声明当前阶段、目标、拟修改文件、拟运行检查和预先约定的验收标准。
2. 先核验本阶段涉及的 TqSdk 事实，再实施本阶段范围内的工作。
3. 运行适用检查，返回实际文件、命令、输出、日志、信号、委托、成交、持仓或账户记录。
4. 逐条比较证据与预先约定的标准。
5. 验收失败时保持当前阶段为 `blocked` 或 `incomplete`，保存证据并说明最小修复或待决定事项。
6. 验收通过时设为 `passed_waiting_for_next_stage_approval`，等待用户批准下一阶段；不得把阶段通过自动解释为推进许可。

### 5. 处理失败与变更

- 区分需求未决、事实未核验、实现失败、环境受限和证据不足。
- 修复必须留在当前阶段，并用新的实际证据重新验收；不得覆盖或改写旧的失败证据。
- 任务单发生实质变更时，标记版本变化，指出受影响阶段，并重新取得用户批准。
- 模拟运行中发现缺陷时，停止、保留证据、变更版本并重新测试；不得原地修改正在运行的版本。

### 6. 停在实盘门

- 说明回测与模拟无法消除成交差异、拒单、延迟、网络或程序故障、经纪商或交易所限制以及真实资金风险。
- 要求用户另行批准账户、权限、资金、风险上限、停止方式和实盘验收标准。
- 将状态设为 `stopped_at_live_trading_gate`。V1 不创建、批准或执行实盘发布。

## 每次响应的状态块

在任务单、阶段开始、验收、阻塞和转换时，给出：

```text
current_stage:
stage_status:
confirmed:
waiting_for_confirmation:
not_in_this_project:
evidence_observed:
acceptance_result:
next_human_gate:
```

不要用计划中的命令冒充已运行命令，也不要用示例输出冒充实际输出。
