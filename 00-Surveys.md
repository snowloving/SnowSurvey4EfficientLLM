<p align="center">
   <img src="https://img.shields.io/badge/Papers-22-critical?style=flat-square" alt="Paper Count">
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
| 2 | 📖 **From Transformers to LLMs: A Systematic Survey of Efficiency Considerations in NLP** | 2025 | arXiv | `模型优化`：数据/设计/压缩/推理 + `LLM适配`：预训练/微调/Prompt/RAG | 312篇文献系统综述；揭示LLM全生命周期效率全景，含30+模型在13项基准的性能-价格Pareto分析 |
| 3 | 🏆 **Empowering LLMs to Edge Intelligence: A Survey of Edge Efficient LLMs and Techniques** | 2025 | Computer Science Review `IF=12.7` | `边缘层级`：SLM设计/模型压缩/推理优化/部署框架 | 首篇面向边缘部署的全栈综述；定义<4B为SLM，汇总30+轻量模型架构对比与边缘硬件实测性能 |
| 4 | 🏆 **A Comprehensive Overview of Large Language Models** | 2025 | ACM TIST `IF=6.6` | `LLM全景`：架构/预训练/微调/增效/多模态/智能体/应用/评估 | 覆盖面最广的LLM综述之一；系统汇总50+预训练LLM架构细节与训练配置，含7大类评估基准全览 |
| 5 | 🏆 **Towards Efficient Generative LLM Serving: A Survey from Algorithms to Systems** | 2025 | ACM Comput. Surv. `IF=28.0` | `算法创新`：解码/架构/压缩 + `系统优化`：量化/并行/内存/调度/内核 | 首篇覆盖LLM推理服务全栈的综述；系统对比10+框架的架构设计与优化取舍 |
| 6 | 📖 **A Survey on Efficient Inference for Large Language Models** | 2024 | arXiv | `三级优化`：数据层(压缩/编排) + 模型层(量化/稀疏/结构/蒸馏) + 系统层(引擎/服务/硬件) | 覆盖最广的LLM推理综述之一；独创数据-模型-系统三级分类，含PTQ/推测解码/服务框架的对比实验 |
| 7 | 🔥 **A Survey of Resource-Efficient LLM and Multimodal Foundation Models** | 2024 | arXiv | `模型覆盖`：LLM/ViT/扩散/多模态 + `优化层级`：架构/算法/系统 + `生命周期`：预训练/微调/推理/服务 | 覆盖四大基础模型的全栈效率综述；含联邦学习、边缘部署、LLMaaS等新兴话题 |
| 8 | 🏆 **Model Compression and Efficient Inference for Large Language Models: A Survey** | 2024 | arXiv | `五维压缩`：量化/剪枝/蒸馏/紧凑架构/动态网络 + `模型分层`：中型(≤1B) vs 真·大型(>1B) | 独创中型vs真·LLM分层方法论；LLM压缩两大核心：免重训练+通用性保持 |
| 9 | 🔥 **A Survey on Transformer Compression** | 2024 | arXiv | `四维压缩`：量化/蒸馏/剪枝/高效架构 + `新架构`：Mamba/RetNet/RWKV + `跨域`：NLP+CV | 同时覆盖语言与视觉Transformer压缩；系统对比Mamba/RetNet与Transformer复杂度与并行性 |

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

