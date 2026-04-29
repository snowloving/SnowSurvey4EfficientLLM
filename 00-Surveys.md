<p align="center">
   <img src="https://img.shields.io/badge/Papers-8-critical?style=flat-square" alt="Paper Count">
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
| 2 | 🔥 **From Transformers to LLMs: A Systematic Survey of Efficiency Considerations in NLP** | 2025 | arXiv | `模型优化`：数据/设计/压缩/推理 + `LLM适配`：预训练/微调/Prompt/RAG | 312篇文献系统综述；揭示LLM全生命周期效率全景，含30+模型在13项基准的性能-价格Pareto分析 |
| 3 | 🔥 **Empowering LLMs to Edge Intelligence: A Survey of Edge Efficient LLMs and Techniques** | 2025 | Computer Science Review `IF=11.5` | `边缘层级`：SLM设计/模型压缩/推理优化/部署框架 | 首篇面向边缘部署的全栈综述；定义<4B为SLM，汇总30+轻量模型架构对比与边缘硬件实测性能 |

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
<br

### 2. From Transformers to LLMs: A Systematic Survey of Efficiency Considerations in NLP (2025)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[From Transformers to LLMs: A Systematic Survey of Efficiency Considerations in NLP]()

- **分类方式**：按 **模型优化**（数据策展/模型设计/模型压缩/动态推理）与 **LLM适配**（预训练/微调/Prompt工程/RAG）双阶段交叉组织，辅以效率度量（FLOPs/延迟/吞吐/碳排放/定价）
- **覆盖子方向**：
  - `数据策展` → 去重（D4/CCNet）、子集选择（Ask-LLM/SubLIME）、主动学习（AnchorAL/NoiseAL）、课程学习（Curri-DPO）
  - `模型设计` → 高效注意力（MQA/GQA/稀疏注意力/Linformer/FlashAttention）、MoE（Switch Transformer/Mixtral/DeepSeekMoE）、低秩近似（ASVD/FWSVD/Linformer）、参数共享（ALBERT/Universal Transformer/Basis Sharing）
  - `模型压缩` → 剪枝（结构化：LLM-Pruner/Sheared LLaMA；非结构化：SparseGPT/Wanda；上下文：DejaVu）、KD（白盒：MiniLLM/TED/GKD；黑盒：Distilling Step-by-Step/Lion）、量化（PTQ：GPTQ/AWQ/SmoothQuant/OmniQuant；QAT：BitNet/LLM-QAT/BinaryBERT）
  - `动态推理` → 早退（DeeBERT/CALM/BEExformer）、Token剪枝（SpAtten/LLMLingua/LazyLLM）、Token并行（推测解码/Speculative Sampling）
  - `LLM适配效率` → 预训练（MLM/RTD/CLM/PPT）、PEFT（LoRA/QLoRA/AdaLoRA/Adapter/BitFit/Prefix-tuning）、Prompt工程（Prompt Pruning/Soft Prompt Compression/CoT/Coconut/CoD）、RAG效率（Self-RAG/Adaptive-RAG/CRAG/RQ-RAG）
  - `效率度量` → 碳排（LLMCarbon/LLMCO2）、能耗（Lannelongue框架）、定价（$/1M tokens）、E2E响应时间、吞吐（tokens/s）
- **核心洞察补充**：训练GPT-4级模型碳排放可达约2000吨CO₂，相当于300次跨大西洋飞行；LoRA可将可训练参数减少至原1/10000；现代蒸馏技术实现Pareto改进——GPT-5 mini性能（63.9%）超越更大模型Claude 4 Sonnet（60.1%）且价格更低；开放权重模型（DeepSeek/Gemma/LLaMA/Mistral）正缩小与私有模型的差距；上下文窗口已从128K扩展至1M-10M tokens；CoD仅消耗CoT 7.6%的token量却维持同等性能
- **附带资源**：论文Table 3提供30+主流LLM在13项基准的详细性能对比，Table 4涵盖许可证、定价、延迟、吞吐等运营效率指标，Figure 22展示性能-价格Pareto前沿，Table 5汇总15+模型预训练的GPU小时、能耗与碳排放，极具选型参考价值
<br>


