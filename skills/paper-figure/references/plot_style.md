# 数据图统一风格系统与绘图规范

整篇论文的所有数据图必须共用一套视觉语法。不同章节的图若各自换配色、换字号、换坐标风格，审稿人会立刻联想到拼装稿件。

## 一、物理尺寸与版面规范

直接按目标期刊的实际印刷宽度创建画布，避免导出超大画布后在 LaTeX 中强行缩放导致字号失控。

| 规格类型 | Elsevier / IEEE 双栏 | ML 顶会（NeurIPS / ICLR / ICML） | 建议高宽比 |
|---|---|---|---|
| 单栏图 | 3.35–3.50 in（85–89 mm） | 2.65–3.25 in（视单双栏模板而定） | 0.65–0.85 |
| 通栏（双栏）图 | 6.80–7.10 in（173–180 mm） | 5.50–6.75 in（单栏正文约 5.5 in） | 0.35–0.55 |
| 多子图组合最大高度 | 不超过 8.5 in | 不超过 7.5 in | 保证图注留白 |

说明：具体期刊若当届调整版心宽度，以 `paper-format/references/venues.md` 和官方模板实测 `\textwidth` / `\columnwidth` 为准。

## 二、字体与字号阶梯

全篇统一选用一种清晰的无衬线字体（优先 Arial 或 Helvetica，Linux 无商业字体时可用 DejaVu Sans 或 Liberation Sans），并与架构图保持一致。

- 子图面板标号 `(a)`、`(b)`、`(c)`：9–10 pt，加粗，统一固定在每个子图左上角相同偏移位置。
- 坐标轴标题：8–9 pt，常规字重，带清晰单位或方向箭头（如 `LocF1 (higher is better)`）。
- 坐标轴刻度与图例文字：7–8 pt。
- 图内数据直标与样本量标注（如 `n=50`）：6.5–7.5 pt，任何文字在印刷终尺寸下严禁低于 6 pt。

## 三、色盲友好配色与全篇色义锁定

推荐使用 Okabe-Ito 改进色板，兼顾红绿色盲可读性与灰度打印对比度：

| 槽位 | 名称 | Hex | 推荐绑定语义（示例，按项目锁定后全篇不变） |
|---|---|---|---|
| C1 | 深蓝（Deep Blue） | `#0072B2` | 本文最终方法（Primary / Ours） |
| C2 | 朱橙（Vermilion） | `#D55E00` | 最强基线或核心对照风险项 |
| C3 | 蓝绿（Bluish Green） | `#009E73` | 第二类证据通道或对照组 B |
| C4 | 紫红（Reddish Purple） | `#CC79A7` | 消融变体或结构先验分支 |
| C5 | 琥珀黄（Orange/Amber） | `#E69F00` | 警告边界或次要对比（避免用于浅色细线） |
| C6 | 浅天蓝（Sky Blue） | `#56B4E9` | 辅助背景组或轻权重对比 |
| N1 | 深炭灰（Charcoal） | `#333333` | 坐标轴、零参考线、总计或基准线 |
| N2 | 中灰（Mid Gray） | `#8C8C8C` | 次要参考、网格线、未强调的旧对照 |

色义锁定铁律：
1. 建立项目级色义表，例如深蓝全篇只表示本文最终方法，不再挪去表示某个检索数 $k$ 或某种上下文可见条件。
2. 当某张图展示的是“曝光条件、检索预算或错误构成”而非“方法对比”时，使用形状（圆点、方块、三角）、线型（实线、虚线、点划线）、填充纹理（斜线）或中性灰阶，避免抢占方法色槽位。
3. 小样本类别或含不确定性的合并类别，可用浅色填充配斜纹（hatch）并在图注说明，不与大样本主项争夺视觉重心。

## 四、常见实验场景图表选型

| 展示目的 | 推荐图型 | 必带统计与视觉要素 | 应避免的陷阱 |
|---|---|---|---|
| 多方法跨类别对比 | 分组点图或横向条形图 | 样本量 $n$、95% 置信区间误差棒 | 柱顶数字重叠、把 $n=5$ 与 $n=50$ 无区间并列 |
| 配对方法增益与消融 | 横向森林图（Forest Plot） | 零垂直虚线、配对 bootstrap 区间、有利方向标注、配对单位 | 混排已弃用原型、画无误差棒的孤点 |
| 随预算/长度变化趋势 | 单轴折线图加阴影置信带 | 固定同一批样本追踪、横轴下方附注平均规模 | 跨组选择偏差连线、截断双 Y 轴 |
| 错因构成或事件占比 | 堆叠百分比条形图（100%） | 清晰入组规则、最大主因置底或前置、直标比例与分母 | 用饼图或把绝对数量与截断百分比叠在同一坐标 |
| 成本与精度权衡 | 散点图加帕累托前沿线 | 明确横轴开销单位（单会话 token 或延迟）、标注最优方向 | 只报总 token 账单不做单样本归一化 |

## 五、可复用 `matplotlib` 样式片段

将以下配置放入项目根目录的 `plot_style.py`，由每张图的绘图脚本统一导入：

```python
import matplotlib as mpl
import matplotlib.pyplot as plt

# 色盲友好色板（项目内按需绑定到固定方法名）
PALETTE = {
    "ours": "#0072B2",
    "baseline_a": "#D55E00",
    "baseline_b": "#009E73",
    "ablation": "#CC79A7",
    "accent": "#E69F00",
    "neutral_dark": "#333333",
    "neutral_mid": "#8C8C8C",
    "neutral_light": "#D9D9D9",
}

def apply_paper_style():
    mpl.rcParams.update({
        # 字体与矢量嵌入（确保 Illustrator / PDF 文本可编辑）
        "font.family": "sans-serif",
        "font.sans-serif": ["Arial", "Helvetica", "DejaVu Sans"],
        "pdf.fonttype": 42,
        "ps.fonttype": 42,
        "svg.fonttype": "none",

        # 字号阶梯（按印刷实尺寸设定）
        "font.size": 8.0,
        "axes.titlesize": 8.5,
        "axes.labelsize": 8.0,
        "xtick.labelsize": 7.5,
        "ytick.labelsize": 7.5,
        "legend.fontsize": 7.5,

        # 坐标轴与网格
        "axes.linewidth": 0.75,
        "axes.edgecolor": "#333333",
        "axes.spines.top": False,
        "axes.spines.right": False,
        "axes.grid": True,
        "axes.axisbelow": True,
        "grid.color": "#E5E5E5",
        "grid.linewidth": 0.5,
        "grid.linestyle": "-",

        # 线条与标记
        "lines.linewidth": 1.4,
        "lines.markersize": 4.5,
        "errorbar.capsize": 2.2,

        # 图例与导出边距
        "legend.frameon": False,
        "legend.handlelength": 1.6,
        "figure.dpi": 150,
        "savefig.dpi": 600,
        "savefig.bbox": "tight",
        "savefig.pad_inches": 0.04,
        "savefig.facecolor": "white",
    })

def save_figure(fig, stem_path):
    """同步导出矢量 PDF 与高分预览 PNG。"""
    fig.savefig(f"{stem_path}.pdf", format="pdf")
    fig.savefig(f"{stem_path}.png", format="png", dpi=600)
```

多面板对齐提示：使用 `constrained_layout=True` 或显式 `GridSpec` 控制间距，导出前打印各 `ax.get_position()` 核查同行子图的上下边界高度差和同列子图的左右对齐误差，确保视觉整齐。