[From Transformers to LLMs: A Systematic Survey of Efficiency Considerations in NLP](https://arxiv.org/pdf/2406.16893)

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
[![Paper](https://img.shields.io/badge/IF=12.7-important)]()

[Empowering large language models to edge intelligence: A survey of edge efficient LLMs and techniques](https://www.sciencedirect.com/science/article/abs/pii/S1574013725000310)

- **分类方式**：按 **边缘部署全栈**（SLM设计→模型压缩→推理优化→部署框架）四阶段组织，覆盖从模型选型到实际落地的完整链路
- **覆盖子方向**：
    - `小语言模型（SLM）` → 大模型小变体（OPT, Qwen）、预训练SLM（Phi, Gemma, TinyLlama, MobileLLM, MiniCPM, SmolLM）、压缩SLM（Gemini-Nano, LaMini-LM, MiniLLM, Sheared LLaMA, Llama 3.2）
    - `模型压缩` → 剪枝（LLM-Pruner, SparseGPT, Wanda）、知识蒸馏（MiniLLM, MiniMA, CoT/ICL/Instruction蒸馏）、量化（GPTQ, AWQ, SmoothQuant, LLM-QAT, BitNet）、低秩分解（LoSparse, TensorGPT）
    - `推理优化` → 投机解码（SpecDecoding, EAGLE, Medusa, LLMCad）、KV Cache压缩（KVQuant, KIVI, H2O, StreamingLLM）、早退（CALM, SkipDecode, EE-LLM）、核优化（FlashAttention, FlashDecoding）、内存卸载（FlexGen, PowerInfer, LLM in a flash, EdgeMoE）
    - `部署框架` → 端侧引擎（ExecTorch, TFLite, PowerInfer, Transformer-Lite）、云边协同（Hybrid LLM, Tabi, Edge-LLM, FedAgg）、部署套件（MLC-LLM, llama.cpp, mlm, NanoLLM）
  - **核心结论/洞察**：SLM（<4B）是边缘部署的基础，设计趋势为更深更窄、共享参数、高质量合成数据；int4量化可提升边缘吞吐量20-40%；投机解码（EAGLE/Medusa）和KV Cache压缩是边缘推理优化的关键；云边协同（Hybrid LLM、Edge-LLM）是突破边缘资源限制的有效路径；SLM在幻觉、可解释性、个性化方面仍面临挑战。
  - **附带资源**：表2（27个SLM训练细节）、表3（26个SLM架构细节）、表5（边缘设备实测吞吐量与PPL）、表8-10（14个部署框架对比），是边缘LLM方向最全面的数据来源。
<br>


### 4. A Comprehensive Overview of Large Language Models (2025)
[![Paper](https://img.shields.io/badge/Journal-ACM_TIST'25-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=6.5-important)]()

[A Comprehensive Overview of Large Language Models](https://arxiv.org/pdf/2307.06435)

- **分类方式**：按 **LLM研发全生命周期**（背景→架构→预训练→微调→增效→多模态→智能体→评估）八大板块组织，提供自包含的全面概览
- **覆盖子方向**：
    - `预训练模型（50+）` → 通用型（GPT-3/4, PaLM, LLaMA, BLOOM, Gopher, Chinchilla, Gemini, Grok）、代码型（Codex, AlphaCode, StarCoder）、科学型（Galactica）、对话型（LaMDA）、金融型（BloombergGPT）
    - `微调模型（30+）` → 指令微调（T0, Flan, OPT-IML, Tk-Instruct）、人类对齐（RLHF, DPO, Constitutional AI, LIMA）、持续预训练
    - `效率优化` → PEFT（LoRA, Adapter, Prefix Tuning, BitFit）、量化（GPTQ, SmoothQuant, QLoRA, LLM.int8）、剪枝（Wanda, LLM-Pruner）
    - `多模态LLM` → 预训练（Flamingo, BLIP-2, MiniGPT-4）、微调（LLaMA-Adapter, LaVIN）、提示（Multimodal-CoT）
    - `评估基准` → 多任务（MMLU, BIG-bench, GLUE/SuperGLUE）、推理（GSM8K, MATH, HumanEval）、语言理解（CoQA, WiC, RACE）、常识（HellaSwag, WinoGrande, PIQA）等100+基准
    - `应用` → 医学、教育、科学、数学、法律、金融、机器人、编码
- **核心洞察补充**：架构对比发现——预归一化在前100B规模提供稳定性但可能损害微调性能，GLM-130B采用DeepNorm（后归一化变体）获更优下游性能；并行注意+FFN层可提速15%且性能无降；MoE架构天然抗灾难性遗忘，适合持续学习；小模型微调——LIMA仅用1000条精选演示即接近GPT-4水平；Chinchilla定律指出每加倍模型规模应加倍训练token数；检索增强可使11B模型匹敌540B PaLM；红队测试发现即使对齐后的模型仍易受越狱攻击
- **附带资源**：论文Table 1-2提炼50+预训练与指令微调LLM的核心发现与洞察，Table 5汇总30+LLM的详细架构参数（层数/头数/隐藏维度/注意力类型/归一化/位置编码/激活函数），Table 6-7提供预训练与指令微调的优化配置（批量大小/学习率/优化器），Table 8-11系统整理预训练与微调数据集及评估基准，Table 12展示各NLP任务上顶级LLM性能对比、Figure 2展示LLM发布历史时间线，开源vs闭源、Table 3-4有50+预训练和30+微调LLM的架构与优化细节。参考文献500+篇，覆盖LLM领域全面。
<br>


### 5. Towards Efficient Generative LLM Serving: A Survey from Algorithms to Systems (2025)
[![Paper](https://img.shields.io/badge/Journal-ACM_Comput.Surv.'25-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=28.0-important)]()

[Towards Efficient Generative Large Language Model Serving: A Survey from Algorithms to Systems](https://dl.acm.org/doi/pdf/10.1145/3754448)

- **分类方式**：按 **算法创新**（解码算法/架构设计/模型压缩）与 **系统优化**（低精度量化/并行计算/内存管理/请求调度/内核优化）双维度组织，从机器学习系统（MLSys）视角审视LLM服务全栈
- **覆盖子方向**：
  - `解码算法` → 非自回归解码（Mask-Predict/Semi-Autoregressive/Blockwise Parallel）、推测解码/投机解码（SpecInfer/Medusa/EAGLE/Sequoia/Staged Speculative/Kangaroo）、早退（DeeBERT/FastBERT/CALM/SkipDecode）、级联推理（CascadeBERT/Tabi/FrugalGPT）
  - `架构设计` → 配置缩小（浅编解码/权重共享）、注意力简化（稀疏/MQA/GQA/MLA/Sliding Window/H₂O/StreamingLLM）、激活共享（跨层注意力复用）、条件计算（MoE路由/DeepSeekMoE/TaskMoE）、循环单元（RWKV/RetNet/Mamba）
  - `模型压缩` → 知识蒸馏（白盒MiniLLM/TinyBERT/黑盒Alpaca/Vicuna/WizardLM）、网络剪枝（结构化LLM-Pruner/Deja Vu/非结构化SparseGPT/Wanda/Flash-LLM/PowerInfer）
  - `低精度量化` → QAT（LLM-QAT/QLoRA/PEQA）、PTQ（GPTQ/SpQR/AWQ/LLM.int8/SmoothQuant/ZeroQuant/W4A4/FlexGen）、硬件支撑（NVIDIA INT8/INT4/FP8 Tensor Core/Hopper架构）
  - `并行计算` → 模型并行（Tensor/Pipeline/Sequence→DeepSpeed-Ulysses/Ring Attention/Context Parallelism）、云伸缩（SpotServe/ServerlessLLM）、去中心化推理（Petals/HexGen）
  - `内存管理` → PagedAttention（vLLM）/vAttention（虚拟-物理分离）/LightLLM（Token级）/CacheGen（KV Cache压缩）/InfiniGen（分层卸载）/Mooncake（KV Cache为中心的分离架构）
  - `请求调度` → 迭代级调度（Orca/Continuous Batching/In-flight Batching）、抢占式（FastServe/Andes）、分离式Prefill-Decode（Splitwise/DistServe/ExeGPT）、异构负载调度（TetriInfer/Llumnix/Helix）
  - `内核优化` → 融合（FasterTransformer/TurboTransformers/ByteTransformer/Welder）、定制注意力（FlashAttention/xFormers/FlashDecoding/FlashDecoding++/FlashInfer）、变长序列（Ragged Tensor/Bucketing/Packing）、自动编译（TVM TensorIR/MLIR/OpenAI Triton/TorchInductor/Mirage）
- **核心洞察补充**：推测解码在保证输出质量无损的前提下通过即用即验机制提升并行度，树上推测+验证（SpecInfer）被后续Medusa/EAGLE广泛采纳；vLLM的PagedAttention通过KV Cache分页管理显著提升批处理能力与吞吐；Prefill-Decode分离架构（Splitwise/DistServe）针对两阶段不同计算特性在不同GPU上独立优化；MQA→GQA→MLA的演进使KV Cache持续压缩（DeepSeek-V2通过MLA实现5.76×推理吞吐提升）；迭代级调度（Orca首创）已成为所有主流框架标配；FlashInfer以block-sparse格式统一多样化KV Cache模式、CUDA Graph最大化GPU利用率
- **附带资源**：论文Table 2系统对比vLLM/TensorRT-LLM/MLC-LLM/FlexFlow-Serve/LightLLM/DeepSpeed-Inference/TGI等10+开源GPU推理框架的并行计算、调度策略、注意力内核实现及优先优化目标（延迟vs吞吐）差异；Table 1分类总结高效Transformer的注意力简化方法及其LLM应用
<br>


### 6. A Survey on Efficient Inference for Large Language Models (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[A Survey on Efficient Inference for Large Language Models](https://arxiv.org/abs/2404.14294)

- **分类方式**：独创 **数据层-模型层-系统层** 三级分类体系，先分析三大效率瓶颈（模型规模/注意力平方复杂度/自回归解码），再按优化层级系统化组织
- **覆盖子方向**：
  - `数据层优化` → 输入压缩（Prompt剪枝：SelectiveContext/LLMLingua/LongLLMLingua/CoT-Influx；Prompt摘要：RECOMP/SemanticCompression；软提示压缩：PromptCompression/Gisting/ICAE/AutoCompressor；RAG：FLARE/REPLUG/Self-RAG）、输出编排（SoT骨架生成/SGD自适应骨架图/APAR自动并行/SGLang DSL编程）
  - `模型层-高效结构` → 高效FFN（MoE：Switch Transformer/BASE/Expert Choice/SE-MoE/StableMoE/SMoE-Dropout/GLaM/Mixtral 8x7B；MoEfication稀疏上采样/MPOE矩阵分解）、高效注意力（MQA/GQA；核注意力：Linear Transformer/Performer/RFA/PolySketchFormer；低秩注意力：Linformer/Luna/Set Transformer/Funnel-Transformer）、替代架构（SSM：S4/DSS/S4D/H3/Mamba/Liquid S4/S5/BiGS/DenseMamba；长卷积：Hyena；类注意力循环：RWKV/RetNet）
  - `模型层-压缩` → 量化（PTQ：GPTQ/AWQ/OWQ/SpQR/SqueezeLLM/QuIP/LLM.int8/SmoothQuant/ZeroQuant/RPTQ/OmniQuant/Atom/BiLLM/KVQuant/KIVI；QAT：LLM-QAT/QLoRA/QA-LoRA/LoftQ/Norm Tweaking）、权重剪枝（非结构化：SparseGPT/Wanda/ISC/BESA/Pruner-Zero/DSOT；结构化：LLM-Pruner/Sheared LLaMA/ZipLM/LoRAPrune/SliceGPT/FLAP/CoFi/SIMPLE/ExpertSparsity/SEER-MoE）、稀疏注意力（静态：Sparse Transformer/StreamingLLM/BigBird/Longformer/SemSA；动态：SpAtten/SeqBoat/Adaptively Sparse Attention/Reformer/Routing Transformer/Sparse Sinkhorn Attention/H₂O/Diffuser）、结构优化（NAS：AutoTinyBERT/NAS-BERT；LRF：LoRD/TensorGPT/LoSparse/ASVD/SVD-LLM）、KD（白盒：MiniLLM/GKD/TED/MiniMoE/DynaBERT/KPTD；黑盒：Multitask-ICT/MCKD/Distilling Step-by-Step/SCoTD/PaD/DISCO/LaMini-LM/Lion）、动态推理（样本级：FastBERT/DeeBERT/PABEE/HASHEE；Token级：CALM/SkipDecode）
  - `系统层-引擎` → 算子优化（FlashAttention 1-2/FlashDecoding/FlashDecoding++/MegaBlocks MoE）、推测解码（draft构造：DistillSpec/SSD/OSD/PaSS/REST/Lookahead/Medusa/Eagle/Kangaroo；验证：token tree verifier/Spectr）、图优化（ByteTransformer/DeepSpeed/算子融合）、卸载（FlexGen/llama.cpp/PowerInfer/FastDecode）
  - `系统层-服务` → 内存管理（vLLM PagedAttention/LightLLM Token级/S³预测分配/FlashInfer）、连续批处理（ORCA迭代级/vLLM/Sarathi/DeepSpeed-FastGen分片融合/Chunked-prefill）、调度（FCFS/FastServe多级反馈队列抢占/VTC公平性）、分布式（Splitwise/TetriInfer/DistServe预填-解码分离/SpotServe可抢占/Infinite-LLM长上下文/LoongServe弹性序列并行）
  - `硬件加速器` → FPGA（FACT/ALLO/DFX/FlightLLM）
  - `框架对比` → Table 6系统对比HuggingFace/DeepSpeed/vLLM/OpenPPL/FlashDecoding++/LightLLM/TensorRT-LLM的推理优化能力、单token延迟和在线服务吞吐
- **核心洞察补充**：提出三大效率瓶颈（模型规模→内存访问/注意力平方复杂度→计算+内存/自回归解码→内存访问）作为全篇分析框架；AWQ在A100上W4A16使LLaMA-2-7B解码1.4×-2.4×加速，预填阶段因反量化开销反而减速；Eagle推测解码达3.47×-3.72×加速，token tree verifier是其关键；vLLM PagedAttention通过虚拟内存管理消除碎片化，使KV Cache内存利用率显著提升；Chunked-prefill将长预填分片与短解码批处理合并，消除流水线气泡；Splitwise/DistServe预填-解码分离架构针对两阶段不同计算特性（计算密集vs内存密集）独立优化；FlashDecoding++通过统一softmax最大值异步化+FlatGEMM+启发式算子选择达4.86×加速
- **附带资源**：论文Table 3提供代表性PTQ方法的多维度对比（量化张量类型/数据格式/参数确定方案/值更新），Table 4在A100上W4A16量化下LLaMA-2系列在批大小×输入长度下的预填/解码/端到端加速比，Table 5对比6种推测解码方法（draft模型/额外开销/接受率/加速比），Table 6对比7个框架的推理吞吐和在线服务能力；论文Sec 7讨论Agent/长上下文/边缘部署/安全-效率协同四大关键应用场景

<br>


### 7. A Survey of Resource-Efficient LLM and Multimodal Foundation Models (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[A Survey of Resource-Efficient LLM and Multimodal Foundation Models](https://arxiv.org/pdf/2401.08092)

- **分类方式**：按 **基础模型类型**（LLM/ViT/扩散模型/多模态）+ **优化层级**（高效架构/高效算法/高效系统）+ **生命周期阶段**（预训练/微调/推理/服务）三维交叉组织
- **覆盖子方向**：
  - `高效架构` → 高效注意力（稀疏：Longformer/ETC/BIGBIRD/HEPOS；近似：Linformer/Reformer/Performer/Luna/Deformable Attention；无注意力：Hyena/H3/Mamba/RWKV/RetNet）、动态网络（MoE：Switch Transformer/GLaM/V-MoE/LIMoE/MoEfication；早退：FREE/SkipDecode/PABEE/DeeBERT/LGViT）、扩散优化（高效采样：DDIM/PNDM/DPM-Solver/ReDi/Nirvana；潜在空间：LDM/LD-ZNet/SALAD；架构变体：SnapFusion/ScaleCrafter/ERNIE-ViLG）、ViT优化（LeViT/PoolFormer/MobileViT/EfficientFormer/EfficientViT）
  - `高效预训练` → 数据缩减（文本去重/MAE掩码自编码/MixMAE/COPA/PatchDropout/TPS）、NAS（Zero-Shot NAS/ZICO/PASHA/RankNAS/PreNAS/ElasticViT）、渐进学习（stackingBERT/CompoundGrow/Staged Training/LiGO）、混合精度训练（Mesa/GACT）
  - `高效微调` → 加法（Adapter：ADA/MetaTroll/ST-Adapter/HiWi/AdaMix/MEFT/PEMA；Prompt Tuning：PromptTuning/ATTEMPT/BioInstruct/DualPL/MPrompt/DPT；Prefix Tuning：UAPT/Prefix-diffusion/DOP/DAPA/PIP）、选择性（SAM/SmartFRZ/FiSH-DiP/Token Mixing/VL-PET/SPT/GreenTrainer）、重参数化（LoRA及其衍生：EfficientDM/QLoRA/PEQA/QALoRA/LoftQ/GLoRA/LongLoRA/LOMO/MeZO/Delta-LoRA/PiSSA/DoRA/LoRA+）
  - `高效推理` → 推测解码（SpecInfer/Medusa/Lookahead Decoding/LLMCad）、提示压缩（LLMLingua/EntropyRank/LLMZip/AutoCompressors/ICAE/Nugget 2D/CoT-Max）、Token剪枝（PoWER-BERT/Length-Adaptive/TRBERT/DynamicViT/AdaViT/SPViT/PuMer）、KV Cache优化（H2O/Scissorhands/Landmark Attention/MLA/vLLM PagedAttention/vAttention/Mooncake/CacheGen/InfiniGen/CachedAttention）、长上下文（Transformer-XL/RMT/Block-Recurrent/LM-Infinite/StreamingLLM/PCW/LongNet/SLED）
  - `模型压缩` → 剪枝（结构化：LLM-Pruner/Sheared LLaMA/CoFi/SIMPLE/SpAtten；非结构化：SparseGPT/Wanda/UPop；上下文：DejaVu/PowerInfer/PowerInfer-2）、KD（黑盒：Lion/LaMini-LM/Distilling Step-by-Step/SOCRATIC CoT/SCOTT/SCoTD/PaD；白盒：MiniLLM/GKD/KPTD/TED/MixKD/DIME-FM）、量化（QAT：LLM-QAT/BitNet/EfficientQAT/QLoRA/PEQA；PTQ：GPTQ/AWQ/OWQ/SqueezeLLM/SmoothQuant/RPTQ/OliVe/OS+/Atom/I-LLM/FlexRound/QuaRot/SpinQuant；权重：GPTQ/SpQR/LLM.int8/QuIP；权重-激活：ZeroQuant/LLM-FP4/QLLM）、低秩分解（LoRD/TensorGPT/LoSparse/LPLR/ViTALiTy）
  - `高效系统` → 分布式训练（弹性：Varuna/Gemini/Bamboo/Oobleck；并行：DeepSpeed ZeRO/Megatron-TP/Galvatron/Sequence Parallelism；MoE：MegaBlocks/Tutel/FlexMoE/SmartMoE/Janus）、联邦学习（FwdLLM/FedBFFT/FedOBD/SplitLoRA/FedKSeed/FedBBPT）、云端服务（FlashAttention-2/Orca/vLLM PagedAttention/S-LoRA/Splitwise/SARATHI/SpotServe/HexGen）、边缘服务（EdgeFM/EdgeMoE/PC-MoE/LLMCad/PowerInfer-2/STI/LLM in a flash/mllmNPL/LMS/ELMS）
- **核心洞察补充**：Scaling Law仍是驱动大模型成功的核心规律，但也是轻量化模型的根本限制；DejaVu发现密集训练的非MoE模型也存在运行时稀疏性，可大幅减少推理计算；Mamba实现5×推理加速并线性缩放；FlashAttention通过算子融合减少HBM访问；vLLM PagedAttention通过虚拟内存管理消除KV Cache碎片化；推测解码在保持输出分布一致性前提下实现2-3×加速；Apple/Google正将LLM嵌入移动操作系统（LLM as a System Service）；未来云-边混合部署、模型稀疏性、Agent全栈优化、隐私保护大模型、Scaling Law理解是六大核心方向
- **附带资源**：论文Figure 4分析LLM各组件的存储与FLOPs成本分布，Figure 5展示GPT-2在不同token长度下的推理FLOPs，Figure 6对比多模态模型各模块成本，Figure 7剖析Stable Diffusion 2.1的U-Net/VAE/CLIP参数与FLOPs分布，Table 4对比Transformer及变体的时间复杂度与空间复杂度，Table 5汇总30+开源LLM训练/推理框架及其功能对比；配套[Github仓库](https://github.com/UbiquitousLearning/Efficient_Foundation_Model_Survey)

<br>


### 8. Model Compression and Efficient Inference for Large Language Models: A Survey (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)](https://arxiv.org/pdf/2402.09748)

[Model Compression and Efficient Inference for Large Language Models: A Survey]()

- **分类方式**：按 **五维压缩技术**（量化/剪枝/蒸馏/紧凑架构/动态网络）组织，并创新性地按 **模型规模分层**（中型模型≤1B vs 真·大型模型>1B），突出LLM的两大独特挑战
- **覆盖子方向**：
  - `量化` → 基础概念（均匀/非均匀/对称/非对称/粒度/校准/STE）、中型模型QAT（Q-BERT/TernaryBERT/BinaryBERT/BiBERT→全二值化）、中型模型PTQ（GOBO/I-BERT整数/组级4-bit）、生成式量化（Token级对比蒸馏+动态缩放）、LLM PTQ权重（GPTQ/QuIP/LDLQ→OBQ优化/AWQ激活感知/OWQ混合精度/SqueezeLLM敏感度K-means/QLoRA NF4/SpQR离群分离）、LLM PTQ权重+激活（LLM.int8离群维度分解/RPTQ聚类重排/SmoothQuant diag(s)平滑迁移/Outlier Suppression γ放大/FPTQ对数均衡/OmniQuant可学习裁剪/QLLM通道拆分/NormalFormat/FP8 vs INT8）、LLM QAT（LLM-QAT数据免蒸馏+KV Cache量化/ZeroQuant层蒸馏/QLoRA NF4+LoRA/QA-LoRA组级/LoftQ SVD初始化/INT2.1/AlphaTuning缩放因子/PEQA）、量化专题（离群值源头分析/4-bit最优性/scaling law/硬件协同内核LUT-GEMM）
  - `剪枝` → 基础概念（非结构化vs结构化/度量：幅度vs损失一阶二阶vs正则化/迭代vs一次性/全局vs局部/上游vs下游）、中型非结构化（幅度：GMP/GMP*；损失一阶：Movement Pruning/PLATON/PST/LoRAPrune；损失二阶：OBD/OBS/Optimal BERT Surgeon；正则化：L0硬混凝土分布/FLOP）、中型结构化（幅度：L2聚合；损失：DSP Gumbel-Softmax/Block Movement；正则化：CoFi联合粗细/L0注意力头+FFN/SIMPLE；其他：LayerDrop/Token Pruning/SNIP）、LLM非结构化（Wanda→权重×激活范数/RIA→相对重要性+通道置换/E-Sparse→信息熵/SparseGPT→OBS掩码+重构/ISC→OBS+OBD混合/GBLM-Pruner/PGZ）、LLM结构化（FLAP→波动度/LLM-Pruner→耦合结构+Fisher/LoRAShear→LHSPG渐进/Sheared LLaMA→目标架构+动态批次/Compresso→协作Prompt剪枝/SliceGPT→PCA截断/LLM Surgeon→通用OBS）
  - `知识蒸馏` → 基础（Logit/特征/关系/黑盒KD）、中型预训练蒸馏（DistilBERT余弦/MiniLM自注意力值-关系/MobileBERT瓶颈+HomoBERT剪枝/TinyBERT双阶段/TED任务感知过滤）、中型微调蒸馏（Distilled BiLSTM/PKD Skip-Last/DynaBERT宽深自适应/Metadistil/AD-KD归因/AdaBERT NAS/MixKD/Meta-KD/ReAugKD）、LLM黑盒KD（IF：Self-Instruct/Alpaca/Vicuna/LaMini-LM/Lion/PERsD；CoT：Distilling Step-by-Step/Fine-tune-CoT/SOCRATIC CoT/SCOTT/KARD/PaD/DOCTOR；ICL：Meta-ICT/Multitask-ICT/LLM-R）、LLM白盒KD（MiniLLM→反向KL+策略梯度/GKD→on-policy+JS散度/MiniMA→40%大小最优/TSLD→Token级Logit缩放）
  - `紧凑架构设计` → 稀疏注意力（步幅：Sparse Transformer/自适应span/α-entmax；窗口：BlockBERT/Longformer滑动+全局/BigBird随机+全局/BP-Transformer二分树/Combiner条件期望；数据驱动：Reformer LSH/Routing Transformer k-means/SAC LSTM边缘预测/SSA排序）、线性近似注意力（结合律：Linear Transformer elu+1/Performer FAVOR+/Nyströmformer聚类/HyperAttention Hamming LSH/双softmax；低秩：Linformer投影/VQ向量量化）、FlashAttention（Tiling分块+Online Softmax增量/FlashAttention-2序列维度并行+减少写回）、NAS（HAT硬件感知搜索→延迟预测器+Super Transformer+ARM vs GPU偏好差异）
  - `动态网络` → MoE（路由：Sparsely-Gated/GShard/Switch/Expert Choice/BASE线性分配/Hash/RL路由/DSelect-k/X-MoE低维路由/ST-MoE z-loss；架构：DeepSpeed-MoE金字塔/Brainformer NAS搜索；训练：StableMoE两阶段/EvoMoE演化/Expert Dropout/Gating Dropout）、MoE+压缩（蒸馏：Switch蒸馏→保留30%增益；剪枝：Z-code/渐进专家剪枝/MPOE张量分解共享/MoEfication→MoE化）、MoE+PEFT（AdaMix适配器混合/Sparse Mixers/SMLP）、早退（DeeBERT/FastBERT/PABEE/SkipBERT/LeeBERT/TR-BERT）、级联推理（Tabi/FrugalGPT/EcoAssistant/Mixture-of-Thoughts）
  - `推理框架` → 通用（DNNFusion算子融合/DeepSpeed Inference多GPU+异构内存）、专用（TurboTransformer序列感知内存/ByteTransformer无填充/ FlexGen Zig-Zag并行离线吞吐/PowerInfer热神经元GPU+冷神经元CPU混合）
- **核心洞察补充**：LLM压缩面临两大核心挑战：(1)**免重训**——微调成本随参数规模剧增，推动PTQ/一次性剪枝/免微调蒸馏成为主流；(2)**通用性保持**——LLM强调多任务泛化和涌现能力，压缩后需仔细验证零样本/少样本/推理能力；2-bit量化模型涌现能力严重退化，4-bit几乎无损；Wanda（权重×激活范数）在不需任何微调和二阶信息下接近SparseGPT性能；SmoothQuant通过数学等价变换diag(s)实现激活→权重量化难度迁移，首个成功W8A8；GPTQ可在4小时内在单A100上量化175B模型；MoE成为LLM高效扩展的主流范式（GPT-4/Mixtral/DeepSeekMoE）；FlashAttention通过Tiling+增量Softmax实现精确注意力计算且大幅减少HBM访问
- **附带资源**：论文TABLE 1从9个维度系统对比AWQ/GPTQ/LLM.int8/SmoothQuant/LLM-QAT等主流量化方法的特征（位宽/粒度/均匀性/对称性/静态vs动态/重训/零样本/整数运算），TABLE 3从8个维度对比LLM剪枝方法（单元/度量/迭代/一次性/微调/全局/局部），TABLE 4对比14种BERT蒸馏方法（训练阶段/知识来源/损失函数），TABLE 5总结8种代表性MoE方法（基座模型/稀疏性/最大规模/负载均衡），TABLE 6对比6种推理框架（通用性/方法），Figure 10展示Adapter模块与Transformer集成的架构图

<br>


### 9. A Survey on Transformer Compression (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[A Survey on Transformer Compression](https://arxiv.org/pdf/2402.05964)

- **分类方式**：按 **架构保持**（量化PTQ/QAT + 知识蒸馏）与 **架构自适应**（剪枝 + 高效架构设计→稀疏/线性注意力→非Transformer→高效FFN）四大维度组织，横跨NLP和CV
- **覆盖子方向**：
  - `量化-LLM` → PTQ（Outlier Suppression γ迁移/SmoothQuant diag(s)等价变换→激活→权重量化难度迁移/OmniQuant可学习权重裁剪+变换/RPTQ通道重排+聚类/ZeroQuant组级权重Token级激活/GPTQ二阶近似/AWQ激活感知/OS+通道平移缩放/QLLM低秩误差补偿/SqueezeLLM离群稀疏存储/CBQ跨块重建+LoRA/SignRound自适应舍入）（QAT：Q-BERT Hessian混合精度/I-BERT多项式近似GELU-SoftMax-LayerNorm+全整数推理/PEQA仅调缩放因子/QLoRA NF4+双量化/LLM-QAT免数据+KV Cache量化）
  - `量化-ViT` → PTQ（PTQ-ViT核范数混合精度+秩保留/PTQ4ViT双均匀量化+Hessian指导/FQ-ViT Log2+2的幂全量化/APQ-ViT分块渐进优化/NoisyQuant固定噪声增强/RepQ-ViT尺度重参数化）（QAT：Q-ViT全可微+头级位宽/Quantformer秩保持+组级量化/OFQ统计权重量化+置信度退火+VVTQ变分感知）
  - `知识蒸馏-NLP` → Logits（DistilBERT/MixKD线性插值/MiniLLM→反向KLD/GKD→on-policy/TED任务感知层过滤）、Hint（PKD Skip-Last/MINILM值-关系/MobileBERT瓶颈+HomoBERT/TinyBERT双阶段）、API黑盒（CoT：Fine-tune-CoT/SCOTT/KARD/PaD；IF：LaMini-LM/Lion/Symbolic KD；ICL：Multitask-ICT/Meta-ICT）
  - `知识蒸馏-ViT` → Logits（DeiT硬标签+蒸馏Token/TinyViT预存数据增强+Logits）、Hint（DearKD CNN中间层诱导/ManifoldKD Patch-批次流形/ViTKD→FFN特征优于MHA+浅层适用+深层生成优于模仿）、跨架构（Renyi→跨归纳偏置蒸馏/CSKD位置级密集预测）
  - `剪枝-LLM` → 非结构化（SparseGPT OBS掩码+重构/Wanda权重×激活范数）、结构化（LLM-Pruner耦合结构+Fisher/LoRAShear LHSPG渐进/Sheared LLaMA目标架构+动态批次/SliceGPT PCA截断）、上下文/Token（Dynamic Context Pruning sigmoid选择+KV Cache感知/稀疏注意力→局部+全局+内容分组）
  - `剪枝-ViT` → Token/特征（Patch Sliming自顶向下/Power-BERT渐进词消除/DynamicViT轻量预测网络/S²ViTE联合非结构化+结构化）、结构化（ViT-Slim单次搜索/SAViT协同优化/X-Pruner类感知可微/Global Hessian剪枝+参数重分布）、表5-6系统对比DeiT剪枝和LLM剪枝方法的精度与加速比
  - `高效架构-NLP` → 稀疏注意力（Factorized/Sparse Transformer/Longformer窗口+全局/BigBird/Reformer LSH/Linear Transformer核函数/Performer FAVOR+/FlashAttention IO感知分块）、非Transformer（S4→H3→Mamba选择性SSM/RetNet并行+递归+块递归三模式/RWKV线性注意力+递归/Hyena门控长卷积）、高效FFN（MoE：GShard/Switch/Expert Choice/DeepSpeed-MoE/SwiGLU激活）
  - `高效架构-ViT` → 增强局部性（T2T-ViT聚合/LeViT CNN前置/MobileViT混合/TNT子Patch/CrossViT双分支/Swin移位窗口/CSwin交叉窗口/KVT k-NN注意力/HiLo高低频解耦）、更快注意力（Image Transformer局部/FasterViT层级分解/Flatten Transformer深度卷积+线性注意力）、无注意力（AFT/GFNet FFT/Pure MLP系列→MLP-Mixer/ResMLP/CycleMLP/MetaFormer池化/Vim双向Mamba/VMamba交叉扫描模块）
  - `其他压缩` → 张量分解（Kronecker GPT2 1.5×/LoRD代码LLM/TSVD三元SVD/TensorGPT嵌入层3×）、早退（CALM 3×加速/SkipDecode KV缓存复用）、推测采样（Speculative Sampling → 理论无损/LLMCad端侧推理）
- **核心洞察补充**：量化→LLM离群值平滑（SmoothQuant/OmniQuant）是关键，ViT低比特（<4bit）需QAT；知识蒸馏→黑盒KD通过API获取CoT/IF/ICL能力的提炼是LLM时代新范式，白盒KD中MINILM值-关系匹配简单高效；剪枝→SparseGPT实现175B一次性50-60%非结构化剪枝无需微调，结构化剪枝需PEFT（LoRA）辅助恢复；高效架构→Mamba/RetNet/RWKV等线性复杂度架构有潜力替代Transformer，但在长序列上下文学习能力上仍待验证；跨域共性→离群值处理、秩保持、结构化搜索策略在NLP和ViT压缩中原理相通；压缩组合→先架构设计→再剪枝→最后量化的顺序可获极致压缩
- **附带资源**：论文Table 1汇总四大类压缩方法的代表工作与亮点，Table 2系统对比PTQ与QAT在ViT-B/DeiT/Swin上的W/A位宽与Top-1精度，Table 3提供LLaMA系列量化困惑度（7B-65B/4-8bit），Table 4对比DistilBERT/TinyBERT/MobileBERT等蒸馏方法的师生参数量与加速比，Table 5-6统计DeiT-B剪枝方法及LLM剪枝的代表性实验数据，Table 8对比Transformer/Mamba/RetNet等架构的训练并行、推理时间和内存复杂度

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
| 3 | 📖 **Art and Science of Quantizing Large-Scale Models: A Comprehensive Overview** | 2024 | arXiv | `量化范式`：PTQ(30+算法) + QAT(4类) + KV Cache压缩 + KD + 极端低比特 | 量化领域最深度的综述之一；详尽推导LLM-QAT/SmoothQuant/AWQ/GPTQ等核心公式，覆盖从二值网络到LLM量化的完整演进 |

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

[Survey on Knowledge Distillation for Large Language Models: Methods, Evaluation, and Application](https://dl.acm.org/doi/pdf/10.1145/3699518?download=true)

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


### 3. Art and Science of Quantizing Large-Scale Models: A Comprehensive Overview (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[Art and Science of Quantizing Large-Scale Models: A Comprehensive Overview](https://arxiv.org/pdf/2409.11650)

- **分类方式**：按 **量化技术演进**（传统QNN→LLM量化）与 **方法体系**（QAT/PTQ/KV Cache压缩/KD）组织，提供从基础到前沿的完整技术脉络
- **覆盖子方向**：
  - `传统QNN基础` → BinaryConnect（确定性/随机二值化+STE）、BNN（权重+激活二值化+移位BatchNorm）、XNOR-Net（XNOR+bitcount加速）、DoReFa-Net（首次量化梯度）、WAGE（首次全整数量化训练→权重/激活/梯度/误差均量化）
  - `LLM量化算法详解` → LLM-QAT（数据免蒸馏+对称MinMax+KV Cache首量化+混合采样，4-bit下仅1.5点精度损失）、PEQA/L4Q（LoRA-LSQ融合→权重合并→量化→梯度反传，3-bit提升2%）、QLoRA（NF4+双量化+Paged Optimizers，65B模型单48GB GPU微调）、LUT-GEMM（BCQ非线性量化+查表去反量化）、ZeroQuant（组级+Token级精细量化+LKD层蒸馏，INT8达5.19×加速）、SmoothQuant（diag(s)平滑变换→激活量化难度迁移至权重，1.51×加速）、SpQR（隔离离群值→高精度存储+双层量化）、OliVe（Outlier-Victim Pair→牺牲正常值换离群值表示范围+abfloat+内存对齐）、GPTQ（OBQ改进→固定左到右量化顺序+Cholesky分解）、AWQ（激活感知选1%显著权重+per-channel缩放+无需反向传播）、EasyQuant（免数据+保留<1%离群值不变+梯度优化范围，10×更快）
  - `QAT分类体系` → 免数据QAT（LLM-QAT/EdgeQAT自适应位宽）、矩阵变换QAT（QuaRot正交旋转去离群值/SpinQuant学习最优旋转）、轻量高效QAT（LR-QAT低秩分解压缩QAT开销/EfficientQAT自适应分层+L4Q LoRA量化融合）、极端低比特QAT（PB-LLM 2-bit部分二值化→保留关键权重+自适应分层参数）
  - `PTQ演进` → 早期（ACIQ截断优化+DFQ免数据4-bit+LBQ多张量+PWLQ分段线性）、中期（SPARQ最高有效位选择+BRECQ首次INT2+AdaRound自适应舍入）、近期（PTQD量化噪声分解+ZeroQ免数据蒸馏+Pareto最优位宽）、视觉PTQ（PTQ-ViT相似性感知+PTQ4ViT双均匀量化+Hessian度量）、扩散PTQ（Q-DiT细粒度组量化+动态激活量化+进化搜索）、ViT PTQ（AdaLog自适应对数底量化+偏置重参数化+FPCS快速渐进搜索）
  - `KV Cache量化` → 系统优化（DeepSpeed Inference多GPU异构内存+FlexGen单GPU高吞吐）、Token淘汰（Scissorhands重要性持久假设5×减少/H2O Heavy-Hitter动态保留）、量化（KVQuant非均匀量化/KIVI免调2-bit非对称/QAQ质量自适应/SKVQ滑动窗/WKVQuant权重KV协同）、跨层压缩（MiniCache相邻层相似KV合并+敏感Token保留/CLA跨层注意力共享/MLKV多层KV头共享）
  - `KD辅助量化` → 逐层蒸馏/注意力蒸馏/Logit蒸馏、QKD三阶段（自学-共学-指导）、SQAKD自监督量化感知蒸馏、LLM-QAT中Logits蒸馏对齐
- **核心洞察补充**：LLM量化面临三大难题——离群值（LLM权重/激活中存在极值，直接裁剪严重损害性能）、分布不匹配（微调数据需与预训练分布一致）、规模差异（小模型量化方法不适用）；SmoothQuant通过数学等价变换diag(s)实现"激活→权重"量化难度迁移，是首个成功实现W8A8的LLM PTQ；AWQ发现仅保护1%显著权重即可大幅降低量化误差，基于激活而非权重本身选择保护对象避免过拟合校准集；LLM-QAT首次将QAT与KV Cache量化结合，30B模型4-bit仅降1.5点；GEAR首创三合一压缩（量化骨干+D的SVD低秩L+稀疏S），KV Cache压缩率远超单一方法；QLoRA使65B模型在单48GB GPU微调成为可能，结合NF4+双量化+分页优化器三大创新
- **附带资源**：论文Table I汇总17+种量化算法的核心技术特征（对称MinMax/NF4/BCQ/OVP等），Table II-IV从激活量化/离群值处理/重要性加权/内存对齐等多维度系统对比各类算法，Figure 2-3展示L4Q与基线对比及KV Cache压缩方法分类树；论文还提供从BinaryConnect到LLM-QAT的完整QAT-QNN演进时间线

<br>
</details>

---

<a id="infer-opt"></a>
### ⚡ 推理阶段优化
> `03-Inference-Optimization` | KV缓存压缩 · 投机解码 · FlashAttention · 系统级服务 · 文本压缩 · 硬件加速

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | 📖 **Large Language Model Inference Acceleration: A Comprehensive Hardware Perspective** | 2025 | arXiv | `硬件平台`：CPU/GPU/FPGA/ASIC/PIM + `优化方法`：量化/稀疏/快速解码/算子优化/异构协同 | 首篇以tokens/s和tokens/J统一度量不同硬件平台LLM推理性能的综述；PIM/NDP能效比最高达46.66 tokens/J |
| 2 | 📖 **A Survey on Hardware Accelerators for LLMs** | 2025 | Applied Sciences | `硬件平台`：FPGA/GPU/ASIC/存内计算 + `加速技术`：稀疏/近似/融合/混合精度 | 系统梳理30+加速器架构；存内计算与ASIC可实现3-4个数量级的能效提升，FPGA在灵活性与效率间取得最优折中 |
| 3 | 🔥 **Prompt Compression for Large Language Models: A Survey** | 2025 | NAACL-HLT | `压缩范式`：硬提示(过滤/改写) + 软提示(编码器-解码器) + `理解视角`：注意力优化/PEFT/模态集成/合成语言 | 首篇Prompt压缩系统综述；独特解读软提示为"LLM新合成语言"，硬软结合是未来方向 |
| 4 | 📖 **Memory Is All You Need: An Overview of CIM Architectures for Accelerating LLM Inference** | 2024 | arXiv | `CIM器件`：SRAM/ReRAM/PCM/FeFET/MRAM + `加速策略`：算法增强/容错/硬件感知训练/异构计算 | 首篇聚焦存内计算加速LLM推理的综述；模拟CIM可突破冯·诺依曼瓶颈，实现数倍至数百倍能效提升 |
| 5 | 📖 **Contextual Compression in Retrieval-Augmented Generation for Large Language Models: A Survey** | 2024 | arXiv | `压缩维度`：语义压缩/PLM压缩/检索器压缩 + `RAG评估`：三元组(上下文+答案+接地)+四能力 | 首篇聚焦RAG上下文压缩的综述；覆盖AutoCompressor/ICAE/RECOMP/LongNet等核心方法 |
| 6 | 📖 **Closer Look at Efficient Inference Methods: A Survey of Speculative Decoding** | 2024 | arXiv | `推测解码`：模型中心(Draft设计) + Draft中心(验证策略) + `部署挑战`：吞吐/长上下文/并行/硬件/泛化 | 首篇推测解码系统综述；独创模型中心vs Draft中心二分法，覆盖Medusa/EAGLE-2/Hydra等前沿方法 |

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

### 3. Prompt Compression for Large Language Models: A Survey (2025)
[![Paper](https://img.shields.io/badge/Conference-NAACL'25-blue)]()

[Prompt Compression for Large Language Models: A Survey](https://aclanthology.org/2025.naacl-long.368.pdf)

- **分类方式**：按 **压缩范式**（硬提示方法/软提示方法）两大维度组织，进一步按架构（仅解码/编码-解码）和机制（过滤/改写/微调/冻结）细分
- **覆盖子方向**：
  - `硬提示-过滤` → 基于自信息（SelectiveContext通过SpaCy短语合并筛选低信息token；LLMLingua以小LM计算困惑度进行token级过滤，支持20x压缩率）、蒸馏增强（LLMLingua-2数据蒸馏训练分类器保留关键token）、RL增强（PCRL模型无关/TACO-RL任务特定的强化学习token选择）、嵌入增强（CPC上下文感知句子编码/TCRA-LLM嵌入摘要与语义压缩）、LongLLMLingua（文档重排+子序列恢复处理更长上下文）
  - `硬提示-改写` → Nano-Capsulator（微调Vicuna-7B将提示总结为简洁自然语言，语义保持损失+效用奖励函数）、CompAct（主动压缩检索文档用于问答）、FAVICOMP（基于熟悉度的证据压缩用于RAG）
  - `软提示-仅解码` → CC对比条件（为每个自然语言提示训练特定软提示，KL散度对齐输出分布）、GIST（微调LLM注意力掩码，压缩token存于KV值，最大26x压缩率，可泛化到未见提示）、AutoCompressor（递归分段压缩，支持30720 token长上下文，逐迭代传递摘要向量）
  - `软提示-编码器-解码器` → ICAE（微调编码器，冻结LLM解码器，LoRA微调，压缩512 token到32-128向量，4x-16x压缩率）、500xCompressor（KV对取代嵌入向量，1-16 token压缩480 token，6x-480x压缩率，ArxivQA新数据防泄漏）、QGC（查询引导压缩器，保留高压缩比下关键信息）、xRAG（冻结嵌入模型+可训练适配器，单token压缩文档，SFR-Embedding-Mistral实现极致压缩）、UniICL（冻结LLM编码器-解码器，仅训练投影器，压缩ICL示例，嵌入可直接用于示例选择）
  - `RAG应用` → xRAG/RECOMP/COCOM/CompAct/FAVICOMP/AdaComp/LLoCO/TCRA-LLM
  - `Agent与工具` → HD-Gist（API文档压缩）、工具使用上下文压缩
  - `特定领域` → Tag-LLM（科学领域）、CoLLEGe（概念嵌入生成）
- **核心洞察补充**：提出四种理解软提示压缩的独特视角——(1)注意力机制优化（压缩token先吸收完整上下文，新token仅关注压缩token，类似"信息蒸馏"）；(2)与Prompt/Prefix Tuning的类比（ICAE类Prompt Tuning生成嵌入，500xCompressor类Prefix Tuning生成KV对，KV对含更丰富信息，高压缩比下优于嵌入）；(3)模态集成（压缩文本可视为新模态，与视觉编码器架构平行，但文本信息密度更高，压缩需更高精度）；(4)新合成语言（编码嵌入满足语言的三个关键特征：编码信息、在实体间传递、自适应评估，可视为LLM的"高效新语言"）
- **核心洞察补充-挑战与未来**：当前软提示编码器与解码器尺寸相近，压缩时间与原始LLM输入处理时间可比，仅在新token生成阶段提升效率（短输出任务收益有限）；微调会导致灾难性遗忘和模型漂移，需要大规模多样化数据重训；硬软提示机制正交，结合可进一步提升压缩率，但压缩时间累加；受多模态架构启发，交叉注意力（而非当前的自注意力）用于压缩token尚待探索；BERT类小模型（参数比LLM少10x+）作为压缩编码器可大幅提升压缩速度
- **附带资源**：论文图2提供Prompt压缩方法树形全景（硬/软、过滤/改写、仅解码/编码-解码、应用领域），Table 1为完整方法与应用的层级化汇总；配套开源仓库持续更新 [https://github.com/ZongqianLi/PromptCompression-Survey](https://github.com/ZongqianLi/PromptCompression-Survey)

<br>


### 4. Memory Is All You Need: An Overview of CIM Architectures for Accelerating LLM Inference (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[Memory Is All You Need: An Overview of Compute-in-Memory Architectures for Accelerating Large Language Model Inference](https://arxiv.org/pdf/2406.08413)

- **分类方式**：按 **CIM器件技术**（SRAM/ReRAM/PCM/FeFET/MRAM）与 **加速策略**（算法增强/容错/硬件感知训练/高精度/全电路/异构计算）双维度组织，深入剖析Transformer算子的CIM映射
- 
- **覆盖子方向**：
  - `Transformer算子分析` → 注意力计算（QKV投影/MHA/Scaled Dot-Product/Softmax）、FFN（两层线性变换+非线性激活）、执行时间分布（FFC层主导，注意力占比随序列长度二次增长）
  - `CIM基本原理` → 交叉开关阵列（Ohm定律乘法+Kirchhoff电流求和）、ADC/DAC转换、模拟MVM（单次读操作完成矩阵向量乘）、复杂度从O(n²)降至O(n)
  - `器件技术对比` → SRAM（6T-12T/成熟/低写延迟/高漏电/低密度）、ReRAM（1T1R/高密度/多值/3D集成/写能量高）、PCM（热驱动相变/高开关比/易制造/耐久度低）、FeFET（三端/高耐久10¹²/CMOS兼容/低写电流）、MRAM（磁性存储/高耐久/低开关比/面积大）
  - `算法增强` → 多模式CIM（MulTCIM：注意力重塑+Token剪枝+动态位宽平衡）、窗口自注意力（ReBERT：排除低注意力Token不降精度）、Token级数据流（TransPIM：Token分片+内存分区并行+HBM近存计算）、矩阵分解（ReTransformer：消除数据依赖+子矩阵流水线避免中间结果写入）
  - `容错与弹性` → 结构化剪枝+权重复制+MSB嵌入（零额外参数容错）、差分结构剪枝（行/列剪枝释放空间复制关键权重）、硬故障防护（非均匀冗余/权重投票）
  - `硬件感知训练` → 噪声注入训练（前向注入非理想性/反向全精度）、漂移补偿（全局校正因子×缩放因子比值）、ISO精度（大网络可在CIM非理想性下保持与FP32相差<1%）
  - `高精度技术` → RIME（单周期NOR/NAND/Minority逻辑实现FP32存内运算）、CMOS协处理（指数/除法由数字单元处理）
  - `全电路设计` → 无ADC方案（共享斜坡+紧凑比较器/位级稀疏位映射翻转/模拟信号存储+时序生成器）、ReRAM非线性扩展（矩阵乘法+激活函数均在ReRAM中实现）
  - `异构计算` → 模拟-数字混合（ReRAM预测Token相关性+SRAM精确注意力计算）、CMOS+NVM混合（iMTransformer：FeFET存投影权重+CMOS存注意力分数+CAM局部敏感哈希过滤）、序列阻塞数据流（X-Former重叠投影引擎和注意力引擎计算）、GPU+NVM扩展（25×更大模型/保持>50%峰值性能）
  - `代表性架构性能` → PIM-GPT（41×-137×加速/123×-383×能效 vs T4 GPU）、iMCAT（200×加速/41×能效 vs Titan RTX）、X-Former（85×加速/7.5×能效 vs GTX 1060）、HARDSEA（13.5×-28.5×加速/291.6×-1894.3×能效 vs RTX 3090）、RACE-IT（10.7×加速/1193×能效 vs H100）、IBM NorthPole（7×加速/14×性能功耗比 vs MLPerf最优）
- **核心洞察补充**：传统架构>60%时间浪费在数据等待，数据搬运能耗比实际FLOPs高数个数量级；CIM通过消除数据搬运突破冯·诺依曼瓶颈，尤其适合Transformer中占主导的大规模MVM运算；注意力计算的双动态操作数特性导致NVM写延迟/能耗问题，是CIM加速Transformer的核心挑战；非线性操作（Softmax/LayerNorm/GELU）虽占比小但在ReRAM中可消耗高达70%系统能量；模拟CIM的非理想性（编程噪声/读取噪声/电导漂移/工艺偏差）需通过硬件感知训练+误差校正+异构架构综合应对；系统级效率远低于宏级效率（外围电路ADC/DAC开销大），无ADC方案是重要趋势；LLM尺寸远超当前CIM容量（GPT-3需数千MB vs 当前百MB级），多芯片扩展是落地关键
- **附带资源**：论文Table I对比BERT/GPT-3的参数量/层数/FC与注意力计算比例，Table II系统对比5种CIM器件技术（多值能力/单元面积/密度/开关比/写能量/写延迟/漏电/耐久度），Table III汇总10+种CIM加速器在BERT/GPT等模型上的加速比和能效比及对比基准

<br>


### 5. Contextual Compression in Retrieval-Augmented Generation for Large Language Models: A Survey (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[Contextual Compression in Retrieval-Augmented Generation for Large Language Models: A Survey](https://arxiv.org/pdf/2409.13385?)

- **分类方式**：按 **压缩技术维度**（语义压缩/预训练语言模型压缩/检索器压缩）三大类组织，并配套RAG评估指标（三元组+四能力）与基准数据集
- **覆盖子方向**：
  - `语义压缩` → 上下文蒸馏（Snell→逐步推理内化/Gisting→压缩为KV注意力前缀）、提示压缩（软提示：Prompt Tuning/Prefix Tuning/Prompt Compression→KL散度对齐；任务无关：LLMLingua-2数据蒸馏+Token分类保留/丢弃）、高效注意力（Transformer-XL分段递归/Longformer稀疏线性/FlashAttention分块重算/LongLoRA高效微调）、外推与插值（Position Interpolation线性变换/YaRN NTK感知缩放至128K）、上下文窗口扩展（Fei语义压缩三阶段→主题聚类+模型调优+重组→6-8×压缩）
  - `PLM压缩` → AutoCompressors（RMT架构+递归摘要向量+随机分段训练+跨段落推理→1-2个数量级压缩）、LongNet（扩大注意力→对数依赖+线性复杂度+10亿Token规模）、In-Context AutoEncoder ICAE（双阶段→自编码预训练+指令微调→4×压缩+固定长度记忆槽+冻结LLM解码器）、RECOMP（抽取式压缩器→对比学习选关键句；摘要式压缩器→GPT蒸馏多文档摘要→RALM前置压缩）
  - `检索器压缩` → LLMChainExtractor（逐文档LLM调用提取相关内容）、EmbeddingsFilter（嵌入相似度筛选→更经济快速）、DocumentCompressorPipeline（多压缩器串联→TextSplitter分块+EmbeddingsRedundantFilter去冗余+RelevantFilter相关性过滤）
  - `评估指标` → RAG三元组（上下文相关性Context Relevance→防止无关信息致幻觉；答案接地性Groundedness→逐声明验证支撑证据；答案相关性Answer Relevance→评估最终回答与用户输入匹配度）、四能力（噪声鲁棒性→区分相关与无关文档；负拒绝→识别文档不足时拒答；信息整合→多文档综合评估；反事实鲁棒性→识别并忽略错误信息）、压缩率、推理时间
  - `基准数据集` → 单跳/多跳QA、多选QA、特定领域QA、长文本场景、对话生成、代码搜索与解释
- **核心洞察补充**：上下文压缩的独特价值在于RAG场景中检索到的文档常含大量无关信息，压缩可显著降低LLM处理开销并提升回答质量；AutoCompressors将长文本递归压缩为摘要向量，作为下一段落的软提示，实现跨段落信息保持；ICAE冻结LLM解码器仅训练编码器，压缩Token可跨LLM复用，4×压缩率下保持良好的条件生成能力；RECOMP通过前置压缩步骤将多文档摘要作为LLM输入前缀，同时降低编码成本并引导正确输出；RAG评估需同时关注检索质量（上下文相关性）和生成质量（接地性+答案相关性），噪声鲁棒性和负拒绝能力反映模型在非理想检索条件下的鲁棒性
- **附带资源**：论文Figure 1提供上下文压缩方法的完整分类体系思维导图（语义压缩→PLM→检索器三叉树），Figure 10展示RAG三元组评估框架（上下文相关性/接地性/答案相关性），配套Github仓库持续更新 [https://github.com/SrGrace/Contextual-Compression](https://github.com/SrGrace/Contextual-Compression)

<br>


### 6. Closer Look at Efficient Inference Methods: A Survey of Speculative Decoding (2024)
[![Paper](https://img.shields.io/badge/Platform-arXiv-blue)]()

[Closer Look at Efficient Inference Methods: A Survey of Speculative Decoding](https://arxiv.org/pdf/2411.13157?)

- **分类方式**：首创 **Draft-模型中心**（Draft模型设计→独立/依赖）与 **Draft-Draft中心**（验证策略→概率/搜索优化/树图/混合自适应）双维度分类体系，并覆盖五类实际部署挑战
- **覆盖子方向**：
  - `Draft阶段-模型中心` → 独立Draft模型（Speculative Sampling同系列/Chimera Trigram+全上下文编码器/S2D Sorted Fine-tuning子模型自适应选择/Direct Alignment蒸馏对齐/Online Speculative Decoding查询分布动态调整）、依赖Draft模型（Medusa多头预测/Hydra序列依赖头/EAGLE特征层预测+自回归头/SpecDec++自适应候选长度/EESD早退+知识蒸馏/LayerSkip早退+损失函数引导/S3D中间层跳过+多Token预测+Draft验证同体）
  - `验证阶段-Draft中心` → 概率方法（Nucleus Sampling截断低概率尾/HASS训练-推理概率对齐→提高接受率）、搜索优化（LazyLLM动态Token剪枝→KV逐步计算/SLiM假设缩减→轻量验证前置过滤/BPD分块并行+重打分机制）、树图方法（GSD DAG合并公共Token序列+剪枝/RSD递归+无放回采样→GumbelTop-k+Stochastic Beam Search）、混合自适应（EAGLE-2置信度分数→接受率近似+动态调整树结构/OPT-Tree最大化期望接受长度/ProPD早剪枝+动态树生成→实时自适应）
  - `部署挑战` → 吞吐（MagicDec自适应稀疏KV Cache解决长上下文高batch瓶颈/BASS批量优化注意力+GPU高利用率→15.8%利用率10×于基线）、长上下文生成（MagicDec稀疏Cache管理/TriForce层次推测+Attention稀疏+重要Token淘汰→支持120K Token）、模型并行（BASS KV Padding+拆分/EMS-SD Unpad KV Cache处理变长序列→batch size 16仍2.85×加速）、硬件限制（PPD硬件感知动态稀疏树→0.004%内存开销/S3D跳层+多Token预测→8.06GB VRAM低于EAGLE 9.63GB/参数卸载+量化开销7×减速）、泛化性（SpecBench多任务基准→EAGLE在翻译/摘要/QA/数学推理/多轮对话上普遍最优，但尚无全任务统一最优方案）
- **核心洞察补充**：有效解码长度(EDL)是衡量推测解码效率的核心指标——接受Token数越多则加速越大；同系列草稿模型（如OPT-125M+OPT-7B）效果好→相似预训练→相似预测行为→高接受率；EAGLE创新性地在特征层而非Token层做预测，结合自回归头，在多项任务上达SOTA；Medusa多头并行解码无需独立Draft模型，简化了部署；树结构（GSD有向无环图/RSD递归/OPT-Tree自适应）比单序列Draft显著提升验证吞吐；Nucleus Sampling通过截断低概率尾解决Beam Search导致的文本退化问题
- **附带资源**：论文Figure 1提供推测解码方法的完整分类体系树形图（模型中心→独立/依赖；Draft中心→概率/搜索/树图/混合），Figure 3为各方法发布时间线图（2023.05-2024.06），Algorithm 1给出标准并行推测解码伪代码；文中对比了多种方法在SpecBench基准上的加速比

<br>

</details>

---

<a id="train-opt"></a>
### 🏋️ 训练阶段优化
> `04-Training-Optimization` | 高效预训练 · 高效微调

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | 🏆 **Parameter-Efficient Fine-Tuning in LLMs: A Survey of Methodologies** | 2025 | Artificial Intelligence Review `IF=10.2` | `PEFT分类`：加性/重参数化/选择性/混合/量化/多任务 + `应用`：视觉/扩散/MLLM | 覆盖100+方法的PEFT全景综述；QLoRA使65B模型可在单48GB GPU微调，PEFT可减少90%+训练成本 |


<details>
<summary><b>📄 展开详情</b></summary>
<br>

*本子方向涵盖以下细分领域：*
- `Efficient-Pretraining`：数据筛选, 模型并行, MeZO等
- `Efficient-Finetuning`：LoRA, Prefix Tuning, P-Tuning, QLoRA等
<br>


### 1. Parameter-Efficient Fine-Tuning in LLMs: A Survey of Methodologies (2025)
[![Paper](https://img.shields.io/badge/Journal-Artif Intell Rev'25-blue)]()
[![Paper](https://img.shields.io/badge/SCI_Q1-red)]()
[![Paper](https://img.shields.io/badge/IF=13.9-important)]()

[Parameter-efficient fine-tuning in large language models: a survey of methodologies](https://doi.org/10.1007/s10462-025-11236-4)

- **分类方式**：按 **PEFT方法类型**（加性/重参数化/选择性/混合/量化/多任务）六大类组织，并拓展至视觉模型、扩散模型、多模态LLM三大应用领域
- **覆盖子方向**：
    - `Additive PEFT` → Adapter（Serial, Residual, Parallel, Compacter）、Soft Prompt（Prefix-tuning, Prompt-tuning, P-tuning, Xprompt, APT）、Scale & Shift（(IA)³, SSF, PASTA, MoV）
    - `Reparameterized PEFT` → 低秩分解（LoRA, KronA）、LoRA衍生（DyLoRA, AdaLoRA, SoRA, LoRA+, DoRA, Laplace-LoRA, HydraLoRA, AFLoRA, LoRA-SP, SuperLoRA, PeriodicLoRA）
    - `Selective PEFT` → 非结构化掩码（Diff pruning, BitFit, Child-tuning, FishMask, LT-SFT）、结构化掩码（FAR, Xattn Tuning, SPT）
    - `Hybrid PEFT` → UniPELT, MAM Adapter, S⁴, LLM-Adapter, NOAH, AutoPEFT, ProPETL
    - `Quantization PEFT` → QLoRA, QA-LoRA, LoftQ, LQ-LoRA, QDyLoRA, BitDelta, BI-Adapter, PEQA
    - `Multi-task PEFT` → AdapterFusion, AdaMix, MOELoRA, LoRAHub, SPoT, ATTEMPT, MPT
    - `应用扩展` → 视觉模型（图像分类、密集预测）、扩散模型（少样本生成、可控生成）、多模态大模型
- **核心结论/洞察**：PEFT通过仅微调<1%参数达到接近全微调性能，大幅降低计算/存储成本；LoRA及其衍生方法是目前最主流的PEFT范式；LoRA可将可训练参数减少10,000倍（GPT-3 175B仅需0.01%参数微调）；QLoRA通过NF4+双量化+Paged Optimizers使65B模型在单48GB GPU上微调成为可能；DoRA通过权重分解（幅度+方向）首次在PEFT上匹敌全参数微调性能；全量SFT需400万GPU小时的场景，PEFT可降至40万GPU小时（90%成本降低）；LLaMA-3.1 405B训练需4000万GPU小时，PEFT使"微调"这一能耗重灾区变得可持续；LLaVA系列MLP连接器在实际效果上可超越复杂的Q-Former设计，PEFT是实现可持续AI研究的关键技术。
- **附带资源**：论文Figure 4提供PEFT方法完整分类体系思维导图，Figure 3/5-11以示意图对比各类方法核心原理，Table 5系统对比各PEFT方法的可训练参数量、应用场景与局限性，Table 6呈现代表性方法在多种基座模型和任务上的性能对比，Table 7汇总视觉/密集预测/扩散模型/可控生成四大应用领域的PEFT方法性能
<br>


### 3. A Survey on Hardware Accelerators for Large Language Models (2025)
[![Paper](https://img.shields.io/badge/Journal-Appl.Sci.'25-blue)]()

[A Survey on Hardware Accelerators for Large Language Models](https://www.mdpi.com/2076-3417/15/2/586/pdf?version=1736429302)

- **分类方式**：按 **硬件平台类型**（FPGA/CPU-GPU/ASIC/存内计算）四大类组织，每类深入剖析加速器微架构与算法-硬件协同设计
- **覆盖子方向**：
  - `FPGA加速器` → MNNFast（列式流处理+零跳过+嵌入缓存，5.38×/6.54×能效）、FTRANS（块循环矩阵压缩+设计自动化，27×/81×能效）、MHA加速（脉动阵列+非线性函数优化，14.6×）、NPE（指令驱动+非线性向量单元，35×/6×能效）、列平衡块剪枝（CSB+BCSR混合稀疏，11×/2× vs GPU）、DFX（免汇编ISA+多FPGA模型并行，3.8×/4×能效）、OPU（可配置PE+动态数据流，15×/2.9×）、FlexRun（模块化GEMV+向量单元+自动设计空间探索，2.79×/2.59× vs GPU）、ODE混合（神经ODE压缩94.6%参数+QAT，12.8×/9.2×能效）
  - `GPU/CPU优化` → SoftMax分解重构（减少HBM访问，1.12×-1.65×）、LightSeq2（算子融合+混合精度+内存生命周期管理，1.4×-3.5×）、简化Transformer（去除残差连接/投影参数，15%参数减少+15%吞吐提升）、LLMA（无草稿模型推测解码，2×-3×）、UltraFastBERT（快速FFN替代→O(log n)复杂度，78×）
  - `ASIC加速器` → A³（近似候选选择+专用流水线，7×/11×能效）、ELSA（近似自注意力+硬件-软件协同，157×/1265×能效）、SpAtten（级联Token+头剪枝+渐进量化，347×/162× vs CPU/GPU，1193×/4059×能效）、Sanger（动态稀疏预测+可重构脉动阵列，22.7×/4.64×）、Energon（混合精度多轮过滤+动态稀疏，168×/8.7×，高达10000×能效）、H3D Transformer（CIM+TPU异构3D集成，2.6×-3.1× vs 7nm TPU）
  - `存内计算加速器` → ATT（ReRAM交叉开关+专用流水线，202× vs GPU）、ReTransformer（ReRAM矩阵乘法+存内SoftMax/查找表，23.21×/1086×能效）、iMCAT（Xbar+CAM+局部敏感哈希过滤，200×/41×能效）、X-Former（NVM投影引擎+CMOS注意力引擎混合，85×/7.5×能效）、Flash Memory推理（窗口化+行列捆绑，25×/5× vs CPU/GPU）、FlashAttention-3（Hopper GPU异步+TMA+warp专用化，1.5×-2.0×，FP8达1.2 PFLOPs）
  - `跨平台定量对比` → Table 1汇总30+加速器的年/技术/加速比/能效/基准平台；ASIC和存内计算可达3-4个数量级能效提升，FPGA在灵活性与实际可部署性间取得最优折中
- **核心洞察补充**：ASIC和存内计算在加速比（最高347× vs CPU）和能效（最高10000× vs CPU）上远超FPGA和GPU，但需要巨额流片投资且缺乏灵活性；FPGA无需流片即可定制架构，在数据中心现有硬件中即插即用；FlashAttention-3通过利用Hopper GPU的Tensor Core异步性和TMA，FP8精度下达到近1.2 PFLOPs/s；LLMA无需额外草稿模型即可实现推测解码，在检索和对话场景中2×-3×加速；FPGA方案（FlexRun/DFX）正走向自动设计空间探索和模块化架构，降低定制门槛
- **附带资源**：论文Table 1系统汇总30+加速器的技术节点、加速比、能效及对比基准，Figure 1可视化加速比vs能效的散点分布；配套开源仓库 [https://github.com/kachris/survey_HA_LLM](https://github.com/kachris/survey_HA_LLM)

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
| 1 | 📖 **Efficiently Integrate LLMs with Visual Perception** | 2025 | Information Fusion  `IF=15.5`| `训练范式`：单阶段 / 两阶段 / 直接适配 | 仅关注视觉模态，直接适配在极低参数量下可接近全微调性能；轻量级LLM+LoRA是资源受限场景的有效路径 |
| 2 | 📖 **A Survey of Token Compression for Efficient Multimodal LLMs** | 2026 | TMLR | `模态驱动`：图像 / 视频 / 音频 + `机制驱动`：Transformation/Similarity/Attention/Query | 首篇MLLM长上下文Token压缩系统综述；Token压缩与模型压缩在削减FLOPs上具有正交互补性 |
| 3 | 📖 **Efficient Multimodal Large Language Models: A Survey** | 2025 | Visual Intelligence | `效率维度`：架构/视觉/LLM/训练/数据 + `应用`：医学/文档/视频/自动驾驶/遥感 | 首篇系统综述高效MLLM全栈优化；视觉Token压缩是MLLM特有的核心瓶颈，轻量LLM+高效投影器+MoE调优是主流范式 |


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

### 3. Efficient Multimodal Large Language Models: A Survey (2025)
[![Paper](https://img.shields.io/badge/Journal-Vis.Intell.'25-blue)]()

[Efficient multimodal large language models: a survey](https://link.springer.com/content/pdf/10.1007/s44267-025-00099-6.pdf)

- **分类方式**：按 **MLLM效率全栈**（架构→高效视觉→高效LLM→训练→数据与基准→应用）六阶段组织，覆盖从模型设计到实际部署的完整链路
- **覆盖子方向**：
  - `架构设计` → 视觉编码器（CLIP/SigLIP/DINOv2/EVA/ViTamin多编码器融合BRAVE）、视觉-语言投影器（MLP/Q-Former/LDPv2/C-Abstractor/D-Abstractor/VSS-Mamba）、紧凑语言模型（Phi-2/Gemma/TinyLlama/Qwen）、视觉Token压缩（多视图输入LLaVA-UHD/InternLM-XComposer2-4KHD、Token处理LLaVA-PruMerge/SparseVLM/FastV/VTW、多尺度融合Mini-Gemini/S²-Wrapper、视觉专家MoVA/P2G、视频方法Elysium/VideoLLaVA）
  - `高效结构` → MoE（MoE-LLaVA/MM1-MoE）、Mamba（Cobra/VL-Mamba线性复杂度）、推测解码SPD、早退FastV/VTW
  - `高效视觉技术` → 紧凑架构（EfficientFormer/DynamicViT/SepViT/NASViT）、剪枝（结构化WDPruning/XPruner/非结构化CAP/DynamicViT/混合SPViT/ViT-Slim）、知识蒸馏（同构DeiT/TinyViT/MiniViT/异构DearKD/CiT）、量化（PTQ：PTQ4ViT/APQ-ViT/NoisyQuant；QAT：Quantformer/Q-ViT/BiViT/BinaryViT；硬件感知：GPU 2:4稀疏量化/FPGA Auto-ViT-Acc）
  - `高效LLM技术` → 注意力优化（GQA/MQA/Funnel-Transformer/Set Transformer/核方法/低秩近似）、替代架构（MoE：GShard/Switch Transformer；RWKV线性注意力/Mamba SSM）、PEFT（LoRA/DyLoRA/LoRA-FA/(IA)³）、全参数微调（LOMO/MeZO内存优化）、量化（PTQ：GPTQ；QAT：AWQ）
  - `训练策略` → 参数高效预训练（冻结vs解冻权衡，TinyLLaVA/VILA/ShareGPT4V/Idefics2多阶段课程）、指令微调（LaVIN MMA轻量适配器/HyperLLaVA动态调优）、训练阶段重构（SPHINX-X单阶段统一/Cobra省略预对齐、TinyGPT-V四阶段课程）、PEFT迁移（EAS/MemVP视觉提示注入FFN）
  - `数据与基准` → 预训练数据（CC3M, LAION-5B, ShareGPT4V, MMC4）、指令微调数据、表5（22个模型×14个基准性能对比）
  - `应用` → 生物医学（Med-MoE/LLaVA-Rad）、文档理解（TinyChart/TextHawk/HRVDA/Monkey）、视频理解（mPLUG-video/Video-LLaVA/LLaMA-VID/MA-LMM记忆增强）、自动驾驶（DriveGPT4/Dolphins）、遥感（GeoLLaVA/TinyRS-R1）
- **核心洞察补充**：高效MLLM不能简单归结为高效LLM，需解决三个独特挑战：视觉-语言对齐、Transformer对视觉token的二次计算成本、联合模态优化；紧凑LLM主干（Phi-2, Gemma-2b）配合轻量投影器（LDPv2）是移动端部署的有效路径；视觉Token压缩（多视图、Token处理、多尺度融合）是处理高分辨率/长视频的关键；MoE（MoE-LLaVA）和Mamba（Cobra, VL-Mamba）是替代Transformer的有前景架构；ViTamin-XL（436M参数）以1/10参数量超越EVA-E（4.4B）的ImageNet零样本性能（82.9% vs 82.0%），证明轻量视觉编码器的潜力。
- **附带资源**：论文Table 1汇总20+主流高效MLLM的架构配置（视觉编码器/LLM/投影器/分辨率），Table 3-4系统整理预训练和指令微调数据集，Table 5对比22个高效MLLM与13个大型MLLM在14项VL基准上的性能；配套持续更新的GitHub仓库 [https://github.com/lijiannuit/Efficient-Multimodal-LLMs-Survey](https://github.com/lijiannuit/Efficient-Multimodal-LLMs-Survey)

<br>
</details>

---

<p align="center">
  <sub>⭐ 持续更新中 · 欢迎提交 Issue 或 PR 补充最新综述 ⭐</sub>
</p>
