<p align="center">
  <img src="https://img.shields.io/badge/dynamic/json?color=brightgreen&label=%F0%9F%93%9A%20Papers&query=count&url=https%3A%2F%2Fapi.count.com%2Fv1" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-brightgreen?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-blue?style=flat-square" alt="PRs Welcome">
</p>

# 📚 Awesome LLM Efficiency & Multimodal Surveys

> 一份高质量、持续更新的**大语言模型（LLM）效率优化**与**多模态大模型**综述导航。  
> 按**通用综述**与**领域特化**两大类别组织，每篇论文附带核心分类方式、覆盖方向、关键洞察及代码资源，便于研究者快速定位。

---

## 📖 目录

- [001 通用综述 (General Surveys)](#001-general-surveys)
- [002 领域特化综述 (Domain-Specific)](#002-domain-specific)
  - [VLLM (视觉大语言模型)](#vllm)

---

## 001-General-Surveys

> **说明**：本部分聚焦 LLM 效率优化的通用方法，涵盖模型压缩、高效架构、推理训练加速等。

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | **Towards Efficient Language Giants: A Comprehensive Survey on Structural Optimizations and Compression Techniques for Large Language Models** | ⭐⭐⭐⭐ | *Lee et al., Neural Networks, 2026* <br> `IF=6.3` | `高效模块设计` + `模型压缩` 双维度 | 混合方案（KD+量化、剪枝+量化）是突破单一技术瓶颈的关键；需根据场景（长上下文/边缘/高精度）选择不同技术组合。 |
| 2 | **Efficient Large Language Models: A Survey** | ⭐⭐⭐ | *Wan et al., arXiv, 2023 (持续更新)* | `模型中心` / `数据中心` / `框架中心` | 算法-硬件-框架协同设计是进一步提升 LLM 效率的关键，单一维度优化已接近瓶颈。 |

> 点击 ▶ 展开查看每篇论文的详细覆盖方向与资源。

<details>
<summary><b>📄 展开详情</b></summary>

<br>

### 1. Towards Efficient Language Giants (2026)
[![Paper](https://img.shields.io/badge/Neural_Networks-2026-blue)]()

- **覆盖子方向**：
  - `高效模块设计`：归一化（LayerNorm/RMSNorm/Dynamic Tanh）、位置编码（RoPE/YaRN/CoPE）、注意力（MQA/GQA/线性注意力/低秩注意力）、FFN（GLU/MoE）
  - `量化`：PTQ（GPTQ, AWQ, QuIP#, AQLM, LeanQuant）、QAT（LLM-QAT, EfficientQAT, BitNet, 1.58 Bits, OneBit, STBLLM）
  - `剪枝`：结构化（SliceGPT, LLM-Pruner, FASP, SlimLLM）、非结构化（Wanda, SparseLLM, OPTISHEAR）、激活剪枝（SCAP, ProSparse, SEAP, R-Sparse, Probe Pruning）
  - `知识蒸馏`：白盒（MiniLLM, GKD, DistiLLM, DSKD, BitDistiller）、黑盒（Distilling Step-by-Step, Lion, DiSCo）、灰盒（Proxy-KD）
  - `近似`：线性近似（SVD系列：ASVD, SVD-LLM, SoLA, SVD-LLM V2）、非线性近似（Softmax优化, ConSmax, LoLCATs）
  - `参数共享`：ALBERT, Basis Sharing, MobileLLM, MobileLLMA, Relaxed Recursive Transformers
- **核心数据洞察**：
  - 量化 3-4bit 下提供 50-76% 内存节约且精度损失 <3.8%
  - 剪枝的 FLOPs 减少难转化为实际加速（仅 1.14-1.36x）
  - KD 可实现 80-88% 压缩，部分场景精度不降反升
- **附带资源**：
  - 无公开GitHub库，但**表4**提供跨技术综合对比（内存/FLOPs/加速比/精度损失），极具参考价值。
  - 参考文献覆盖至2025-2026年。

### 2. Efficient Large Language Models: A Survey (2023)
[![arXiv](https://img.shields.io/badge/arXiv-2312.03863-b31b1b.svg)](https://arxiv.org/abs/2312.03863)
[![GitHub](https://img.shields.io/badge/GitHub-持续更新-181717?logo=github)](https://github.com/AIoT-MLSys-Lab/Efficient-LLMs-Survey)

- **覆盖子方向**：
  - `模型压缩`：量化（GPTQ, AWQ, SmoothQuant）、剪枝（SparseGPT, Wanda）、蒸馏、低秩分解（LoRA, QLoRA）
  - `高效架构`：高效注意力（GQA, MQA, FlashAttention）、MoE（Mixtral, DeepSpeed-MoE）、替代架构（Mamba, RWKV）
  - `推理优化`：KV Cache 管理（PagedAttention, StreamingLLM）、投机解码（Medusa, Eagle）、系统优化（vLLM, TensorRT-LLM）
  - `训练优化`：高效微调（LoRA 系列, IA3）、分布式训练（ZeRO, FSDP）、混合精度训练
- **附带资源**：配套持续更新的 [GitHub 仓库](https://github.com/AIoT-MLSys-Lab/Efficient-LLMs-Survey)。

<br>
</details>

---

## 002-Domain-Specific

### 🎨 VLLM (视觉大语言模型)

> **说明**：聚焦多模态（视觉-语言）大模型的训练效率、集成范式与优化策略。

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | **Efficiently Integrate Large Language Models with Visual Perception: A Survey from the Training Paradigm Perspective** | ⭐⭐⭐⭐ | *Ma et al., Information Fusion, 2025* <br> `IF=15.5` | `训练范式`：单阶段 / 两阶段 / 直接适配 | 直接适配在极低参数量下可接近全微调性能；轻量级LLM+LoRA是资源受限场景的有效路径。 |

<details>
<summary><b>📄 展开详情</b></summary>

<br>

### 1. Efficiently Integrate LLMs with Visual Perception (2025)
[![Paper](https://img.shields.io/badge/PDF-Information_Fusion_2025-blue?logo=googlescholar&logoColor=white)](https://arxiv.org/pdf/2502.01524)

- **覆盖子方向**：
  - `单阶段调优`：仅训练模态集成器（MI），利用LLM零样本/少样本能力；代表：Resampler、Q-Former、线性投影
  - `两阶段调优`：预训练+指令微调/RLHF；参数效率策略：仅训练MI、重参数化（LoRA/DoRA）、轻量级LLM（Phi/MobileLLaMA）
  - `直接适配`：跳过预训练，下游任务直接微调MI；常用瓶颈适配器、注意力适配器、度自适应前缀
  - `模态集成器`：外部（注意力抽象器、密集投影器、卷积抽象器、VSS抽象器）+ 内部（度自适应前缀、瓶颈适配器、注意力适配器、单模态线性适配器）
  - `训练策略`：多任务学习、指令微调、RLHF（含PPO）
  - `评测基准`：传统（VQAv2, GQA, COCO Caption, TextVQA）+ 先进（MME, MMBench, MM-Vet, POPE）
- **核心洞察补充**：引入微调阶段通常提升性能，但部分两阶段模型因数据或参数量不足反而不如更轻量的方案；未来需解决幻觉、细粒度视觉理解、泛化能力三大挑战。
- **附带资源**：
  - 论文 Table 8 总结了33个两阶段调优模型（LLaVA、MiniGPT4、mPLUG-Owl等）的代码可用性
  - 提供基于LST仓库的 Direct Adaptation 复现代码

<br>
</details>

---

<p align="center">
  <sub>⭐ 持续更新中 · 欢迎提交 Issue 或 PR 补充最新综述 ⭐</sub>
</p>