### 3. Empowering LLMs to Edge Intelligence: A Survey of Edge Efficient LLMs and Techniques (2025)
[![Paper](https://img.shields.io/badge/Journal-Comput.Sci.Rev'25-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=11.5-important)]()

[Empowering large language models to edge intelligence: A survey of edge efficient LLMs and techniques]()

- **分类方式**：按 **边缘部署全栈**（SLM设计→模型压缩→推理优化→部署框架）四阶段组织，覆盖从模型选型到实际落地的完整链路
- **覆盖子方向**：
  - `SLM设计` → 小变体（Qwen 0.5B-4B/Gemma 2B/InternLM 1.8B/TinyLlama 1.1B）、预训练SLM（MobileLLM/MobiLlama/OpenELM/SmoLLM/Phi系列）、压缩SLM（Gemini-Nano/Llama 3.2 1B-3B/Sheared LLaMA/MiniMA/Baby Llama）
  - `SLM架构对比` → 25+SLM的详细架构参数表（注意力类型/词表大小/归一化/位置编码/激活函数/层数/头数/隐藏维度/上下文长度）
  - `模型压缩` → 剪枝（结构化5粒度/非结构化/SparseGPT/Wanda）、KD（白盒MiniLLM/GKD/黑盒CoT-ICL-IF蒸馏）、量化（PTQ：GPTQ/AWQ/SpQR/AQLM/LLM.int8/SmoothQuant/Outlier Suppression+；QAT：LLM-QAT/EfficientQAT/EdgeQAT；二值化：PB-LLM/BiLLM/BitNet b1.58）、低秩分解（TensorGPT/LoSparse/LoRA）
  - `推理优化` → 推测解码（EAGLE/Medusa/Lookahead/LLMCad/SpecExec）、KV Cache压缩（FastGen/StreamingLLM/H2O/Scissorhands/KIVI/KVQuant/IntactKV）、早退（CALM/ConsistentEE/FREE/SkipDecode/LayerSkip）、内核优化（FlashAttention 1-2-3/FlashDecoding++/T-MAC）、内存卸载（FlexGen/PowerInfer/LLM in a flash/EdgeMoE）
  - `部署框架` → 端侧推理引擎（ExecTorch/TFLite/MNN/ncnn/LLMCad/PowerInfer-2/Transformer-Lite）、云边协同（Hybrid LLM/Tabi/Edge-LLM/FedAgg/动态Token级协同）、部署套件（MLC-LLM/llama.cpp/mllm/NanoLLM）
  - `边缘硬件实测` → Raspberry Pi 5/Jetson AGX Orin/Mac Mini上TinyLlama-1.1B和Phi-3-3.8B的吞吐与困惑度对比（FP16 vs INT4）
- **核心洞察补充**：定义SLM为<4B参数模型（基于Open LLM Leaderboard统计分布）；边缘部署面临四大矛盾（模型增长vs内存限制/计算需求vs算力受限/能耗vs电池供给/吞吐需求vs带宽有限）；深度>宽度的架构设计对亚B级模型更关键（MobileLLM验证）；量化可显著提升边缘吞吐（TinyLlama在Raspberry Pi 5上INT4达27.61 tokens/s vs FP16的22.85 tokens/s）；Apple Intelligence采用混合精度量化（平均3.7 bits/weight）+LoRA适配器的量产方案
- **附带资源**：论文Table 3提供25+SLM的完整架构参数对比表，Table 4列出三种典型边缘硬件规格，Table 5展示边缘设备上的实测吞吐与困惑度，Table 6对比7种代表性量化方法（均匀性/对称性/校准/混合精度），Table 10对比llama.cpp/MLC-LLM/mllm/NanoLLM四种部署套件的模型架构支持、硬件兼容性、量化支持等特性

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
| 1 | 🔥 **A Survey on Model Compression for Transformer-Based LLMs** | 2026 | IEEE TETCI `IF=11.8` | `压缩方法`：剪枝/量化/蒸馏/低秩分解 + `新视角`：KV Cache压缩/NAS | 首篇将KV Cache压缩与NAS纳入LLM模型压缩统一框架的综述；混合压缩是工业落地主流范式 |
| 2 | 🔥 **Survey on Knowledge Distillation for LLMs: Methods, Evaluation, and Application** | 2025 | ACM TIST `IF=6.5` | `KD范式`：白盒(Logits/Hint) + 黑盒(ICL/CoT/Instruction Following) + `鲁棒性评估` | 首次提出白盒/黑盒二分法用于LLM KD分类，清晰区分了可访问内部参数（白盒）和仅可访问API输出（黑盒）的两类方法；首篇从鲁棒性视角统一评估LLM蒸馏算法的综述；MiniLLM在GPT-2上对抗及OOD鲁棒性最优 |

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


### 1. A Survey on Model Compression for Transformer-Based LLMs (2026)
[![Paper](https://img.shields.io/badge/Journal-IEEE_TETCI'26-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=11.8-important)]()

[A Survey on Model Compression for Transformer-Based Large Language Models](https://ieeexplore.ieee.org/document/11408261)

- **分类方式**：按 **压缩技术类型**（剪枝/量化/知识蒸馏/低秩分解/KV Cache压缩/NAS）六大类组织，并进一步细分：
  - `剪枝` → 结构化（层级式/组件式）、非结构化（幅度/损失）、半结构化（N:M稀疏）
  - `量化` → QAT（BitNet系列/LLM-QAT/BitDistiller）、PTQ（仅权重/权重+激活）
  - `知识蒸馏` → 黑盒（CoT蒸馏/ICL蒸馏）、白盒（特征/响应/关系）
  - `低秩分解` → SVD变体（FWSVD/EoRA/ASVD）、张量分解（TensorGPT）
  - `KV Cache压缩` → 层级/头数/序列长度/特征维度四维度
  - `NAS` → One-Shot NAS/Zero-Shot NAS/硬件感知NAS
- **覆盖子方向**：
  - `结构化剪枝` → LLM-Pruner, LoSparse, Sheared LLaMA, SliceGPT, DISP-LLM, LoRAPrune, TransAct
  - `非结构化剪枝` → SparseGPT, Wanda, RIA, SPP
  - `半结构化剪枝` → AST, MaskLLM, 4:2稀疏模式
  - `QAT` → BitNet b1.58, LLM-QAT, BitDistiller, Efficient QAT, OneBit
  - `权重PTQ` → GPTQ, AWQ, OWQ, SpQR, SqueezeLLM, QLoRA, LoftQ
  - `权重+激活PTQ` → SmoothQuant, OmniQuant, QuaRot, ASER, MobileQuant
  - `黑盒KD` → CoT蒸馏（Magister/PaD/ELLM-MKD）、ICL蒸馏（SeCoKD/MEND/AICD）
  - `白盒KD` → 特征（TinyBERT/MINILMv2）、响应（MiniLLM/SWITCH）、关系（MGSKD）
  - `低秩分解` → FWSVD, EoRA, LPAF, MoDeGPT, ASVD, TensorGPT
  - `KV Cache` → Cross-Layer Attention, MLKV, GQA, HeadKV-R2, KVQuant, TokenSelect, KVMerger, GEAR, MatryoshkaKV
  - `NAS` → LLaMA-NAS, NAS-BERT, Puzzle, HAT
- **核心洞察补充**：结构化剪枝比通常不超过30%，过高会导致性能急剧退化；非结构化剪枝可在50%稀疏度下保持优良性能，但破坏模型结构难以硬件加速；QAT性能优于PTQ但训练成本更高；混合精度是处理离群值的最常用策略；混合压缩（如Apple的2-bit量化+8-bit KV Cache量化）是工业落地主流路径；Scaling Law在模型压缩中可能失效——权重压缩至1 bit、激活压缩至8 bit时性能骤降。
- **附带资源**：无公开GitHub库，但论文Table III提供了六大类压缩方法的压缩目标、微调需求、硬件兼容性、典型压缩比的一览对比表，Table I-II分别给出代表性剪枝和量化方法的实验数据，极具横向对比参考价值。
<br>


### 2. Survey on Knowledge Distillation for LLMs: Methods, Evaluation, and Application (2025)
[![Paper](https://img.shields.io/badge/Journal-ACM_TIST'25-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=6.5-important)]()

[Survey on Knowledge Distillation for Large Language Models: Methods, Evaluation, and Application]()

- **分类方式**：按 **KD范式**（白盒/黑盒）两大维度组织，并进一步按功能细分为方法、评估、应用三大板块
- **覆盖子方向**：
  - `白盒KD-基于Logits` → DistillBERT/TinyBERT/MobileBERT/MiniLM/PD/MixKD/ReAugKD/MetaDistil/AD-KD/MiniLLM/GKD/MiniMA/f-DISTILL
  - `白盒KD-基于Hint` → PKD/PKD-Last/PKD-Skip/XtremeDistil/TED/HomoDistil
  - `黑盒KD-ICL` → ICL蒸馏/Meta-ICL/In-Context Tuning/SeCoKD/MEND/AICD
  - `黑盒KD-CoT` → Distilling Step-by-Step/Symbolic KD/SCOTT/MCC-KD/Dialogue CoT/KRAD/PaD/S3
  - `黑盒KD-Instruction Following` → Self-Instruct/Alpaca/Vicuna/GPT4All/Lion/LaMini-LM/Personalized Distillation/UniversalNER
  - `多模态KD` → CoMD/VPD/Localized Symbolic KD
  - `鲁棒性评估` → 对抗鲁棒性（AdvGLUE/ANLI）+ OOD鲁棒性（Flipkart/DDXPlus），在GPT-2/OPT/LLaMA/LLaMA2上统一评估9种KD算法
- **核心洞察补充**：MiniLLM（反向KL散度+策略梯度优化）在GPT-2全系列上对抗及OOD鲁棒性最优；同蒸馏算法在不同模型架构上效果差异显著——GPT-2上MiniLLM最优，OPT上传统KD最优，LLaMA上SeqKD最优，LLaMA2上JS散度最优；白盒KD需大量GPU内存（教师前向传播特征），黑盒KD则依赖闭源API生成数据，存在成本与公平性挑战；MiniMA发现学生模型约为教师40%大小时蒸馏效果最优
- **附带资源**：论文Table 1系统汇总14种白盒KD方法的压缩率、评估任务及性能对比，Table 5对比8种黑盒KD方法的特点与数据集，Table 2-8提供GPT-2/OPT/LLaMA在多种KD算法下的对抗鲁棒性（ASR↓）与OOD鲁棒性（F1↑）完整实验数据，极具工程选型参考价值

<br>
</details>

---

<a id="infer-opt"></a>
### ⚡ 推理阶段优化
> `03-Inference-Optimization` | KV缓存压缩 · 投机解码 · FlashAttention · 系统级服务 · 文本压缩 · 硬件加速

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | 🔥 **Large Language Model Inference Acceleration: A Comprehensive Hardware Perspective** | 2025 | arXiv | `硬件平台`：CPU/GPU/FPGA/ASIC/PIM + `优化方法`：量化/稀疏/快速解码/算子优化/异构协同 | 首篇以tokens/s和tokens/J统一度量不同硬件平台LLM推理性能的综述；PIM/NDP能效比最高达46.66 tokens/J |

<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `KV-Cache-Compression`：PagedAttention, RadixAttention, KV缓存压缩
- `Speculative-Decoding`：Medusa, Eagle, Lookahead 等
- `FlashAttention`：FA1/2/3, 高效注意力内核
- `System-Level-Serving`：vLLM, TensorRT-LLM, SGLang, 调度优化
- `Text-Compression`：提示压缩, Prompt压缩

### 1. Large Language Model Inference Acceleration: A Comprehensive Hardware Perspective (2025)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[Large Language Model Inference Acceleration: A Comprehensive Hardware Perspective](https://dai.sjtu.edu.cn/project.html)

- **分类方式**：按 **硬件平台**（CPU/GPU/FPGA/ASIC/PIM-NDP）与 **软件优化方法**（量化/稀疏/快速解码/算子优化/异构协同/同构协同）双维度交叉组织，并首次以 tokens/s 和 tokens/J 统一量化对比
- **覆盖子方向**：
  - `量化` → 仅权重量化（GPTQ/AWQ/SpQR/T-MAC）、权重+激活量化（SmoothQuant/LLM.int8/Atom/QUIK）、KV Cache量化
  - `稀疏` → 权重稀疏（SparseGPT/Wanda/DejaVu/E-Sparse）、激活稀疏（Turbo Sparse/ProSparse/SoLA/R-Sparse）、注意力稀疏（StreamingLLM/H2O/Sparse Flash Attention）
  - `快速解码` → 推测解码（Medusa/EAGLE/Sequoia/Ouroboros/Kangaroo/Lookahead）、跳层（AdaInfer/LayerSkip/Mixture-of-Depths）
  - `算子优化` → 融合（FlashAttention/FlashDecoding++/TensorRT-LLM）、非线性近似（ConSmax/HAAN）、粗粒度处理（TCP/Gaudi2/Groq LPU）、存储优化（FlashFormer/KV Cache预取）
  - `异构协同` → CPU-GPU（PowerInfer/Twinpilot）、GPU-FPGA（GLITCHES）、PIM-NPU（NeuPIMs/IANUS）、PIM-CXL（CXL-PNM）
  - `硬件平台对比` → CPU: 3-50 tokens/s, 0.0057-2.38 tokens/J；GPU: 18-343.4 tokens/s, 0.06-0.86 tokens/J；FPGA: 3.61-450 tokens/s, 0.15-6.30 tokens/J；ASIC: 9.95-2700 tokens/s, 0.11-13.99 tokens/J；PIM/NDP: 10-1998 tokens/s, 0.14-46.66 tokens/J
- **核心洞察补充**：PIM/NDP在所有硬件平台中实现最高能效比（46.66 tokens/J），边缘CPU（3-6W）能效亦优于GPU；量化在GPU上可实现最高绝对推理速度（343.4 tokens/s），算子优化在ASIC上可达2700 tokens/s；大batch（bs=8）较小batch（bs=1）吞吐提升2.56-5.32倍，能效提升3.82-7.87倍；未来三大趋势为多模态、推理时计算、更高能效，边缘芯片需达到>10 tokens/J以支持100-1000Hz实时控制
- **附带资源**：[github仓库](https://github.com/Kimho666/LLM_Hardware_Survey)；论文图13-14提供bs=1和bs=8下各平台功耗-吞吐散点图，图18直观展示当前边缘AI与未来需求的1-2个数量级差距，极具系统设计参考价值

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
| 2 | 🔥 **A Survey of Token Compression for Efficient Multimodal LLMs** | 2026 | TMLR | `模态驱动`：图像 / 视频 / 音频 + `机制驱动`：Transformation/Similarity/Attention/Query | 首篇MLLM长上下文Token压缩系统综述；Token压缩与模型压缩在削减FLOPs上具有正交互补性 |

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
