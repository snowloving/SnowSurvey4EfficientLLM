<p align="center">
   <img src="https://img.shields.io/badge/Papers-3-critical?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 📚 Awesome-Efficient-LLM-Surveys

> 一份高质量、持续更新的**大语言模型（LLM）效率优化**综述导航。  
> 按**通用综述**与**特定领域**两大类别组织，每篇论文附带核心分类方式、覆盖方向、关键洞察及代码资源，便于研究者快速定位。

---

## 📖 目录

- [001 通用综述 (General Surveys)](#001-general-surveys)
- [002 特定领域 (Domain-Specific)](#002-domain-specific)
  - [架构级优化 (Architecture Optimization)](#arch-opt)
  - [模型压缩 (Model Compression)](#model-compress)
  - [推理阶段优化 (Inference Optimization)](#infer-opt)
  - [训练阶段优化 (Training Optimization)](#train-opt)
  - [路由与级联 (Routing and Cascade)](#routing-cascade)
  - [多模态 (Multimodal)](#multimodal)
---

## 001-General-Surveys

> **说明**：本部分聚焦 LLM 效率优化的通用方法，涵盖模型压缩、高效架构、推理训练加速等。
> 
> **评级说明**：`🏆` = 必读经典 · `🔥` = 高质量综述 · `📖` = 值得翻阅
> 
| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | 🔥 **Towards Efficient Language Giants** | 2026 | Neural Networks `IF=6.3` | `高效模块设计` + `模型压缩` 双维度 | 混合方案（KD+量化/剪枝+量化）是突破单一技术瓶颈的关键 |
| 2 | *待添加* | — | — | — | — |

<details>
<summary><b>📄 展开详情</b></summary>

<br>

### 1. Towards Efficient Language Giants (2026)
[![Paper](https://img.shields.io/badge/Journal-Neural_Networks'26-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=6.3-important)]()

[Towards efficient language giants: A comprehensive survey on structural optimizations and compression techniques for large language models](https://arxiv.org/pdf/2312.03863)

- **分类方式**：按 **高效模块设计**（MHA/FFN/normalization/PE）+ **模型压缩**（量化/剪枝/KD/近似/参数共享）双维度组织
- **覆盖子方向**：
   - `高效模块设计` → 归一化（LayerNorm/RMSNorm/Dynamic Tanh）、位置编码（RoPE/YaRN/CoPE）、注意力（MQA/GQA/线性注意力/低秩注意力）、FFN（GLU/MoE）
   - `量化` → PTQ（GPTQ, AWQ, QuIP#, AQLM, LeanQuant）、QAT（LLM-QAT, EfficientQAT, BitNet, 1.58 Bits, OneBit, STBLLM）
   - `剪枝` → 结构化（SliceGPT, LLM-Pruner, FASP, SlimLLM）、非结构化（Wanda, SparseLLM, OPTISHEAR）、激活剪枝（SCAP, ProSparse, SEAP, R-Sparse, Probe Pruning）
   - `知识蒸馏` → 白盒（MiniLLM, GKD, DistiLLM, DSKD, BitDistiller）、黑盒（Distilling Step-by-Step, Lion, DiSCo）、灰盒（Proxy-KD）
   - `近似` → 线性近似（SVD系列：ASVD, SVD-LLM, SoLA, SVD-LLM V2）、非线性近似（Softmax优化, ConSmax, LoLCATs）
   - `参数共享` → ALBERT, Basis Sharing, MobileLLM, MobileLLMA, Relaxed Recursive Transformers
- **核心结论/洞察**：量化、剪枝、KD占据不同的精度-效率空间——量化在3-4bit下提供50-76%内存节约且精度损失<3.8%；剪枝的FLOPs减少难转化为实际加速（1.14-1.36x）；KD可实现80-88%压缩且部分场景精度不降反升。混合方案（如KD+量化、剪枝+量化）是突破单一技术瓶颈的关键。场景化设计（长上下文/快速响应/边缘/高精度）应选择不同的技术组合。
- **附带资源**：无公开GitHub库，但表4提供了跨技术综合对比（内存/FLOPs/加速比/精度损失），极具参考价值。参考文献覆盖至2025-2026年。Benchmarks and datasets模块基础但很有用。

<br>
</details>
---

## 002-Domain-Specific

> **说明**：按细分技术方向组织的领域综述，每个方向聚焦一类特定优化技术或应用场景。

---

<a id="arch-opt"></a>
### 🏗️ 架构级优化
> `01-Architecture-Optimization` | 注意力机制 · FFN优化 · 替代架构 · MoE · 推理模型优化

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
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

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
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

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
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

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
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

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
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
> `06-Multimodal` | 视觉-语言大模型训练效率与集成范式 · Token压缩

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | 🔥 **Efficiently Integrate LLMs with Visual Perception** | 2025 | Information Fusion  `IF=15.5`| `训练范式`：单阶段 / 两阶段 / 直接适配 | 仅关注视觉模态，直接适配在极低参数量下可接近全微调性能；轻量级LLM+LoRA是资源受限场景的有效路径 |
| 2 | 🔥 **A Survey of Token Compression for Efficient Multimodal LLMs** | 2026 | TMLR | `模态驱动`：图像 / 视频 / 音频 + `机制驱动`：变换/相似度/注意力/查询 | 首篇MLLM长上下文Token压缩系统综述；Token压缩与模型压缩在削减FLOPs上具有正交互补性 |

<details>
<summary><b>📄 展开详情</b></summary>

<br>

### 1. Efficiently Integrate LLMs with Visual Perception (2026)
[![Paper](https://img.shields.io/badge/Journal-Information_Fusion'26-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=15.5-important)]()

[Efficiently integrate large language models with visual perception: a survey from the training paradigm perspective](https://arxiv.org/pdf/2502.01524)

- **覆盖子方向**：
  - `单阶段调优`：仅训练模态集成器（MI），利用LLM零样本/少样本能力；代表方法：Frozen、ClipCap、MAGMA、Flamingo、MAPL、ESPER、BLIP-2、AIM
  - `两阶段调优`：预训练+指令微调/RLHF；代表方法：Flamingo、LLaMA-Adapter、ESPER、LLaVA、MiniGPT4、BLIP-2、LLaVA 1.5、CogVLM-Chat、MobileVLM、LLaVA-Phi、TinyLLaVA、MobileVLM v2、VL-Mamba、Imp、Bunny
  - `直接适配`：跳过预训练，下游任务直接微调MI；代表方法：VL-Adapter、PromptFusion、LST、eP-ALM、LaVIN、VL-PET、MemVP
- **核心洞察补充**：引入微调阶段通常提升性能，但部分两阶段模型因数据或参数量不足反而不如更轻量的方案；未来需解决幻觉、细粒度视觉理解、泛化能力三大挑战。
- **附带资源**：
  - 无公开GitHub库，但论文 Table 8 总结了两阶段调优模型（LLaVA、MiniGPT4、mPLUG-Owl等）的代码可用性。
    
### 2. A Survey of Token Compression for Efficient Multimodal LLMs (2026)
[![Paper](https://img.shields.io/badge/Journal-TMLR'26-blue)]()
[![Paper](https://img.shields.io/badge/OpenReview-Reviewed-8A2BE2)](https://openreview.net/forum?id=G2od9JVHkE)

[A survey of token compression for efficient multimodal large language models](https://arxiv.org/pdf/2507.20198)

- **分类方式**：按 **主导数据模态**（图像/视频/音频）与 **内在压缩机制**（变换-based/相似度-based/注意力-based/查询-based）双维度交叉组织
- **覆盖子方向**：
  - `图像中心压缩` → 变换（Pixel Unshuffle/池化/卷积）、相似度（ToMe/FOLDER/DivPrune）、注意力（PruneVid/VisionZip/FastV/FitPrune/ZipVL）、查询（Q-Former系列/Token蒸馏/跨模态选择如SparseVLM/TRIM）
  - `视频中心压缩` → 变换（2D/3D池化与卷积）、相似度（Chat-UniVi/HoliTom/DyCoke/FrameFusion）、注意力（窗口注意力/流式LLM中的KV缓存）、查询（Token Turing Machines/BLIP-3-Video/LongVU）
  - `音频中心压缩` → 变换（Token堆叠/池化/时序卷积）、相似度（A-ToMe）、注意力（SpeechPrune）、查询（Q-Former/MMCE-Qformer/跨模态选择）
  - `定义边界`：明确区分Token压缩（输入/特征级剪枝合并）与注意力稀疏/高效注意力变体（计算图稀疏化但序列长度不变）
- **核心洞察补充**：Token压缩直接削减序列长度N，与模型压缩（量化/剪枝/蒸馏）在影响FLOPs的维度上呈正交关系（前者减少N，后者减少D），二者结合可获得叠加增益（如NVILA同时量化+Token压缩）；训练无关方法在保留10%视觉Token时近乎无损，但更强大模型（如Qwen2.5-VL）对压缩更敏感；显式依赖注意力分数的方法与FlashAttention等加速库不兼容。
- **附带资源**：
  - [GitHub仓库](https://github.com/cokeshao/Awesome-Multimodal-Token-Compression)，论文图3提供清晰分类法思维导图，表2-3对比训练无关方法在图像/视频理解基准上的性能，表4汇总常用多模态基准与评估指标，极具工程落地参考价值。
    
<br>
</details>

---

<p align="center">
  <sub>⭐ 持续更新中 · 欢迎提交 Issue 或 PR 补充最新综述 ⭐</sub>
</p>
