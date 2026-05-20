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
- [Model-Compression](02-Model-Compression.md)
- [Parameter-Efficient-Finetuning](03-Parameter-Efficient-Finetuning.md)
- [Inference-Optimization](04-Inference-Optimization.md)

---

## 📂 Repository Structure

```text
Efficient-LLM-Literature/
├── 00-Surveys/                      
│   ├── General-Surveys/             
│   └── Domain-Specific/           
│
├── 01-Architecture-Optimization/   
│   ├── Attention-Mechanisms/      
│   ├── Mixture-of-Experts/          
│   ├── Alternative-Architectures/   
│   └── Other/                      
│
├── 02-Model-Compression/          
│   ├── Quantization/               
│   ├── Pruning-Sparsity/            
│   ├── Knowledge-Distillation/     
│   ├── Low-Rank-Decomposition/     
│   └── Neural-Architecture-Search/  
│
├── 03-Parameter-Efficient-Finetuning/       
│   ├── Adapter-based-Tuning/
│   ├── Prefix/Prompt-Tuning/
│   ├── Selective-Tuning/
│   ├── LoRA/   
│   └── Other/
│
├── 04-Inference-Optimization/      
│   ├── Speculative-Decoding/         
│   ├── Prompt-Compression/
│   ├── KV-Cache-Compression/   
│   └── KV-Cache-Sparsification/          
│
├── 05-Technique Co-optimization/      
│   ├── 0/         
│   ├── 0/
│   ├── 0/   
│   └── 0/
└── 
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
