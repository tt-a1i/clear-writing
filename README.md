# Clear Writing

让 AI 的中文和英文回答更容易读。

这个仓库维护两个独立的 Agent Skill，用于优化解释、任务汇报和文本改写。目标是让读者更容易理解重点、关系和依据。必要时，多写几个字也值得。

## 两个 Skill

| Skill | 用途 |
| --- | --- |
| [clear-writing-zh](clear-writing-zh/SKILL.md) | 中文表达优化，处理名词堆叠、长修饰、模糊指代和成果汇报 |
| [clear-writing-en](clear-writing-en/SKILL.md) | English clarity: unpack dense phrases, clarify sentence relationships, and report evidence accurately |

两个文件夹各自包含完整的 `SKILL.md`，可以单独安装和使用，不依赖另一个 Skill。

## 安装与使用

使用支持 Agent Skills 的客户端。具体调用方式取决于客户端。

通过 [skills CLI](https://github.com/vercel-labs/skills) 选择安装：

```bash
npx skills add tt-a1i/clear-writing --skill clear-writing-zh
npx skills add tt-a1i/clear-writing --skill clear-writing-en
```

也可以克隆仓库，把需要的整个 Skill 文件夹复制到客户端的 skills 目录。不要只复制 README，也不要把两个 `SKILL.md` 合并。

例如，在支持 `$skill-name` 的客户端中：

```text
使用 $clear-writing-zh 改写下面这段话。保留事实、语气和不确定性。

使用 $clear-writing-zh 总结本次任务。说明完成范围、验证结果和剩余事项。

Use $clear-writing-en to revise this explanation for a general audience.
Preserve the facts and uncertainty.
```

默认只作用于当前任务。需要持续采用时明确说明，例如「后续中文回复使用 clear-writing-zh」。安装 Skill 不会自动改写项目文件，也不代表授权发布或发送内容。

## 我们想改善什么

AI 的回答有时内容正确，却需要反复读才能理解。常见问题是把多个概念挤进一个短语，省去关键关系，或用几段过程叙述埋住结果。

两个 Skill 遵循共同的取舍：

- 先回答读者的问题，再补充依据。
- 让动作、对象、条件和因果关系清楚可见。
- 保留必要术语，用熟悉的说法解释陌生概念。
- 保留事实与限定条件，区分观察、推断和建议。
- 汇报完成范围与验证范围，避免把修改、测试、合并和发布混为一谈。
- 按内容选择自然段、列表或表格，不强制套模板。

中文和英文分别维护。英文里的关系代词省略、名词动用问题，不能直接变成中文禁令。熟悉的比喻、自然的长句和必要的连接词都可以保留。

### 一个例子

以下事实和文本均为虚构示例。

改写前：

> 完成了登录刷新并发竞态治理及异常恢复路径验证，平台兼容性仍待补齐。

假设实际证据只有「修改了刷新逻辑、并发刷新测试通过、没有测试 iOS」，应写成：

> 已修改登录刷新逻辑，并发刷新测试通过。iOS 端尚未验证。

改写时不能把原文中没有证据支持的部分，当成已确认的成果。若只有原文而没有上述证据，应保留其事实范围或指出歧义。

## 依据与边界

这个项目受到 [dualface/ste-zh](https://github.com/dualface/ste-zh) 的启发，尤其是结论先行、用具体动词和如实汇报验证状态。这里的 Skill 为独立编写，并采用更灵活的句长、结构和措辞规则；本项目不是 ASD-STE100 标准或其官方中文版本。

另一个参考是 Clark、Martin 与 Mahowald 的预印本 [Why is AI-generated language so hard to understand?](https://arxiv.org/abs/2610.29162)（2026-10-21）。论文比较了 14 个模型在不同场景下的语言特征，并探索了压缩压力对表达选择的影响。

论文只分析英文，不能直接证明中文规则的效果，也没有直接证明这两个 Skill 能减少阅读疲惫。研究结果是设计参考；这些规则的实际效果仍需要在真实任务中检验。

## 持续维护

这是一个会持续修订的仓库。我们会从实际使用中收集读起来费力、改写失真、结构僵硬的例子，再决定是否调整规则。

欢迎提交 Issue 或 Pull Request。一个有用的改进案例应包含：

1. 场景和读者：这段话写给谁，帮助对方做什么。
2. 已脱敏的原文与必要的来源事实。
3. 具体问题：哪里需要回读、哪里容易误解。
4. 建议改写，以及必须保留的条件与不确定性。
5. 适用语言，是否需要同步调整另一种语言。

维护时先检查已有规则能否处理问题。只有真实案例显示缺口时，才新增规则。调整共同原则时审查两个 Skill；语言特有的问题只改对应版本。过时、重复或让表达更僵硬的规则应删掉。

评估时用相同输入分别生成启用与未启用 Skill 的文本，检查事实和限定条件是否保留，再比较理解难度、自然程度和重点是否容易找到。记录模型、提示词和样本，不把单次偏好当作普遍结论。句子更短本身不算改进证据。

提交前检查两个 Skill 的元数据、链接、示例和含义一致性。仓库不设置逐字匹配的输出测试；规则和示例不能证明真实读者体验。

## English

Two standalone Agent Skills for clearer Chinese and English prose. Use `clear-writing-zh` for Chinese and `clear-writing-en` for English. Each folder is independently installable with the commands above.

The skills preserve meaning, voice, causal relationships, and justified uncertainty. They favor readable explanations and evidence-based task reports without fixed sentence limits or mandatory report templates.

We plan to refine them using real, anonymized examples. Contributions should include the audience, source facts, original text, proposed revision, and the specific difficulty being addressed. Evaluate factual fidelity before readability. The linked research informs the design; it does not validate these skills or establish their effectiveness in Chinese.

## License

[MIT](LICENSE)
