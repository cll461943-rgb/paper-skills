# 审稿意见回复信（Response Letter）编写指南与模板

收到期刊大修（Major Revision）、小修（Minor Revision）或顶会 Rebuttal 通知时，回复信的目标是让审稿人与编辑用最少的时间确认：每一条顾虑都被认真听懂了、每一项实质改动都在正文里落地了、没有回避任何硬问题。

## 一、核心原则

1. 先落地，后动笔：先把需要补做的实验、重绘的图和重写好的段落改完，再写回复信。严禁在回复信里口头答应“已澄清”而正文一字未改。
2. 逐条拆解，一问一答：如果一位审稿人在一大段话里提了三个独立问题，拆成 `R1-C1`、`R1-C2`、`R1-C3` 逐个编号回复，不把棘手问题埋进长段里糊弄过去。
3. 结论前置：每条回复第一句先给明确答复（已补充某项实验 / 已重构某节并收窄主张 / 感谢指出歧义并改写表述），再展开量化数据与修改位置。
4. 不卑不亢，客观冷静：杜绝情绪化争辩（如“审稿人没有仔细读第 4 节”）。即便对方误读，也先检讨原文表达不够直白，再平和指出原意并说明正文做了哪处增强。
5. 精确定位与摘录：每一处修改都写明修订稿中的章节号、页码/行号或图/表号，并直接贴出关键新增或修改后的短摘录（标出改动处），方便审稿人不来回翻全文就能验收。

## 二、四类棘手意见的处理策略

- 面对真实硬伤（如过度声称、单系统局限）：直接承认原稿表述过宽或验证不足。若修订期内补上了实验，给出完整对照表；若客观条件受限，主动把相关主张从标题、摘要和贡献中撤回，并在 Limitations 中如实界定边界。
- 面对新增大工作量实验要求：先评估是否为核心主张的必证项。若是，优先完成最小可验证闭环；若超出本篇范围或受算力/数据许可制约，给出在代表性子集上的受控验证结果，说明完整扩展的现实边界并写入未来工作。
- 面对审稿人误读：先给明确事实和数据澄清，随后展示在正文对应位置增加的显式定义或小图说明，避免其他读者产生同样误解。
- 面对审稿人意见冲突（例如 R1 要求扩写某部分，R2 要求大幅压缩）：在致编辑的总说明和相关条次中坦诚点出权衡方案（如主文保留核心结论、详细推导与补充表迁入附录），让编辑看到全局协调。

## 三、回复信标准模板（英文投稿常用结构，中文返修可等比例对应）

```markdown
# Response to Reviewers

Dear Editor and Reviewers,

We sincerely thank the Editor and all reviewers for their constructive and thorough feedback. The reviews helped us identify key gaps in <briefly name 2-3 core areas, e.g., experimental closure, claim boundaries, and figure clarity>.

### Summary of Major Revisions
1. **<Major Revision 1>**: <One-sentence summary of new experiment or method fix, with exact section/table pointer.>
2. **<Major Revision 2>**: <One-sentence summary of narrowed claims or restructured narrative.>
3. **<Major Revision 3>**: <One-sentence summary of redrawn figures and formatting cleanup.>

All modifications in the revised manuscript are highlighted in <color, e.g., blue> (and tracked in the accompanying diff PDF). Below we provide a point-by-point response to each comment.

---

## Response to Reviewer 1

### Comment R1-1 (Summary / Quote)
> <Exact quote or faithful summary of the reviewer's concern.>

**Response:**
We thank the reviewer for pointing out <core issue>. <Direct verdict sentence: We have conducted the requested ablation / revised the claim in Section X / added a paired evaluation.>

Specifically, <present concrete quantitative results, control settings, or concise table here>. These results show that <bounded takeaway without overclaiming>.

**Manuscript Revision:**
- **Section X.Y (Page P, Lines L1–L2):** Added the paired ablation analysis and updated Table N.
- **Revised excerpt:**
  > "<Exact short excerpt of the revised text, highlighting the key change.>"

---

### Comment R1-2
> <Next concern.>

**Response:**
<Direct answer + evidence + exact revision pointer.>

---

## Response to Reviewer 2
(Repeat the same numbered structure for every reviewer and every sub-point.)
```

## 四、提交前回复信自查表

- [ ] 编辑信和每位审稿人的所有意见（包括嵌套在长段里的次要问题）均已拆分编号并全部回应，零遗漏。
- [ ] 每条回复给出的页码、行号、节号、图号、表号与最终提交的修订版 PDF 完全一致。
- [ ] 回复信中新增的所有数据、置信区间与修订版正文/附录表格完全吻合，无小数位打架。
- [ ] 全文语气礼貌、克制、以证据说话，无防御性反驳或空洞感谢堆砌。
- [ ] 修订版 PDF 的高亮标记清晰无错乱，且匿名审稿阶段回复信中同样未泄露作者身份信息。
