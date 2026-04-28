## 001-General-Surveys

### Efficient Large Language Models: A Survey
- ⭐⭐⭐ [Efficient Large Language Models: A Survey](https://arxiv.org/abs/2312.03863)
  - *Wan et al., arXiv, 2023 (持续更新)*
  - **分类方式**：按 **模型中心 / 数据中心 / 框架中心** 三个视角组织
  - **覆盖子方向**：
    - `模型压缩` → 量化（GPTQ, AWQ, SmoothQuant）、剪枝（SparseGPT, Wanda）、蒸馏、低秩分解（LoRA, QLoRA）
    - `高效架构` → 高效注意力（GQA, MQA, FlashAttention）、MoE（Mixtral, DeepSpeed-MoE）、替代架构（Mamba, RWKV）
    - `推理优化` → KV Cache 管理（PagedAttention, StreamingLLM）、投机解码（Medusa, Eagle）、系统优化（vLLM, TensorRT-LLM）
    - `训练优化` → 高效微调（LoRA 系列, IA3）、分布式训练（ZeRO, FSDP）、混合精度训练
  - **核心结论/洞察**：算法-硬件-框架协同设计是进一步提升 LLM 效率的关键，单一维度优化已接近瓶颈
  - **附带资源**：[GitHub 持续更新](https://github.com/AIoT-MLSys-Lab/Efficient-LLMs-Survey)

---

## 002-Domain-Specific

### VLLM

#### Efficiently integrate large language models with visual perception: a survey from the training paradigm perspective ⭐⭐⭐⭐ (A–)
  - Ma et al., Information Fusion, 2025 (IF=15.5)
  - **分类方式**：按```训练范式```组织：单阶段调优（Single-stage Tuning） / 两阶段调优（Two-stage Tuning） / 直接适配（Direct Adaptation）
  - **覆盖子方向**：
    - 单阶段调优：仅训练模态集成器（MI），利用LLM零样本/少样本能力 → 代表：Resampler、Q-Former、线性投影
    - 两阶段调优：预训练+指令微调/RLHF → 参数效率策略：仅训练MI、引入重参数化（LoRA/DoRA）、使用轻量级LLM（Phi/MobileLLaMA）
    - 直接适配：跳过预训练，下游任务直接微调MI → 常用瓶颈适配器、注意力适配器、度自适应前缀
    - 模态集成器：外部集成器（注意力抽象器、密集投影器、卷积抽象器、VSS抽象器）+ 内部集成器（度自适应前缀、瓶颈适配器、注意力适配器、单模态线性适配器）
    - 训练策略：多任务学习、指令微调、RLHF（含PPO）
    - 评测基准：传统（VQAv2, GQA, COCO Caption，TextVQA）+ 先进（MME, MMBench, MM-Vet, POPE）
  - **核心结论/洞察**：引入微调阶段（两阶段调优）通常提升性能，但部分两阶段模型因数据或参数量不足反而不如单阶段/直接适配；直接适配在极低参数量下可接近全微调性能；轻量级LLM+LoRA是资源受限场景的有效路径；未来需解决幻觉、细粒度视觉理解、泛化能力三大挑战。
  - **附带资源**：[论文](https://arxiv.org/pdf/2502.01524)，无公开GitHub库，但论文中Table 8总结了33个两阶段调优模型的代码可用性（LLaVA、MiniGPT4、mPLUG-Owl等）；实验部分提供了Direct Adaptation的复现代码（基于LST仓库）。
---


<p align="center">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-brightgreen?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-blue?style=flat-square" alt="PRs Welcome">
</p>

# 📚 Awesome LLM Efficiency & Multimodal Surveys

> 一份高质量、持续更新的**大语言模型（LLM）效率优化**与**多模态大模型（VLLM）**综述导航。
> 致力于为研究者提供清晰的分类脉络、核心洞察与代码资源。

---

## 📖 目录

- [通用综述 (General Surveys)](#001-general-surveys)
- [领域特化综述 (Domain-Specific)](#002-domain-specific)
  - [视觉大语言模型 (VLLM)](#vllm)

---

## 001-General-Surveys

### ⚡ Efficient Large Language Models: A Survey
[![arXiv](https://img.shields.io/badge/arXiv-2312.03863-b31b1b.svg)](https://arxiv.org/abs/2312.03863)
[![GitHub](https://img.shields.io/badge/GitHub-持续更新-181717?logo=github)](https://github.com/AIoT-MLSys-Lab/Efficient-LLMs-Survey)

| 项目 | 内容 |
|------|------|
| **作者** | *Wan et al., arXiv, 2023 (持续更新)* |
| **目前评级** | ⭐⭐⭐ |
| **分类方式** | **模型中心** / **数据中心** / **框架中心** 三层视角 |
| **覆盖子方向** | **模型压缩:** 量化（GPTQ, AWQ, SmoothQuant）、剪枝（SparseGPT, Wanda）、蒸馏、低秩分解（LoRA, QLoRA）<br> **高效架构:** 高效注意力（GQA, MQA, FlashAttention）、MoE（Mixtral, DeepSpeed-MoE）、替代架构（Mamba, RWKV）<br> **推理优化:** KV Cache管理（PagedAttention, StreamingLLM）、投机解码（Medusa, Eagle）、系统优化（vLLM, TensorRT-LLM）<br> **训练优化:** 高效微调（LoRA系列, IA3）、分布式训练（ZeRO, FSDP）、混合精度训练 |
| **核心洞察** | 🔑 算法-硬件-框架的**协同设计**是跨越LLM效率瓶颈的唯一路径，单一维度的优化潜力已趋极限。 |
| **资源信息** | 附带持续更新的 [GitHub仓库](https://github.com/AIoT-MLSys-Lab/Efficient-LLMs-Survey)。 |

---

## 002-Domain-Specific

### 🎨 VLLM (视觉大语言模型)

#### Efficiently Integrate Large Language Models with Visual Perception: A Survey from the Training Paradigm Perspective

[![Paper](https://img.shields.io/badge/Paper-Information%20Fusion%202025-blue?logo=googlescholar&logoColor=white)](https://arxiv.org/pdf/2502.01524)
[![Impact Factor](https://img.shields.io/badge/IF-15.5-ff69b4)]()

| 项目 | 内容 |
|------|------|
| **作者** | *Ma et al., Information Fusion, 2025 (IF=15.5)* |
| **目前评级** | ⭐⭐⭐⭐ (卓越的选择) |
| **分类方式** | 按 **`训练范式`** 组织：<br>① 单阶段调优 (Single-stage Tuning) <br>② 两阶段调优 (Two-stage Tuning) · **[当前主流]** <br>③ 直接适配 (Direct Adaptation) · **[新兴极简路线]** |
| **覆盖子方向** | **范式与策略:** <br>• `单阶段调优`：仅训练模态集成器（MI），零样本/少样本推理。代表：Resampler, Q-Former, 线性投影。<br>• `两阶段调优`：预训练 + 指令微调/RLHF。参数效率策略包括：仅训练MI、重参数化（LoRA/DoRA）、采用轻量级LLM（Phi/MobileLLaMA）。<br><br>**核心组件:** <br>• `模态集成器（MI）`：外部（注意力抽象器、密集投影器、卷积抽象器）| 内部（度自适应前缀、各类适配器）。<br>• `训练技巧`：多任务学习、指令微调、RLHF（含PPO）。<br><br>**评测:** <br>• `传统基准`：VQAv2, GQA, COCO Caption, TextVQA。<br>• `综合性基准`：MME, MMBench, MM-Vet, POPE。 |
| **核心洞察** | 🔑 **两阶段微调**通常带来性能提升，但若数据或模型规模不匹配，可能被更轻量的方案反超。<br>🎯 **直接适配**路径在参数量极低时，能够实现接近全参数微调的性能，极具潜力。<br>🧠 轻量级LLM + LoRA 是资源受限场景的**有效路径**。<br>⚠️ **三大待解挑战:** 幻觉抑制、细粒度视觉理解、跨场景泛化能力。 |
| **资源信息** | **代码复现:** 论文提供了基于LST仓库的`Direct Adaptation`实验代码。<br>**模型索引:** 文中 Table 8 详尽总结了33个主流两阶段模型（如LLaVA, MiniGPT4, mPLUG-Owl等）的代码可用性。 |

---

<p align="center">
  <sub>持续更新中 · 欢迎通过 Issue 或 PR 补充最新综述</sub>
</p>
