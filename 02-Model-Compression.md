<p align="center">
  <img src="https://img.shields.io/badge/Papers-11-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 📦 Model Compression of LLM

> **涵盖领域**: 量化 (Quantization) · 剪枝 (Pruning) · 知识蒸馏 (Knowledge Distillation) · 低秩分解 (Low-Rank Approximation)
> **核心目标**: 降低LLM的存储占用和计算开销，使其能在资源受限环境中高效部署

---

## 📖 目录

- [📊 本领域综述论文](#-survey)
- [🔥 本领域经典论文之量化 (Quantization)](#-quantization)
- [🏆 本领域经典论文之剪枝 (Pruning)](#-pruning)
- [🥇 本领域经典论文之知识蒸馏 (Knowledge Distillation)](#-kd)
- [🎯 本领域经典论文之低秩分解 (Low-Rank Approximation)](#-lowrank)

---

<a id="survey"></a>
## 📊 本领域综述论文

> **说明**: 本领域综述专注于模型压缩技术，覆盖量化、剪枝、知识蒸馏、低秩分解等方向。

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | **A Survey on Model Compression for Transformer-Based LLMs** | 2026 | IEEE TETCI `IF=11.8` | `压缩方法`：剪枝/量化/蒸馏/低秩分解 + `新视角`：KV Cache压缩/NAS | 首篇将KV Cache压缩与NAS纳入LLM模型压缩统一框架的综述；混合压缩是工业落地主流范式 |
| 2 | **A Survey of Model Compression Techniques: Past, Present, and Future** | 2025 | Front. Rob. AI `IF=3.0` | `压缩总论`：量化/剪枝/蒸馏/低秩分解 + 轻量级架构设计(NAS/Transformer变体) | 横跨CV与NLP的压缩全景综述，从LeNet到LLM的通透演进梳理，包含未来趋势（LLM压缩/硬件感知/AutoML） |
| 3 | **A Survey on Model Compression for Large Language Models** | 2024 | TACL `IF=6.9` | `量化(QAT/PTQ)` / `剪枝(非结构化/结构化/半结构化)` / `KD(黑盒/白盒)` / `低秩分解` | 聚焦压缩技术本身，按压缩类型（量化/剪枝/KD/低秩）系统梳理，附带标准化指标与基准评估体系 |
| 4 | **A Survey of Low-Bit Large Language Models: Basics, Systems, and Algorithms** | 2025 | Neural Networks `IF=6.3` | `基础(数据格式/粒度/动静)` / `系统(框架/硬件支持)` / `算法(QAT/PTQ/等效变换/补偿/混合精度)` 三维度 | 迄今最全面的LLM低位量化综述，首创基础-系统-算法三维框架，覆盖量化全技术栈从底层格式到上层部署 |
| 5 | **Low-bit Model Quantization for Deep Neural Networks: A Survey** | 2025 | arXiv | `量化核心`：8大类×24子类（近五年方法的精细分类） | 对近五年低比特量化方法进行了最精细的类别划分，提供了覆盖最新进展的分类学框架 |
| 6 | **Art and Science of Quantizing Large-Scale Models: A Comprehensive Overview** | 2024 | arXiv | `量化范式`：PTQ(30+算法) + QAT(4类) + KV Cache压缩 + KD + 极端低比特 | 量化领域最深度的综述之一；详尽推导LLM-QAT/SmoothQuant/AWQ/GPTQ等核心公式，覆盖从二值网络到LLM量化的完整演进 |
| 7 | **Contemporary Advances in Neural Network Quantization: A Survey** | 2024 | IJCNN | `量化技术体系`：QAT/PTQ/混合精度/硬件加速，CNN→Transformer→LLM | 系统梳理神经网络量化从传统CNN到LLM时代的完整演进，重点分析Transformer量化中激活离群值问题与混合精度策略 |
| 8 | **A Comprehensive Study on Quantization Techniques for Large Language Models** | 2024 | ICAIRC | `权重量化`(NF4/GPTQ/SpQR/AWQ) + `激活量化`(SmoothQuant/动态量化) + `混合精度`(QLoRA) + `LLM-QBench基准` | 提出LLM-QBench统一评估基准，对6种主流量化技术在LLaMA/OPT/BLOOM/Falcon上标准化评测；发现仅权重量化(4-bit)可保留99%精度但需激活量化才能实现实际推理加速 |
| 9 | **A Comprehensive Review of Binary Neural Network** | 2023 | Artificial Intelligence Review `IF=13.9` | `二值网络总论`：BNN基础/训练/架构/应用全景 | 从二值网络视角理解极致量化，为LLM极端压缩(1-bit)提供理论和方法论基础 |
| 10 | **A Survey of Quantization Methods for Efficient Neural Network Inference** | 2021 | arXiv | `量化基础`：PTQ/QAT/混合精度/硬件感知 | 量化领域经典入门综述，系统阐述从基础量化原理到硬件部署的完整知识体系 |
| 11 | **Pruning and Quantization for Deep Neural Network Acceleration: A Survey** | 2021 | Neurocomputing `IF=6.5` | `剪枝+量化联合`：结构化/非结构化/量化感知/硬件加速 | 系统整合剪枝与量化两大压缩路线，覆盖从算法原理到硬件加速的端到端优化流程 |

---

<a id="quantization"></a>
## 🔥 本领域经典论文之量化 (Quantization)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|

---

<a id="pruning"></a>
## 🏆 本领域经典论文之剪枝 (Pruning)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|

---

<a id="kd"></a>
## 🥇 本领域经典论文之知识蒸馏 (Knowledge Distillation)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|

---

<a id="lowrank"></a>
## 🎯 本领域经典论文之低秩分解 (Low-Rank Approximation)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|

---

<p align="center">
  <sub>⭐ 持续更新中 · 缺少的图片精读之后会补 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
