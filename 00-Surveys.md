<p align="center">
   <img src="https://img.shields.io/badge/Papers-2-orange?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-brightgreen?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-blue?style=flat-square" alt="PRs Welcome">
</p>

# 📚 Awesome-Efficient-LLM-Surveys

> 一份高质量、持续更新的**大语言模型（LLM）效率优化**综述导航。  
> 按**通用综述**与**领域特化**两大类别组织，每篇论文附带核心分类方式、覆盖方向、关键洞察及代码资源，便于研究者快速定位。

---

## 📖 目录

- [001 通用综述 (General Surveys)](#001-general-surveys)
- [002 领域特化综述 (Domain-Specific)](#002-domain-specific)
  - [架构级优化 (Architecture Optimization)](#arch-opt)
  - [模型压缩 (Model Compression)](#model-compress)
  - [推理阶段优化 (Inference Optimization)](#infer-opt)
  - [训练阶段优化 (Training Optimization)](#train-opt)
  - [路由与级联 (Routing and Cascade)](#routing-cascade)
  - [多模态 (Multimodal)](#multimodal)
---

## 001-General-Surveys

> **说明**：本部分聚焦 LLM 效率优化的通用方法，涵盖模型压缩、高效架构、推理训练加速等。


| # | 论文标题 | 评级 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|:----:|------|-------------|--------------|
| 1 | **Towards Efficient Language Giants** | 3.5 | 2026 | Neural Networks `IF=6.3` | `高效模块设计` ↔ `模型压缩` 双维度 | 混合方案（KD+量化/剪枝+量化）是突破单一技术瓶颈的关键 |
| 2 | **Efficient Large Language Models: A Survey** | 3 | 2023 | arXiv (持续更新) | `数据中心` · `模型中心` · `框架中心` | 算法-硬件-框架协同设计是进一步提效的关键 |
| 3 | *待添加* | — | — | — | — | — |

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

> **说明**：按细分技术方向组织的领域综述，每个方向聚焦一类特定优化技术或应用场景。

---

<a id="arch-opt"></a>
### 🏗️ 架构级优化
> `01-Architecture-Optimization` | 注意力机制 · FFN优化 · 替代架构 · MoE · 推理模型优化

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | *待添加* | — | — | `注意力机制` / `替代架构` / `MoE` 等 | — |

<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `Attention-Mechanisms`：GQA, MQA, Sliding Window 等高效注意力
- `FFN-Optimization`：SwiGLU, Parallel FFN 等
- `Alternative-Architectures`：Mamba, RWKV, Hyena 等非Transformer架构
- `Mixture-of-Experts`：MoE路由、负载均衡
- `Reasoning-Model-Optimization`：CoT, ToT, 长推理链效率优化

<br>
</details>

---

<a id="model-compress"></a>
### 📦 模型压缩
> `02-Model-Compression` | 量化 · 剪枝 · 知识蒸馏 · 低秩分解 · NAS

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | *待添加* | — | — | `量化` / `剪枝` / `蒸馏` / `低秩分解` 等 | — |

<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `Quantization`：GPTQ, AWQ, SmoothQuant, LLM.int8() 等
- `Pruning-Sparsity`：SparseGPT, Wanda, 半结构化稀疏等
- `Knowledge-Distillation`：MiniLLM, GKD, 上下文蒸馏等
- `Low-Rank-Decomposition`：LoRA及其变体, SVD等
- `Neural-Architecture-Search`：(可选) LLM专用NAS

<br>
</details>

---

<a id="infer-opt"></a>
### ⚡ 推理阶段优化
> `03-Inference-Optimization` | KV缓存压缩 · 投机解码 · FlashAttention · 系统级服务 · 文本压缩

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | *待添加* | — | — | `KV-Cache` / `投机解码` / `FlashAttention` / `系统服务` 等 | — |

<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `KV-Cache-Compression`：PagedAttention, RadixAttention, KV缓存压缩
- `Speculative-Decoding`：Medusa, Eagle, Lookahead 等
- `FlashAttention`：FA1/2/3, 高效注意力内核
- `System-Level-Serving`：vLLM, TensorRT-LLM, SGLang, 调度优化
- `Text-Compression`：提示压缩, Prompt压缩

<br>
</details>

---

<a id="train-opt"></a>
### 🏋️ 训练阶段优化
> `04-Training-Optimization` | 高效预训练 · 高效微调

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | *待添加* | — | — | `高效预训练` / `高效微调` 等 | — |

<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `Efficient-Pretraining`：数据筛选, 模型并行, MeZO等
- `Efficient-Finetuning`：LoRA, Prefix Tuning, P-Tuning, QLoRA等

<br>
</details>

---

<a id="routing-cascade"></a>
### 🔀 路由与级联
> `05-Routing-and-Cascade` | 模型路由 · 级联早期退出

| # | 论文标题 | 评级 | 出处 | 分类视角 | 一句话核心洞察 |
|---|---------|:----:|------|----------|----------------|
| 1 | *待添加* | — | — | `模型路由` / `级联退出` 等 | — |

<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `Model-Routing`：选择最佳模型（Router）
- `Cascade-Exit`：级联早期退出, LoRAExit等

<br>
</details>

---

<a id="multimodal"></a>
### 🎨 多模态 (Multimodal)
> `06-Multimodal` | 视觉-语言大模型训练效率与集成范式

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
