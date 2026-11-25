# 去 AI 味清洗清单与术语符号映射模板

本文件用于阶段门 G6 的语言自然度自查，同时提供术语表与内部代号映射表模板。原则是以准确、平实、证据边界清晰的学术表达替代套话和装饰辞藻，绝不为了换词而破坏原意。

## 一、英文学术写作常见 AI 痕迹与改法

### 1. 高频浮夸词与空洞动词
大模型在英文论文中常堆砌华丽但缺乏技术指向的词汇。出现以下词汇时，先检查上下文是否真有不可替代的技术含义，若无则换回平实常用词：

| 常见 AI 高频词 | 建议平实替换（按语境选） |
|---|---|
| `delve into`, `scrutinize`, `unveil`, `elucidate` | `examine`, `analyze`, `investigate`, `show`, `explain` |
| `leverage`, `harness`, `utilize`（过度泛用） | `use`, `apply`, `adopt`, `exploit`（仅用于利用特性） |
| `bolster`, `underscore`, `accentuate`, `amplify` | `support`, `highlight`, `confirm`, `increase` |
| `pivotal`, `paramount`, `profound`, `intricate`, `nuanced` | `key`, `important`, `complex`, `subtle`（或直接给出具体表现） |
| `foster`, `cultivate`, `nurture`, `galvanize` | `encourage`, `enable`, `improve`, `drive` |
| `tapestry`, `landscape`, `paradigm shift`, `testament` | 直接写具体领域、现状、变化或证据 |
| `ameliorate`, `alleviate`, `rectify`, `mitigate`（连续泛用） | `reduce`, `fix`, `correct`, `limit` |
| `demonstrate`, `showcase`, `depict`（尤其在图注表题中） | `show`, `compare`, `present`, `report` |

### 2. 机械句式与结构癖好
- 冗余开场短语：删去 `It is worth noting that`、`First and foremost`、`In today's rapidly evolving landscape`、`Needless to say`，直接进入主语和谓语。
- 否定式平行套话：避免高频使用 `It is not merely X, but rather Y` 或 `not only ... but also ...` 来制造拔高感，直接说清它是什么以及边界在哪里。
- 空洞的句尾分词总结：警惕 `, thereby highlighting the importance of ...`、`, paving the way for ...`、`, underscoring its vast potential` 这类无新信息的尾巴，直接删掉或换成具体后果。
- 破折号与格式滥用：正文中尽量少用长破折号插入解释，改用逗号、括号或拆成两句。英文顶会正文严禁滥用 `\textbf{}`、`\emph{}` 和引号来强行标重点，也不要把本该连贯论证的段落写成 `\begin{itemize}` 清单。
- 方法名所有格：避免写 `HybridAudit's performance` 或 `Mem0's history table`，改为 `the performance of HybridAudit` 或 `the history table of mem0`。

## 二、中文学术写作常见 AI 痕迹与改法

### 1. 情绪渲染词与商业/公文腔
- 清理渲染词：去掉“毋庸置疑”“颠覆性”“范式转移”“痛点”“切中要害”“令人惊叹”“不可磨灭”“深刻揭示”“本质上”等词，改用“针对上述问题”“实验表明”“在某条件下提升多少”。
- 避免陈旧公文腔：现代中文学术写作应平实准确，不要无故将“旨在”改成“拟”，将“是”改成“系”，或堆砌文言虚词。
- 杜绝虚高贴帽：不要在没有理论模型和经典引文支撑的情况下，反复穿插“立足某某融合视角”“从宏观范式审视”等空帽子。

### 2. 翻译腔与节奏僵硬
- 拆分长定语：把“一个基于多源异构证据并在运行时保持低开销的自适应记忆审计框架”拆成短句，先说是什么框架，再说依赖什么证据和约束。
- 压缩被动语态：中文少用连续的“被”字句，例如把“旧事实被系统保留且被检索器返回”改为“系统保留旧事实，检索器随后将其返回”。
- 打破机械结构：删去不必要的“首先……其次……最后……”和强行凑齐的三段排比。句长应有起伏，长句解释因果条件，短句落定判断。
- 清除连环同款结尾：检查相关工作或实验分析的连续小节，避免每节末都套用“与上述聚焦……不同，本文……”这一同一模板。

## 三、结构层“多 Agent 拼装味”自查项

即使单句通顺，整篇稿件仍可能暴露拼接痕迹，合龙时逐项排查：
1. 同一组数字是否在不同章节以几乎相同的句式出现超过三次。
2. 是否有两节分别照着同一份实验笔记或源码调研各自重写了一遍细节。
3. 章节末尾是否残留格式不统一的局部引用清单。
4. 是否夹杂按开发周次追忆的编年史叙述（如“初版我们尝试了 X，后来在某周发现过拟合又改成 Y”）。
5. 同一条实验局限或待补说明是否像粘贴模板一样在全文重复出现。

## 四、克制清洗的四步工作流

1. 标出症状：通读段落，只标记真正存在空洞渲染、翻译腔、逻辑跳跃或拼装重复的句子。
2. 判定必要性：如果原句已经清晰、准确、无明显机器味，直接判定“通过”并保留原句，禁止为了制造修改记录而换词。
3. 最小改动：改写问题句时，严禁改动任何数值、实验条件、假设边界和引用编号。
4. 朗读复核：默读改后整段，确认句间靠因果与语义推进，而不是靠机械过渡词硬连。

## 五、术语表、符号表与内部代号映射表模板

在每个论文项目根目录维护 `glossary_and_symbols.md`，起草与制图全过程以此为准：

```markdown
# 术语、符号与代号映射表

## 1. 内部代号清洗表（左列严禁出现在正文、图表与附录）
| 内部代号 / 代码字段 | 正式学术名称（中文） | 正式学术名称（英文） | 处理规则 |
|---|---|---|---|
| `W10` / `W11` | 观测通道纠偏协议 | Runtime Observation Protocol | 禁提周次 |
| `ours_v2` | 规则含关键词先验旧版（仅消融用） | Heuristic-Prior Variant (Deprecated) | 移出主表，仅消融简述 |
| `hybrid_audit_v1` | HybridAudit | HybridAudit | 全文统一简称 |
| `delete_retrieved_on_fail` | 失败即删基线 | Delete-on-Failure Baseline | 改用语义名 |
| `shopping_task_002` | 个别空响应剔除样本 | Excluded Empty-Response Case | 仅报总数，不列样例文件名 |
| `sha256("w11-split-v1:...")` | 确定性哈希切分 | Deterministic Hash Split | 细节放代码仓库与复现说明 |

## 2. 核心数学符号表（与图表、算法伪代码 100% 同步）
| 符号 | 含义 | 首次出现位置 | 禁用异体 |
|---|---|---|---|
| $p_{\text{struct}}$ | 生命周期结构先验分数 | §4.3 | 禁用 $p_{\mathrm{life}}$ |
| $\tau_{\text{loc}}$ | 定位判定阈值 | §4.4 | 禁用裸写 `tau` |

## 3. 数值精度与缩写规则
- 定位/分类指标（F1、Precision、Recall）：统一三位小数（如 `0.786`）。
- 比例与覆盖率（%）：统一一位小数（如 `80.0%`）。
- 大于等于 1000 的样本或记录计数：统一加千分位逗号（如 `1,697`）。
- 常见领域缩写（如 LLM、API）按惯例保留；自定义缩写首次出现给出全称。
```
