# 📚 Awesome Efficient Large Language Models: From Architecture Design to Inference Systems

<div align="center">

[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Papers](https://img.shields.io/badge/Papers-400+-blue.svg)](.)
[![Last Update](https://img.shields.io/badge/Last%20Update-April%202026-brightgreen)](.)

**A curated literature collection for Efficient Large Language Models (LLMs).**  
*Surveys, architectures, compression, inference, training, routing, benchmarks, and tools.*

</div>

---

## 📌 Overview

`SnowSurvey4EfficientLLM` is a systematic literature repository focusing on **efficiency in Large Language Models** (LLMs). It covers the entire lifecycle of LLM efficiency – from architectural innovations and model compression to inference acceleration, training optimization, routing strategies, evaluation benchmarks, and open‑source tooling.

This repository is designed for:
- **Researchers** looking for a structured entry point into efficient LLM literature.
- **Engineers** seeking practical optimization techniques and production‑ready tools.
- **Students** wanting to understand the landscape of LLM efficiency.

---

## 🔗 Full List
- [Surveys](00-Surveys.md)
- [Architecture-Optimization](01-Architecture.md)

---

## 📂 Repository Structure

```text
Efficient-LLM-Literature/
├── 00-Surveys/                      # 综述（含Benchmark综述）
│   ├── General-Surveys/             # 通用效率综述
│   └── Domain-Specific/             # 长文本/多模态/代码等
│
├── 01-Architecture-Optimization/    # 架构级优化
│   ├── Attention-Mechanisms/        # GQA, MQA, Sliding Window, etc.
│   ├── Alternative-Architectures/   # Mamba, RWKV, Hyena, etc.
│   ├── Mixture-of-Experts/          # MoE routing, load balancing
│   └── Other/                       # FFN-and-Activation-Optimization: SwiGLU, Parallel, etc.
│
├── 02-Model-Compression/            # 模型压缩
│   ├── Quantization/                # GPTQ, AWQ, SmoothQuant, LLM.int8()
│   ├── Pruning-Sparsity/            # SparseGPT, Wanda, 半结构化稀疏
│   ├── Knowledge-Distillation/      # MiniLLM, GKD, 上下文蒸馏
│   ├── Low-Rank-Decomposition/      # LoRA及其变体, SVD等
│   └── Neural-Architecture-Search/  # （可选）LLM专用NAS
│
├── 03-Inference-Optimization/       # 推理阶段优化（运行时）
│   ├── KV-Cache-Compression/        # PagedAttention, RadixAttention, KV缓存压缩
│   ├── Speculative-Decoding/        # Medusa, Eagle, Lookahead
│   ├── FlashAttention/              # FA1/2/3, 高效注意力内核
│   ├── System-Level-Serving/        # vLLM, TensorRT-LLM, SGLang, 调度
│   └── Text-Compression/            # 提示压缩, Prompt压缩
│
├── 04-Training-Optimization/        # 训练阶段优化
│   ├── Efficient-Pretraining/       # 数据筛选, 模型并行, MeZO等
│   └── Efficient-Finetuning/        # LoRA, Prefix Tuning, P-Tuning, QLoRA
│
├── 05-Routing-and-Cascade/          # 多模型路由与级联
│
├── 06-Multimodal/    # 多模态
│
└── 07-Code-and-Tools/               # 开源代码与工具库
    ├── Inference-Engines/           # vLLM, TensorRT-LLM, llama.cpp
    ├── Optimization-Libraries/      # FlashAttention, SpecForge, unsloth
    └── Awesome-Lists/               # Awesome-LLM-Inference等
```

Each subdirectory contains:

- A `README.md` describing the sub‑topic.
- A curated list of papers (title, authors, venue, year, abstract, links).
- Where available, links to **official code** or **third‑party implementations**.

---

## 🚀 How to Use This Repository

### For Readers
1. **Start with `00-Surveys/General-Surveys/`** to get a broad overview of efficient LLM research.
2. **Drill down** into specific areas of interest (e.g., `02-Model-Compression/Quantization/`).
3. **Check `06-Benchmarks-and-Evaluation/`** to understand how different techniques are measured.
4. **Explore `07-Code-and-Tools/`** for practical implementations and serving engines.

### For Contributors
We welcome additions, corrections, and suggestions. Please follow these guidelines:
- Add new papers in the appropriate subdirectory (or create a new subdirectory if justified).
- Use the standard paper entry template (see `_TEMPLATE.md` in the root).
- Ensure information is accurate (title, authors, venue, year, DOI/arXiv link).
- Submit a **Pull Request** or open an **Issue** for discussion.

> 📝 **Maintenance**: This repository is updated monthly. Last major update: April 2026.

---

## 📄 License
The metadata (paper titles, authors, links, organization) of this repository is licensed under the MIT License.
Paper copyrights and content belong to their respective authors and publishers.

## 🙏 Acknowledgements
- All researchers who have contributed to the efficient LLM field.
- Open‑source communities: Hugging Face, vLLM, MLC-LLM, TensorRT-LLM, and many others.
- https://github.com/horseee/Awesome-Efficient-LLM

## 📧 Contact
For questions, suggestions, or collaboration, please open an Issue or contact a1311965600@gmial.com.
