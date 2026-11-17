# Grilling CN

**把模糊想法问清楚，再决定怎么做。**

基于 [mattpocock/skills 的 grilling](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) 的中文适配，独立维护、非官方。

## 核心流程

把计划拆成有依赖关系的设计树，每轮提出当前能回答的全部问题并给出推荐。先调查可以查明的事实，用户回答后更新决策树；直到没有遗漏分支，再确认双方理解一致。

适合推敲产品方案、技术设计和重要选择；需要用户参与回答，不能无人值守替用户做决定。

## 小幅补充

- 中文提问，解释必要术语，保留原始标识。
- “是／同意”接受推荐，避免双重否定和一个问题捆绑多个决定。
- 推荐附简短理由与代价，区分事实、建议和已确认的选择。
- 结束时中文复述关键决定，保持原来的确认边界。

## 安装与调用

```bash
npx skills add batespaige357-tech/grilling-cn --skill grilling-cn
```

对助手说：“用 grilling-cn 帮我推敲这个方案，按依赖关系分轮问我。”Codex 可使用 `$grilling-cn`。也可复制 `skills/grilling-cn` 整个目录到助手的技能目录。

原流程调查环境事实时使用子代理，需要宿主具备相应能力；本包不附带代理运行时、浏览器或外部账号。无需安装其他 Matt Pocock 技能。

## 来源与检查

MIT，保留 Matt Pocock 版权及完整许可证。详见 [CHANGES.md](CHANGES.md)。

已检查原正文完整保留、UTF-8、本地引用及技能格式。未进行真实多轮访谈或助手行为评估；不宣称能够保证决策正确。仓库不含示例网页、截图或前后对比，未运行前端编译。
