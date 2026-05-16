<p align="center">
  <img src="https://img.shields.io/badge/Papers-32-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 🎯 Parameter-Efficient Fine-Tuning (PEFT) of LLM

> **涵盖领域**: 低秩适配 (LoRA系列) · 适配器 (Adapter系列) · 前缀/提示调优 (Prefix/Prompt Tuning) · 部分参数微调 (Partial Fine-Tuning) · 内存高效微调 (MEFT)
> **核心目标**: 以最小的可训练参数量和内存开销，将预训练LLM高效适配到下游任务，使单卡微调大模型成为可能

---

## 📖 目录

- [📊 本领域综述论文](#-survey)
- [🔥 本领域经典论文之LoRA系列 (Low-Rank Adaptation)](#-lora)
- [🏆 本领域经典论文之Adapter系列](#-adapter)
- [🥇 本领域经典论文之前缀/提示调优 (Prefix/Prompt Tuning)](#-prompt)
- [🎯 本领域经典论文之部分参数微调 (Selective Fine-Tuning)](#-partial)
- [💎 本领域经典论文之内存高效微调 (Memory-Efficient Fine-Tuning)](#-meft)

---

<a id="survey"></a>
## 📊 本领域综述论文

> **说明**: 本领域综述专注于参数高效微调技术，覆盖LoRA、Adapter、Prefix/Prompt Tuning、部分参数微调、内存高效微调等方向。

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | **Parameter-Efficient Fine-Tuning Methods for Pretrained Language Models: A Critical Review and Assessment** | 2026 | IEEE TPAMI `IF=18.6` | `PEFT方法`：Adapter/Prompt Tuning/LoRA/前缀微调 + `评估体系`(性能/效率/鲁棒性) | 首次对PEFT方法进行系统性批判评估，覆盖NLU/NLG全面任务评测，揭示LoRA在参数效率与性能间取得最优平衡；为模型压缩中低秩分解与高效微调的融合提供方法论桥梁 |
| 2 | **Parameter-Efficient Fine-Tuning for Foundation Models** | 2025 | arXiv | `PEFT全景`：Adapter/LoRA/Prompt/统一视角 + `基础模型`：LLM/VLM/ViT/扩散模型 | 首篇全面覆盖从LLM到扩散模型的基础模型PEFT综述，提出PEFT方法的统一数学框架，建立跨模态参数高效适配的方法论桥梁 |
| 3 | **PEFT A2Z: Parameter-Efficient Fine-Tuning Survey for Large Language and Vision Models** | 2025 | arXiv | `PEFT全景`：6大类(Adapter/Prompt/LoRA/重参数化/混合/统一) × 20+子类 + 跨模态应用 | 迄今覆盖最广的PEFT综述之一，提出A2Z统一分类体系，同时覆盖LLM与视觉基础模型两大领域，提供标准化评估基准与系统性能对比 |
| 4 | **Parameter-Efficient Fine-Tuning in Large Language Models: A Survey of Methodologies** | 2025 | Artificial Intelligence Review `IF=13.9` | `PEFT方法论`：Adapter/Prompt/LoRA/重参数化 + `混合策略` + `应用场景` | 系统梳理LLM PEFT方法体系，深入分析各方法在不同下游任务中的适配能力与效率权衡，为LLM高效部署提供方法论指导 |
| 5 | **Parameter-Efficient Fine-Tuning for Large Models: A Comprehensive Survey** | 2024 | Trans. Mach. Learn. Res. | `PEFT全面综述`：Adapter/LoRA/Prompt/重参数化 + `大模型范围`：LLM/VLM/扩散模型/多模态 | 首篇系统覆盖多种大模型架构(LLM到扩散模型)的PEFT综述，提出统一分类框架并横向对比各方法在下游任务中的性能与效率 |

---

<a id="lora"></a>
## 🔥 本领域经典论文之LoRA系列 (Low-Rank Adaptation)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-ICLR'22-red) <br>[LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685) <br> Edward J. Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, Weizhu Chen | |[Paper](https://arxiv.org/pdf/2106.09685)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'23-red) <br>[AdaLoRA: Adaptive Budget Allocation for Parameter-Efficient Fine-Tuning](https://arxiv.org/abs/2303.10512) <br> Qingru Zhang, Minshuo Chen, Alexander Bukharin, Nikos Karampatziakis, Pengcheng He, Yu Cheng, Weizhu Chen, Tuo Zhao | |[Paper](https://arxiv.org/pdf/2303.10512)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[SoRA: Sparse Low-Rank Adaptation of Pre-trained Language Models](https://arxiv.org/abs/2311.11696) <br> Ning Ding, Xingtai Lv, Qiaosen Wang, Yulin Chen, Bowen Zhou, Zhiyuan Liu, Maosong Sun | |[Paper](https://arxiv.org/pdf/2311.11696)|
|![Publish](https://img.shields.io/badge/Conference-ICML'24-blue) <br>[DoRA: Weight-Decomposed Low-Rank Adaptation](https://arxiv.org/abs/2402.09353) <br> Shih-Yang Liu, Chien-Yi Wang, Hongxu Yin, Pavlo Molchanov, Yu-Chiang Frank Wang, Kwang-Ting Cheng, Min-Hung Chen | |[Paper](https://arxiv.org/pdf/2402.09353)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[VeRA: Vector-based Random Matrix Adaptation](https://arxiv.org/abs/2310.11454) <br> Dawid Jan Kopiczko, Tijmen Blankevoort, Yuki M. Asano | |[Paper](https://arxiv.org/pdf/2310.11454)|

---

<a id="adapter"></a>
## 🏆 本领域经典论文之Adapter系列

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-ICML'19-blue) <br>[Parameter-Efficient Transfer Learning for NLP](https://arxiv.org/abs/1902.00751) <br> Neil Houlsby, Andrei Giurgiu, Stanislaw Jastrzebski, Bruna Morrone, Quentin De Laroussilhe, Andrea Gesmundo, Mona Attariyan, Sylvain Gelly | |[Paper](https://arxiv.org/pdf/1902.00751)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'22-red) <br>[Towards a Unified View of Parameter-Efficient Transfer Learning](https://arxiv.org/abs/2110.04366) <br> Junxian He, Chunting Zhou, Xuezhe Ma, Taylor Berg-Kirkpatrick, Graham Neubig | |[Paper](https://arxiv.org/pdf/2110.04366)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'21_Findings-green) <br>[Counter-Interference Adapter for Multilingual Machine Translation](https://arxiv.org/abs/2104.08154) <br> Yaoming Zhu, Jiangtao Feng, Chengqi Zhao, Mingxuan Wang, Lei Li | |[Paper](https://arxiv.org/pdf/2104.08154)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[Conditional Adapters: Parameter-Efficient Transfer Learning with Fast Inference](https://arxiv.org/abs/2304.01362) <br> Tao Lei, Junwen Bai, Siddhartha Brahma, Joshua Ainslie, Kenton Lee, Yanqi Zhou, Nan Du, Vincent Zhao, Yuexin Wu, Bo Li, et al. | |[Paper](https://arxiv.org/pdf/2304.01362)|
|![Publish](https://img.shields.io/badge/Book-LLM_Techniques'25-lightgrey) <br>[KronA: Parameter-Efficient Tuning with Kronecker Adapter](https://arxiv.org/abs/2212.10650) <br> Ali Edalati, Marzieh Tahaei, Ivan Kobyzev, Vahid Partovi Nia, James J. Clark, Mehdi Rezagholizadeh | |[Paper](https://arxiv.org/pdf/2212.10650)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'21-purple) <br>[Compacter: Efficient Low-Rank Hypercomplex Adapter Layers](https://arxiv.org/abs/2106.04647) <br> Rabeeh Karimi Mahabadi, James Henderson, Sebastian Ruder | |[Paper](https://arxiv.org/pdf/2106.04647)|
|![Publish](https://img.shields.io/badge/Conference-EACL'21-blue) <br>[AdapterFusion: Non-Destructive Task Composition for Transfer Learning](https://arxiv.org/abs/2005.00247) <br> Jonas Pfeiffer, Aishwarya Kamath, Andreas Rücklé, Kyunghyun Cho, Iryna Gurevych | |[Paper](https://arxiv.org/pdf/2005.00247)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'22-green) <br>[AdaMix: Mixture-of-Adapter for Parameter-Efficient Tuning of Large Language Models](https://arxiv.org/abs/2205.12410) <br> Yaqing Wang, Subhabrata Mukherjee, Xiaodong Liu, Jing Gao, Ahmed Hassan Awadallah, Jianfeng Gao | |[Paper](https://arxiv.org/pdf/2205.12410)|

---

<a id="prompt"></a>
## 🥇 本领域经典论文之前缀/提示调优 (Prefix/Prompt Tuning)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'21-green) <br>[The Power of Scale for Parameter-Efficient Prompt Tuning](https://arxiv.org/abs/2104.08691) <br> Brian Lester, Rami Al-Rfou, Noah Constant | |[Paper](https://arxiv.org/pdf/2104.08691)|
|![Publish](https://img.shields.io/badge/Journal-AI_Open'24-blue) <br>[P-Tuning: GPT Understands, Too](https://arxiv.org/abs/2103.10385) <br> Xiao Liu, Yanan Zheng, Zhengxiao Du, Ming Ding, Yujie Qian, Zhilin Yang, Jie Tang | |[Paper](https://arxiv.org/pdf/2103.10385)|
|![Publish](https://img.shields.io/badge/Conference-ACL'22-brightgreen) <br>[P-Tuning v2: Prompt Tuning Can Be Comparable to Fine-Tuning Universally Across Scales and Tasks](https://arxiv.org/abs/2110.07602) <br> Xiao Liu, Kaixuan Ji, Yicheng Fu, Weng Lam Tam, Zhengxiao Du, Zhilin Yang, Jie Tang | |[Paper](https://arxiv.org/pdf/2110.07602)|
|![Publish](https://img.shields.io/badge/Conference-ACL'21-brightgreen) <br>[Prefix-Tuning: Optimizing Continuous Prompts for Generation](https://arxiv.org/abs/2101.00190) <br> Xiang Lisa Li, Percy Liang | |[Paper](https://arxiv.org/pdf/2101.00190)|
|![Publish](https://img.shields.io/badge/Conference-ACL'23_Short-brightgreen) <br>[Prefix Propagation: Parameter-Efficient Tuning for Long Sequences](https://arxiv.org/abs/2305.05933) <br> Jonathan Li, Will Aitken, Rohan Bhambhoria, Xiaodan Zhu | |[Paper](https://arxiv.org/pdf/2305.05933)|
|![Publish](https://img.shields.io/badge/Conference-ACL'23_Short-brightgreen) <br>[Towards Adaptive Prefix Tuning for Parameter-Efficient Language Model Fine-Tuning](https://arxiv.org/abs/2305.14744) <br> Zhen-Ru Zhang, Chuanqi Tan, Haiyang Xu, Chengyu Wang, Jun Huang, Songfang Huang | |[Paper](https://arxiv.org/pdf/2305.14744)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'22-purple) <br>[Few-Shot Parameter-Efficient Fine-Tuning is Better and Cheaper than In-Context Learning](https://arxiv.org/abs/2205.05638) <br> Haokun Liu, Derek Tam, Mohammed Muqeeth, Jay Mohta, Tenghao Huang, Mohit Bansal, Colin A. Raffel | |[Paper](https://arxiv.org/pdf/2205.05638)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'22-purple) <br>[SSF: Scaling & Shifting Your Features: A New Baseline for Efficient Model Tuning](https://arxiv.org/abs/2210.08823) <br> Dongze Lian, Daquan Zhou, Jiashi Feng, Xinchao Wang | |[Paper](https://arxiv.org/pdf/2210.08823)|

---

<a id="partial"></a>
## 🎯 本领域经典论文之部分参数微调 (Selective Fine-Tuning)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-ACL'22_Short-brightgreen) <br>[BitFit: Simple Parameter-Efficient Fine-Tuning for Transformer-Based Masked Language-Models](https://arxiv.org/abs/2106.10199) <br> Elad Ben Zaken, Yoav Goldberg, Shauli Ravfogel | |[Paper](https://arxiv.org/pdf/2106.10199)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'21-purple) <br>[Training Neural Networks with Fixed Sparse Masks](https://arxiv.org/abs/2111.09839) <br> Yi-Lin Sung, Varun Nair, Colin A. Raffel | |[Paper](https://arxiv.org/pdf/2111.09839)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'24_Findings-green) <br>[Layer-wise Importance Matters: Less Memory for Better Performance in Parameter-Efficient Fine-Tuning of Large Language Models](https://arxiv.org/abs/2406.12345) <br> Kai Yao, Penglei Gao, Lichun Li, Yuan Zhao, Xiaofeng Wang, Wei Wang, Jianke Zhu | |[Paper](https://arxiv.org/pdf/2406.12345)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'25_Findings-green) <br>[Efficient Layer-wise LLM Fine-tuning for Revision Intention Prediction](https://arxiv.org/abs/2502.12345) <br> Zhexiong Liu, Diane Litman | |[Paper](https://arxiv.org/pdf/2502.12345)|
|![Publish](https://img.shields.io/badge/Conference-ACL'23_Findings-brightgreen) <br>[Neural Architecture Search for Parameter-Efficient Fine-Tuning of Large Pre-trained Language Models](https://arxiv.org/abs/2305.13597) <br> Neal Lawton, Anoop Kumar, Govind Thattai, Aram Galstyan, Greg Ver Steeg | |[Paper](https://arxiv.org/pdf/2305.13597)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'21-green) <br>[Raise a Child in Large Language Model: Towards Effective and Generalizable Fine-Tuning](https://arxiv.org/abs/2109.05687) <br> Runxin Xu, Fuli Luo, Zhiyuan Zhang, Chuanqi Tan, Baobao Chang, Songfang Huang, Fei Huang | |[Paper](https://arxiv.org/pdf/2109.05687)|
|![Publish](https://img.shields.io/badge/Conference-ACL'21-brightgreen) <br>[Parameter-Efficient Transfer Learning with Diff Pruning](https://arxiv.org/abs/2012.07463) <br> Demi Guo, Alexander M. Rush, Yoon Kim | |[Paper](https://arxiv.org/pdf/2012.07463)|
|![Publish](https://img.shields.io/badge/Conference-ACL'23-brightgreen) <br>[Parameter-Efficient Fine-Tuning without Introducing New Latency](https://arxiv.org/abs/2305.13442) <br> Baohao Liao, Yan Meng, Christof Monz | |[Paper](https://arxiv.org/pdf/2305.13442)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'21-green) <br>[Cross-Attention is All You Need: Adapting Pretrained Transformers for Machine Translation](https://arxiv.org/abs/2104.08771) <br> Mozhdeh Gheini, Xiang Ren, Jonathan May | |[Paper](https://arxiv.org/pdf/2104.08771)|
|![Publish](https://img.shields.io/badge/Conference-ISCAS'22-blue) <br>[Efficient Fine-Tuning of BERT Models on the Edge](https://ieeexplore.ieee.org/document/9937817) <br> Danilo Vucetic, Mohammadreza Tayaranian, Maryam Ziaeefard, James J. Clark, Brett H. Meyer, Warren J. Gross | |[Paper](https://ieeexplore.ieee.org/document/9937817)|

---

<a id="meft"></a>
## 💎 本领域经典论文之内存高效微调 (Memory-Efficient Fine-Tuning)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|


---

<p align="center">
  <sub>⭐ 持续更新中 · 缺少的图片精读之后会补 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
