# 主流期刊与会议格式档案

说明：各期刊与会议每年可能微调页数限制、声明模块和匿名政策。下表给出常规基准参数，正式落版与提交前务必对照目标去向当届官方 Author Guidelines 或 Call for Papers 复核；表中标为“以当届官网为准”的细项须在项目格式卡中补齐实测值。

## 一、快速对照总表

| 目标去向 | 官方模板 | 栏数 | 正文篇幅惯例 | 摘要限制 | 匿名要求 | 参考文献风格 | 特有必需项 |
|---|---|---|---|---|---|---|---|
| Elsevier（Information Fusion / KBS） | `elsarticle.cls` | 审稿常用单栏 `review` / 终版或自审常用 `5p,twocolumn` | 常见双栏 12–16 页（无硬性一刀切，过长易被拒） | 通常 150–250 词 | 多为单盲（以具体刊物最新政策为准） | `elsarticle-num` 或 `elsarticle-harv` | Highlights、CRediT 声明、利益冲突声明、数据可用性声明 |
| IEEE TPAMI / TNNLS | `IEEEtran.cls` (`journal`) | 双栏 | TPAMI 常规稿一般 14 页内；TNNLS 常规约 10–14 页（超页规则见官网） | 通常 150–250 词，不含公式和引用 | 一般为单盲（以当年政策为准） | `IEEEtran.bst`（数字顺序） | Index Terms；录用终稿需作者简介与照片 |
| NeurIPS | `neurips_202X.sty` | 单栏 | 9 页正文（不含参考文献、Checklist 与附录） | 简明一段，通常 150–250 词 | 严格双盲 | `natbib`（作者-年份或编号，依模板默认） | NeurIPS Paper Checklist（必附）、局限性讨论 |
| ICML | `icml202X.sty` | 双栏 | 8 页正文（不含影响声明、参考文献与附录） | 建议 4–6 句，简明单段 | 严格双盲 | `icml202X.bst`（作者-年份） | Broader Impact Statement（放参考文献前，不占正文页数） |
| ICLR | `iclr202X_conference.sty` | 单栏 | 常规 9–10 页正文（以当届 CFP 为准，不含参考文献与附录） | 一段式，无硬性极短上限但建议 250 词内 | 严格双盲（OpenReview） | `iclr202X_conference.bst`（作者-年份） | Ethics / Reproducibility 声明（推荐/按需）、LLM 使用披露（以当届政策为准） |
| ACL ARR（ACL / EMNLP / NAACL） | `acl_latex`（`acl.sty`） | 双栏 | 长文 8 页、短文 4 页（不含 Limitations、Ethics、参考文献与附录） | 建议 150–250 词 | 严格双盲 | `acl_natbib.bst`（作者-年份） | 强制 Limitations 专节（通常放正文后、参考文献前）、Responsible NLP Checklist |

## 二、分刊细则与高频踩坑点

### 1. Elsevier `elsarticle`（Information Fusion、Knowledge-Based Systems）
- 模板选项：初投审稿常见 `\documentclass[preprint,12pt]{elsarticle}` 或 `review` 单栏便于审稿人阅读；若为了直观掌控印刷篇幅与双栏图宽，可用 `5p,twocolumn` 预排检查，再按期刊投稿系统要求决定上传单栏还是双栏 PDF。
- Highlights 硬规则：独立列出 3 至 5 条纯英文要点，每条严格不超过 85 个英文字符（含空格），不能写成中文，不能塞入未解释缩写或公式，也不重复摘要原句。
- 声明模块：文末规范填写 CRediT authorship contribution statement、Declaration of competing interest、Data availability（不可留“占位”或红字）。
- 图形摘要（Graphical Abstract）：多为推荐或可选，若提交则独立构图，聚焦核心机制而非直接截正文某张数据表。
- 主题契合提醒：投 Information Fusion 时，若正文主打多源信息融合，必须给出清晰的融合机理、冲突消解分析以及信息融合领域的代表文献，不可仅做口号式贴标。

### 2. IEEE 期刊（TPAMI、TNNLS）
- 模板结构：使用 `\documentclass[journal]{IEEEtran}`，首页自带双栏排版、摘要与 `IEEEkeywords`（Index Terms）。
- 摘要禁区：IEEE 摘要必须独立成篇，严禁在摘要里出现文献引用编号、图表引用和复杂数学公式。
- 图表与页数：TPAMI 对超页收费与总页数有明确上限（以当年官网最新规定为准）；长公式跨栏需谨慎使用 `figure*` 置顶或拆行，避免打断双栏阅读流。
- 文献格式：严格使用 `IEEEtran.bst` 样式，按正文出现顺序编号，作者名缩写与期刊名标准缩写保持一致。

### 3. ML 三大顶会（NeurIPS / ICML / ICLR）
- 页数红线：超出一行都可能触发 desk reject。绝不允许通过修改页边距、压缩行距、改小正文字号或缩小图注字体来硬塞页数，官方脚本会自动检测样式篡改。
- 匿名要求：禁用 `\author` 真名，使用模板匿名开关；文中引用自己先前工作必须用第三人称（“Wang et al. 提出……”而非“在我们先前的工作中……”）；开源代码用匿名仓库（如 Anonymous GitHub）或提交补充材料压缩包，剥离所有带个人/机构标识的 URL。
- 必备章节与清单：NeurIPS 必须完整、诚实填写 Paper Checklist 并附在参考文献之后（乱填“Yes”而正文无对应内容会被直接质疑诚信）；ICML 必须包含 Impact Statement；ICLR 需注意 OpenReview 公开评审期与当届 LLM 使用披露规范。

### 4. ACL ARR（ACL / EMNLP / NAACL）
- 强制 Limitations：长短文均须设置 `Limitations` 专节（紧接结论之后、参考文献之前，通常不计入 8/4 页正文上限），诚实交代适用范围、数据偏置、算力开销与失败边界，未写 Limitations 可能直接拒稿。
- 伦理与复现：涉及人工标注、用户隐私或敏感安全评测时，增设 `Ethics Statement` 并完整填写 ARR 的 Responsible NLP Checklist。
- 匿名期与预印本：核查当届 ARR 是否仍保留匿名期规定或已调整预印本政策（具体口径以当届官网公告为准）。

## 三、Word 内部讨论稿的最低底线

当导师或合作者习惯在 Word 中用批注审阅中文讨论稿时，可额外导出一份内部 `.docx`，但须满足三条底线：
1. 绝不直接拿 `pandoc` 默认样式裸导出的文件交付审稿或投稿。
2. 若由 Markdown 转 Word，必须配好定制样式文件（统一中英文字体、标题层级、表格边框、段落间距），并在首页顶部标明“内部讨论稿（非最终期刊排版）”。
3. 导出后人工翻查每一张表格和公式，确认没有窄列挤压和公式编号错位。
