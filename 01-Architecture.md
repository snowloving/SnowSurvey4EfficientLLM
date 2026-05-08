<p align="center">
  <img src="https://img.shields.io/badge/Papers-8-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 🏗️ Efficient Architecture of LLM

> **涵盖领域**: 高效注意力机制 · 稀疏专家架构(MoE) · Transformer替代架构(SSM/Linear Attention/ Hybrid)
> **核心目标**: 从架构层面降低Transformer的二次复杂度O(N²)和Feed-Forward Network内存带宽瓶颈

---

## 📖 目录

- [📊 本领域综述论文](#-survey)
- [🔥 本领域经典论文](#-important)
- [📄 论文清单](#-list)


---

<a id="survey"></a>
## 📊 本领域综述论文

> **说明**: 本领域综述专注于架构级效率优化，覆盖高效注意力、MoE稀疏激活、SSM/线性注意力等替代架构方向。（这个方向没有专有综述）

<!-- 
| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | **A Comprehensive Survey on Efficiency Optimization in LLMs: From Architecture Design to Synergistic Acceleration** | 2025 | KBS | `高效注意力` / `稀疏MoE` / `Transformer替代` 三类 | 首次将架构效率置于全生命周期优化框架，强调MoE+线性注意力的协同加速效应 |
---
-->

<a id="important"></a>
## 🔥 本领域经典论文

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Paper-arXiv'19-b31b1b) <br>[Fast Transformer Decoding: One Write-Head is All You Need](https://arxiv.org/abs/1911.02150) <br> Noam Shazeer | |[Paper](https://arxiv.org/pdf/1911.02150)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[GQA: Training Generalized Multi-Query Transformer Models from Multi-Head Checkpoints](https://arxiv.org/abs/2305.13245) <br> Joshua Ainslie, James Lee-Thorp, Michiel de Jong, Yury Zemlyanskiy, Federico Lebrón, Sumit Sanghai |<img width="1002" alt="image" src="https://arxiv.org/html/2305.13245v3/extracted/5314337/images/gmq_architecture.png"> |[Paper](https://arxiv.org/pdf/2305.13245)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model](https://arxiv.org/abs/2405.04434) <br> DeepSeek-AI |<img width="1002" alt="image" src="https://arxiv.org/html/2405.04434v5/x4.png"> |[Paper](https://arxiv.org/pdf/2405.04434)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'19-b31b1b) <br> [Generating Long Sequences with Sparse Transformers](https://arxiv.org/abs/1904.10509) <br> Rewon Child, Scott Gray, Alec Radford, Ilya Sutskever | |[Paper](https://arxiv.org/pdf/1904.10509)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'20-b31b1b) <br>[Longformer: The Long-Document Transformer](https://arxiv.org/abs/2004.05150) <br> Iz Beltagy, Matthew E. Peters, Arman Cohan | |[Paper](https://arxiv.org/pdf/2004.05150)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'20-purple) <br>[Big Bird: Transformers for Longer Sequences](https://arxiv.org/abs/2007.14062) <br> Manzil Zaheer, Guru Guruganesh, Avinava Dubey, Joshua Ainslie, Chris Alberti, Santiago Ontanon, Philip Pham, Anirudh Ravula, Qifan Wang, Li Yang, Amr Ahmed | |[Paper](https://arxiv.org/pdf/2007.14062)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'20-red) <br>[Reformer: The Efficient Transformer](https://arxiv.org/abs/2001.04451) <br> Nikita Kitaev, Łukasz Kaiser, Anselm Levskaya | |[Paper](https://arxiv.org/pdf/2001.04451)|
|![Publish](https://img.shields.io/badge/Conference-ICML'20-blue) <br>[Sparse Sinkhorn Attention](https://proceedings.mlr.press/v119/tay20a.html) <br> Yi Tay, Dara Bahri, Liu Yang, Donald Metzler, Da-Cheng Juan | |[Paper](https://proceedings.mlr.press/v119/tay20a/tay20a.pdf)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'20-purple) <br>[Fast Transformers with Clustered Attention](https://arxiv.org/abs/2007.04825) <br> Apoorv Vyas, Angelos Katharopoulos, François Fleuret | |[Paper](https://arxiv.org/pdf/2007.04825)|

---

<a id="list"></a>
## 📄 论文清单

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|


---

<p align="center">
  <sub>⭐ 持续更新中 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
