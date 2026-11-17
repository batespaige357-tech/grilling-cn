---
name: grilling-cn
description: 中文方案追问与决策澄清。Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled: the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask the whole frontier in one round: number each question and give your recommended answer. Then wait for the user's answers before the next round.

Format a round like so:

```
❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Word each question so "yes" accepts your recommended answer.

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent with a fresh context window to find it; don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.


## 中文适配 — grilling-cn 新增

独立社区适配，不代表 Matt Pocock 官方版本。沿用原设计树、依赖前沿、分轮提问、先查事实再请用户决策的方法。

- 用户使用中文时，用自然中文解释当前需要选择的问题。保留代码标识、产品名称和必要英文术语，首次出现的抽象概念用一句话说明实际含义。
- 原来的“yes 接受推荐”用“是／同意”也能接受推荐；每个问题只对应一个可确认的推荐，避免“是否不需要……”这种双重否定。若推荐包含真实取舍，简述理由和代价，允许用户另选或纠正前提。
- 同轮继续覆盖当前全部可回答的前沿问题；依赖尚未回答问题的后续选择留到后轮，不通过猜测填空。
- 将用户已确认的选择、尚未确认的建议、已查明的事实分开。用户否定推荐时，按实际回答更新设计树，不把默认推荐当成已同意；已回答的问题仅在新证据造成冲突时重新提出。
- 结束时用中文简要复述已达成的方案和关键取舍，请用户确认共享理解。确认前保持原流程的停止边界；访谈本身不授权修改代码、发布内容或执行方案。
