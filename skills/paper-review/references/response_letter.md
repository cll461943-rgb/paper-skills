# 审稿意见答复指南与模板（会议答辩 / 期刊返修）

收到审稿意见后，先按投稿类型拆分流程，不再把顶会答辩（Rebuttal）与期刊返修（Major/Minor Revision）塞进同一份模板。两类场景的目标一致：让审稿人与编辑在最短时间内确认每条顾虑都被认真听懂、每项实质改动都有据可查、没有回避任何硬问题，但两者的交付形态与约束截然不同。

## 一、场景分流与前置核对

### 场景 A：会议答辩（Rebuttal / Author Response）

动笔前先按当届评审平台与官方通知登记以下规则（未核实项标为待补，全部以当届 CFP 与系统说明为准）：

1. 平台长度上限：分别记录全局总评（Global Response）与各审稿人单独回复的字符或字数上限。
2. 截止时间与讨论机制：记录答辩截止时刻，以及后续是否开放多轮 Author-Reviewer Discussion。
3. 新结果与改稿权限：确认平台是否允许提交新实验结果、附图表、上传修订版 PDF 或提供匿名链接。
4. 匿名与保密边界：确认答辩阶段不得泄露作者身份、单位或非匿名仓库；若借助外部模型辅助起草，先核对保密条款并记录授权范围与服务留存设置。

输出形态为可直接粘贴进评审平台的纯文本或 Markdown 逐点答复，紧凑直白，不套用期刊致编辑长信头，也不强行制作平台不接收的标红追踪稿。

### 场景 B：期刊返修（Major / Minor Revision）

动笔前逐条核对编辑决策信与期刊返修指南，按实际要求准备交付包：

1. 干净修订稿（Clean Manuscript）。
2. 逐点回复信（Response to Reviewers）及修改说明（Summary of Changes，按刊物要求合并在信首或单独提交）。
3. 标色或追踪修订稿（Marked-up / Tracked Changes Version）：**仅在编辑信或期刊指南明确要求时生成**，并严格按要求选择高亮颜色或 diff 格式，不作为无条件的默认必交件。

## 二、核心原则

1. 先落地，后动笔：期刊返修先把补实验、重绘图和重写段落全部落到干净修订稿里，再写回复信。会议答辩在平台允许范围内先完成核验实验或确定正文改动方案，允许交修订稿时同步落地，不允许改稿时明确说明将在终稿修订的确切章节与内容。严禁口头声称“已澄清”而缺乏实际改动支撑。
2. 逐条拆解，一问一答：如果一位审稿人在一大段话里提了三个独立问题，拆成 `R1-C1`、`R1-C2`、`R1-C3` 逐个编号回复，不把棘手问题埋进长段里糊弄过去。
3. 结论前置：每条回复第一句先给明确答复（已补充某项实验 / 已重构某节并收窄主张 / 感谢指出歧义并改写表述），再展开量化数据与修改位置。
4. 不卑不亢，客观冷静：杜绝情绪化争辩（如“审稿人没有仔细读第 4 节”）。即便对方误读，也先检讨原文表达不够直白，再平和指出原意并说明正文做了哪处增强。
5. 精确定位与摘录：期刊返修的每一处修改都写明干净修订稿中的章节号、页码/行号或图/表号，并贴出关键新增或修改后的短摘录。会议答辩受字数所限时，优先呈现关键量化对照与明确位置指针，仅对核心争议句给精炼改写摘录。

## 三、四类棘手意见的处理策略

- 面对真实硬伤（如过度声称、单系统局限）：直接承认原稿表述过宽或验证不足。若修订期或答辩窗口内补上了实验，给出完整对照表；若客观条件受限，主动把相关主张从标题、摘要和贡献中撤回，并在 Limitations 中如实界定边界。
- 面对新增大工作量实验要求：先评估是否为核心主张的必证项。若是，优先完成最小可验证闭环；若超出本篇范围或受算力/数据许可制约，给出在代表性子集上的受控验证结果，说明完整扩展的现实边界并写入未来工作。
- 面对审稿人误读：先给明确事实和数据澄清，随后展示在正文对应位置增加的显式定义或小图说明，避免其他读者产生同样误解。
- 面对审稿人意见冲突（例如 R1 要求扩写某部分，R2 要求大幅压缩）：在致编辑的总说明（或会议答辩的 Global Response）和相关条次中坦诚点出权衡方案（如主文保留核心结论、详细推导与补充表迁入附录），让编辑或领域主席看到全局协调。

