# CareerPilot

[中文](#中文) | [English](#english)

---

## 中文

CareerPilot 是一个面向长期职业规划的 skill，分成两种模式：

- 运行模式：用于稳定回答用户当前的职业规划问题
- 维护模式：用于更新职业规划链路本身

## 文件结构

- `SKILL.md`：主 skill 定义
- `decision.md`：职业决策框架
- `transition.md`：职业转型框架
- `growth.md`：职业成长框架
- `lens-handoff.md`：外部视角 skill 的显式调用与回传协议
- `chain-manifest.md`：当前链路与依赖记录
- `update-policy.md`：维护模式触发条件与采纳标准
- `evolution-log.md`：链路演化记录

## 设计原则

CareerPilot 不把“链路进化”混进每一次普通咨询。

- 运行模式负责回答用户当前的职业规划问题
- 维护模式负责判断 skill 自身是否需要更新

`bggg-skill-taotie` 在维护模式中作为进化器使用，而不是默认的运行时大脑。
CareerPilot 可以显式调用外部视角 skill，但最终结论必须回到 CareerPilot 做整合。
对行业 / 专业相关问题，顺序固定为：现状判断 -> 显式调用行业 lens -> CareerPilot 整合。

---

## English

CareerPilot is a long-horizon career planning skill with two distinct modes:

- runtime mode for stable career advice
- maintenance mode for updating the planning chain

## Files

- `SKILL.md`: main skill definition
- `decision.md`: decision framework
- `transition.md`: transition framework
- `growth.md`: growth framework
- `lens-handoff.md`: explicit invocation and return protocol for external lens skills
- `chain-manifest.md`: current chain and dependencies
- `update-policy.md`: maintenance trigger and adoption rules
- `evolution-log.md`: change history

## Design

CareerPilot does not mix chain evolution into every user session.

- Runtime mode answers the user's current career planning question
- Maintenance mode evaluates whether the skill itself should evolve

`bggg-skill-taotie` is used as an evolver in maintenance mode, not as the default runtime brain.
CareerPilot can explicitly invoke an external lens skill, but the final recommendation must return to CareerPilot for integration.
For domain-specific career questions, the order is fixed: current-state assessment -> explicit domain lens invocation -> CareerPilot integration.
