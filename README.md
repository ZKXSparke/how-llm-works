<div align="center">

# 图解大模型原理 · How LLMs Work

**把看不见的 AI 过程,放慢、画出来,讲给外行听。**

一个可交互的科普合集 —— 用真实例子和动画,一步步看清大语言模型背后到底发生了什么。

🔗 **在线体验:** https://zkxsparke.github.io/how-llm-works/

</div>

---

## 这是什么

AI 张口就能答你的问题,但它到底是**怎么知道答案的**?它在"读懂"文字,还是只是在算数字?

本仓库是一组**面向爱好者 / 外行**的交互式可视化科普。每一章用一个真实例子,带你**放慢节奏、一步步**看清大模型某个核心机制 —— 不堆术语,但也不糊弄:简化的地方都老实标注,真实原理、公式、工程做法一并给出。

- 🎯 面向**好奇的小白**,不是工程师
- 🐢 **逐步引导**,节奏由你掌控("下一步")
- 🧪 图表**由真实数据驱动**,可悬停 / 点击 / 拖动
- 🧱 每个 demo 都是**单个 HTML 文件,纯前端、可离线**打开
- 🔬 硬核仪表风视觉,但旁白是大白话;另设「实际情况」框补充真知识

## 章节

| # | 标题 | 讲什么 | 状态 |
|---|------|--------|------|
| **01** | [**慢读向量化**](慢读向量化.html) | 一个问题如何在**向量数据库**里找到答案 —— 分词 → 向量化 → 索引 → 检索 → 生成(即 **RAG**)。重点讲透:抽象的"意思"凭什么能变成确定的数字坐标。 | ✅ 已上线 |
| 02 | 为什么会有幻觉 | 当知识库里没有相关资料时,模型为何会"自信地编造",以及上下文如何影响幻觉率。 | 🚧 规划中 |
| 03 | Prompt → 答案 | 一段提示词进入模型后,如何一个 token 一个 token 地推出结果(注意力 / 下一词预测)。 | 🚧 规划中 |

> 合集会持续扩充。欢迎 Issue 提建议。

---

## 第 01 章《慢读向量化》

用一篇真实的**杭州西湖**短文当知识库,提一个问题(「雷峰塔什么时候倒掉、又什么时候重建?」),完整演示一个 RAG 问答系统是怎么找到并给出答案的。

**12 屏,你会依次看到:**

`导言` → `原文·知识库` → `分块` → `分词` → 向量化四步(`分布假说` · `猜词游戏` · `维度热力图` · `钉成确定坐标`)→ `入库索引` → `提问向量化` → `检索` → `生成答案`

**亮点**

- **把"意思变数字"讲透**:从分布假说("一个词的意思藏在它常和谁一起出现里")、自监督"猜词游戏"训练,到几百维"打分轴"、再到余弦相似度公式 —— 回答"为什么抽象的意思能变成一个确定坐标"。
- **数据驱动的可视化**:共现强度决定连线长短、向量分量决定热力深浅、2D 距离实时算相似度并排序。
- **可玩的检索**:在"意思地图"上**拖动问题点**,排名实时重排 —— 亲手感受"离得越近 = 意思越像"。
- **诚实**:为了画得出来用了 2D,真实嵌入是 1024+ 维 —— 界面里都老实标了;余弦公式照给。

## 本地运行

无需构建、无需联网,直接打开即可:

```bash
# 方式一:双击 慢读向量化.html 用浏览器打开

# 方式二:起个本地服务(中文文件名更稳妥)
python -m http.server 8000
# 浏览器访问 http://localhost:8000/慢读向量化.html
```

## 技术

纯 `vanilla JS + 内联 SVG/Canvas + CSS`,**单文件、零依赖、可离线**。视觉设计借助 [Claude Design](https://claude.ai/design),工程实现借助 [Claude Code](https://www.claude.com/product/claude-code)。

## 数据与版权

- 知识库示例文本**改编自维基百科「西湖」条目**,依 **CC BY-SA** 使用。
- demo 中的向量分量、2D 坐标、相似度等数值为**示意数据**(界面已标注),用于教学演示;真实系统在高维空间用真实嵌入模型计算。
- 代码以 **MIT** 许可证开源(见 [LICENSE](LICENSE))。

## 关注作者 · Follow

由 **Sparker** 制作。四流边缘瞎拍爱好者 · 菜鸟手残游戏玩家 🙂

在**小红书**找到我 —— **Spark**(小红书号 `1675517590`),扫码关注:

<img src="assets/xhs-follow.png" alt="小红书 @Spark 关注二维码" width="280">

---

<div align="center">

### How LLMs Work — Visual, Slow, For Everyone

Interactive visual explainers of what really happens inside large language models.
**Chapter 01 · "Slow-Read Embedding"** walks through the full RAG pipeline — tokenization → embedding → indexing → retrieval → generation — on a real Wikipedia passage, and answers the hard question: *why can an abstract "meaning" become a definite numerical coordinate?*

Single self-contained HTML, no build, works offline. Chinese UI.
**Live:** https://zkxsparke.github.io/how-llm-works/

</div>