## 四、会议答辩模板（Rebuttal，适配平台直接提交）

```markdown
<!-- 提交前删除本核对块
平台约束登记（以当届 CFP 与系统说明为准）：
- 评审平台与届次：<待补>
- 长度上限：Global Response <待补> 字符/词；单审稿人回复 <待补> 字符/词
- 截止时间：<待补>
- 允许提交新结果：<是 / 否 / 限补充说明>
- 允许上传修订稿或图表：<是 / 否>
- 允许匿名链接：<是 / 否>
- 核对日期：<YYYY-MM-DD>
-->

### Global Response（若平台提供全局回复框）
We thank the Area Chair and all reviewers for their constructive feedback. Three themes appeared across reviews, which we address concisely below:
1. **<Shared Concern 1>**: <Direct answer + key quantitative evidence or narrowed scope.>
2. **<Shared Concern 2>**: <Direct answer + key comparison or planned camera-ready revision in Section X.>

---

### Response to Reviewer 1

**[R1-C1] <Short label of concern>**
<Direct verdict sentence.> <Concise quantitative evidence, control setting, or bounded takeaway aligned with our frozen statistical protocol.> <If revision upload is permitted: Updated in Section X.Y / Table N. Otherwise: We will include this clarification and Table N in Section X.Y of the final version.>

**[R1-C2] <Short label of concern>**
<Direct answer + evidence + exact planned or applied section pointer.>

---

### Response to Reviewer 2
(Repeat compact numbered items for every reviewer and every sub-point within platform length limits.)
```

## 五、期刊返修回复信模板（Response Letter，英文投稿常用结构，中文返修可等比例对应）

```markdown
# Response to Reviewers

Dear Editor and Reviewers,

We sincerely thank the Editor and all reviewers for their constructive and thorough feedback. The reviews helped us identify key gaps in <briefly name 2-3 core areas, e.g., experimental closure, claim boundaries, and figure clarity>.

### Summary of Major Revisions
1. **<Major Revision 1>**: <One-sentence summary of new experiment or method fix, with exact section/table pointer.>
2. **<Major Revision 2>**: <One-sentence summary of narrowed claims or restructured narrative.>
3. **<Major Revision 3>**: <One-sentence summary of redrawn figures and formatting cleanup.>

<!-- 仅当编辑信或期刊指南明确要求提交标色或追踪修订稿时保留下一句，否则删除 -->
[If requested by the Editor: All modifications in the revised manuscript are highlighted in <color, e.g., blue> (and tracked in the accompanying marked-up PDF).] Below we provide a point-by-point response to each comment.

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

## 六、提交前自查表

### 通用核查项

- [ ] 编辑信、领域主席和每位审稿人的所有意见（包括嵌套在长段里的次要问题）均已拆分编号并全部回应，零遗漏。
- [ ] 答复中新增的所有数据、区间估计与统计结果均与正文、附录表格及冻结实验口径完全一致，无小数位打架。
- [ ] 全文语气礼貌、克制、以证据说话，无防御性反驳或空洞感谢堆砌。
- [ ] 匿名审稿阶段未泄露作者身份、机构或非匿名仓库；审稿意见及草稿未越权外发至不符合保密与留存要求的第三方服务。

### 会议答辩专项

- [ ] 全局与分审稿人答复的长度严格低于当届平台字符或字数上限，可直接粘贴进平台且格式清晰。
- [ ] 未违反当届关于提交新结果、上传修订稿、贴图或匿名链接的规则，提交前已删去内部核对注释块。

### 期刊返修专项

- [ ] 每条回复给出的页码、行号、节号、图号、表号与最终提交的干净修订稿 PDF 完全一致。
- [ ] 严格按编辑信与期刊指南组包：未要求标色修订稿时未擅自多交；明确要求时，标色标记清晰无错乱且与干净修订稿内容一致。
