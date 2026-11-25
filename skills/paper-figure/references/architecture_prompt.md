# 架构图设计规范与图像模型 Prompt 模板

本文件用于指导论文中“问题动机实例图（图 1）”与“方法架构图（图 2）”的设计、AI 辅助出草稿及后续矢量化定稿。

## 一、工具选型边界

1. 定量数据图（折线图、柱状图、森林图、热力图、分布图）一律使用代码（如 Python `matplotlib` 或 R `ggplot2`）直接读取冻结数据绘制，严禁交由图像生成模型绘制，防止编造数值或坐标失真。
2. 架构图与机制示意图有两条推荐路线：
   - 路线 A（首选，完全可控）：先草拟布局与组件清单，直接用矢量工具（Draw.io、Figma、Inkscape、Illustrator 或手写干净 SVG）绘制，确保字体、箭头、数学符号和配色 100% 可编辑且与正文一致。
   - 路线 B（概念发散与审美参考）：用图像生成模型先产出构图和视觉风格草稿，确认信息流合理后，人工在矢量工具中临摹重建，或对底图做严格矢量化与文字重排。切勿把带有拼写错乱、模糊符号或伪公式的生图原图直接塞进终稿。

## 二、视觉与信息设计原则

1. 扁平极简：采用现代扁平矢量风格，线条粗细统一，圆角半径克制。去掉一切 3D 立体阴影、渐变发光、照片纹理和手绘草图噪点。
2. 纯白画布与浅色模块：整图底色必须为纯白（`#FFFFFF`），方便融入双栏论文版面与黑白打印。模块填充选用低饱和浅色（柔和淡蓝、淡灰、淡米、淡绿），只用中深饱和度的边框或强调色标出核心创新模块。
3. 单向清晰动线：整图只保留一条主阅读流向（从左到右，或从上到下）。不要把核心模块放正中同时向左右两边发散箭头，避免读者分不清输入和输出。
4. 文字只做身份标签：图内文字只用来标明模块名称、数据对象和简短变量名（每个标签控制在 2 至 5 个词）。绝不在方框里塞完整句子、长段落或成片推导公式；原理解释留给正文和图注。
5. 拒绝纯文字空框：在核心创新模块里，嵌入一个极简的局部视觉示意（例如三节点微型来源图、时间轴上的两条并行轨道、过滤器前后的候选数量变化），让审稿人一眼看出方法做了什么操作，而不只是看一堆抽象名词。
6. 严守证据边界：只画已经实现且有实验结果支撑的路径和组件。草案、未来扩展或已被消融证伪的分支不得画入主架构图。

## 三、图像模型 Prompt 模板（中英文双版）

使用前，先按本文已锁定的符号表和实现范围填满花括号占位符。建议同一设计稿用中英文模板各生成 2 至 3 组候选，挑选动线最清晰的一版作为矢量化底稿。

### 英文模板（面向原生英文训练权重较强的生图模型）

```text
Role: Scientific illustrator specializing in top-tier AI and systems venues (NeurIPS, ICML, IEEE TPAMI, Elsevier journals).

Task: Draw a clean, publication-ready schematic diagram based on the structured specification below.

Core Takeaway (one sentence):
{one_sentence_message}

Reading Flow & Layout:
- Direction: strictly Left-to-Right (or Top-to-Bottom), divided into {num_stages} clearly separated stages.
- Stage 1 (Input / Context): {stage_1_elements}
- Stage 2 (Core Mechanism with Mini Visual Inset): {stage_2_elements_and_mini_diagram}
- Stage 3 (Output / Verification): {stage_3_elements}

Visual Style Constraints:
- Flat 2D vector illustration aesthetic with crisp, uniform thin lines and generous whitespace.
- Pure solid white background (#FFFFFF) with no grid, texture, or drop shadows.
- Soft, low-saturation pastel fills for module containers; use one muted accent color strictly to highlight the proposed novel component.
- Clean geometric icons or tiny inline diagrams (e.g., 3-node graph, timeline bar, filter gate) to convey mechanism visually rather than relying on text boxes.

Text & Labeling Constraints:
- Render short English labels only (2 to 4 words per label) matching this exact label list: {exact_label_list}.
- Use clean sans-serif typography.
- Never write full sentences, explanatory paragraphs, or multi-line equations inside boxes.
- Do not include unimplemented modules or draft footnotes.

Strict Prohibitions:
- No 3D effects, no glossy gradients, no photorealistic objects, no hand-drawn sketch lines, no cluttered crossing arrows, no illegible or garbled characters.
```

### 中文模板（用于构图讨论或中文语义理解更稳的生图模型）

```text
角色：你是熟悉顶刊与顶会学术审美的科研插图设计师，擅长把复杂系统机制转化为极简、严谨的扁平矢量结构图。

任务：根据下方给定的结构化说明，绘制一张用于论文主文的示意图（图内标注文字使用简短英文标签，便于直接用于英文稿件或统一术语）。

核心信息（一句话）：
{一句话核心结论}

布局与流向：
- 严格采用单一方向阅读动线（从左到右），共分 {阶段数} 个清晰区块，区块之间留足空白。
- 第一区块（输入与真实实例）：{输入内容或时间轴实例}
- 第二区块（核心机制与局部图解）：{核心组件名称，以及需要画出的微型机制图，如小图结构、双路径汇聚或过滤前后对比}
- 第三区块（输出与结果）：{输出结果}

视觉规范：
- 扁平化二维矢量风格，线条粗细一致，边界对齐工整，留白充足。
- 背景纯白，无任何底纹、网格或阴影装饰。
- 配色克制，采用柔和浅色底块区分功能域，仅用一种稳重强调色突出本文核心模块，避开高饱和刺眼撞色。
- 用极简几何图标或微型示意图表达原理，不要把整张图画成密密麻麻的文字方框。

文字规范：
- 严格只绘制以下简短英文标签，不自行发明多余标签：{精确标签清单}。
- 使用干净的无衬线字体，禁止在框内写长句、解释段落、长公式或“待验证”灰字注释。

禁止项：
- 禁止 3D 立体效果、渐变反光、写实照片风、潦草手绘线、交叉混乱的双向箭头和模糊乱码文字。
```

## 四、生成后的四步定稿流程

1. 逻辑核对：遮住文字只看箭头与色块，确认输入到输出的流向与正文算法流程一致，没有画出未验证的分支。
2. 矢量化重建：在 Figma、Draw.io 或 Inkscape 中按草稿构图重新排布矢量元素，导入与数据图完全一致的色义配色和无衬线字体。
3. 符号与标签审计：把图内每个变量名、方法简称逐一与正文符号表、算法伪代码核对（例如统一使用 $p_{\text{struct}}$，杜绝出现未定义的 $p_{\mathrm{life}}$）。
4. 栏宽试排：按双栏约 7.0 英寸宽度导出 PDF，嵌入测试页面后放大到 100% 印刷比例检查最小字号与线条清晰度。
