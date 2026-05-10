<p align="center">
  <img src="https://img.shields.io/badge/Papers-18-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 🏗️ Efficient Architecture of LLM

> **涵盖领域**: 高效注意力机制 · 稀疏专家架构(MoE) · Transformer替代架构(SSM/Linear Attention/ Hybrid)
> **核心目标**: 从架构层面降低Transformer的二次复杂度O(N²)和Feed-Forward Network内存带宽瓶颈

---

## 📖 目录

- [📊 本领域综述论文](#-survey)
- [🔥 本领域经典论文之Efficient Attention Mechanisms](#-efficentAttention)
- [🏆 本领域经典论文之Mixture of Experts](#-MoE)


---

<a id="survey"></a>
## 📊 本领域综述论文

> **说明**: 本领域综述专注于架构级效率优化，覆盖高效注意力、MoE稀疏激活、SSM/线性注意力等替代架构方向。（这个方向没有专有综述）

<!-- 
| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| 1 | **A Comprehensive Survey on Efficiency Optimization in LLMs: From Architecture Design to Synergistic Acceleration** | 2025 | KBS | `高效注意力` / `稀疏MoE` / `Transformer替代` 三类 | 首次将架构效率置于全生命周期优化框架，强调MoE+线性注意力的协同加速效应 |
---
-->

<a id="efficentAttention"></a>
## 🔥 本领域经典论文之Efficient Attention Mechanisms

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Paper-arXiv'19-b31b1b) <br>[Fast Transformer Decoding: One Write-Head is All You Need](https://arxiv.org/abs/1911.02150) <br> Noam Shazeer | |[Paper](https://arxiv.org/pdf/1911.02150)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[GQA: Training Generalized Multi-Query Transformer Models from Multi-Head Checkpoints](https://arxiv.org/abs/2305.13245) <br> Joshua Ainslie, James Lee-Thorp, Michiel de Jong, Yury Zemlyanskiy, Federico Lebrón, Sumit Sanghai |<img width="1002" alt="image" src="https://arxiv.org/html/2305.13245v3/extracted/5314337/images/gmq_architecture.png"> |[Paper](https://arxiv.org/pdf/2305.13245)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model](https://arxiv.org/abs/2405.04434) <br> DeepSeek-AI |<img width="1002" alt="image" src="https://arxiv.org/html/2405.04434v5/x4.png"> |[Paper](https://arxiv.org/pdf/2405.04434)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'19-b31b1b) <br> [Generating Long Sequences with Sparse Transformers](https://arxiv.org/abs/1904.10509) <br> Rewon Child, Scott Gray, Alec Radford, Ilya Sutskever | |[Paper](https://arxiv.org/pdf/1904.10509)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'20-b31b1b) <br>[Longformer: The Long-Document Transformer](https://arxiv.org/abs/2004.05150) <br> Iz Beltagy, Matthew E. Peters, Arman Cohan | |[Paper](https://arxiv.org/pdf/2004.05150)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'20-purple) <br>[Big Bird: Transformers for Longer Sequences](https://arxiv.org/abs/2007.14062) <br> Manzil Zaheer, Guru Guruganesh, Avinava Dubey, Joshua Ainslie, Chris Alberti, Santiago Ontanon, Philip Pham, Anirudh Ravula, Qifan Wang, Li Yang, Amr Ahmed | |[Paper](https://arxiv.org/pdf/2007.14062)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'20-red) <br>[Reformer: The Efficient Transformer](https://arxiv.org/abs/2001.04451) <br> Nikita Kitaev, Łukasz Kaiser, Anselm Levskaya | |[Paper](https://arxiv.org/pdf/2001.04451)|
|![Publish](https://img.shields.io/badge/Conference-ICML'20-blue) <br>[Sparse Sinkhorn Attention](https://proceedings.mlr.press/v119/tay20a.html) <br> Yi Tay, Dara Bahri, Liu Yang, Donald Metzler, Da-Cheng Juan | |[Paper](https://proceedings.mlr.press/v119/tay20a/tay20a.pdf)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'20-purple) <br>[Fast Transformers with Clustered Attention](https://arxiv.org/abs/2007.04825) <br> Apoorv Vyas, Angelos Katharopoulos, François Fleuret | |[Paper](https://arxiv.org/pdf/2007.04825)|
|![Publish](https://img.shields.io/badge/Journal-TACL'21-orange) <br>[Efficient Content-Based Sparse Attention with Routing Transformers](https://arxiv.org/abs/2003.05997) <br> Aurko Roy, Mohammad Saffar, Ashish Vaswani, David Grangier | |[Paper](https://arxiv.org/pdf/2003.05997)|
|![Publish](https://img.shields.io/badge/Conference-ACL'22-brightgreen) <br>[ClusterFormer: Neural Clustering Attention for Efficient and Effective Transformer](https://arxiv.org/abs/2203.09053) <br> Ningning Wang, Guobing Gan, Peng Zhang, Shuai Zhang, Junqiu Wei, Qun Liu, Xin Jiang | |[Paper](https://arxiv.org/pdf/2203.09053)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[HyperAttention: Long-context Attention in Near-Linear Time](https://arxiv.org/abs/2310.05869) <br> Insu Han, Rajesh Jayaram, Amin Karbasi, Vahab Mirrokni, David Woodruff, Amir Zandieh | |[Paper](https://arxiv.org/pdf/2310.05869)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'20-b31b1b) <br>[Linformer: Self-Attention with Linear Complexity](https://arxiv.org/abs/2006.04768) <br> Sinong Wang, Belinda Z. Li, Madian Khabsa, Han Fang, Hao Ma | |[Paper](https://arxiv.org/pdf/2006.04768)|
|![Publish](https://img.shields.io/badge/Conference-ICASSP'20-blue) <br>[Lightweight and Efficient End-to-End Speech Recognition Using Low-Rank Transformer](https://ieeexplore.ieee.org/document/9053878) <br> Genta Indra Winata, Samuel Cahyawijaya, Zhaojiang Lin, Zihan Liu, Pascale Fung | |[Paper](https://ieeexplore.ieee.org/document/9053878)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'21-purple) <br>[Luna: Linear Unified Nested Attention](https://arxiv.org/abs/2106.01540) <br> Xuezhe Ma, Xiang Kong, Sinong Wang, Chunting Zhou, Jonathan May, Hao Ma, Luke Zettlemoyer | |[Paper](https://arxiv.org/pdf/2106.01540)|
|![Publish](https://img.shields.io/badge/Conference-ICML'19-blue) <br>[Set Transformer: A Framework for Attention-based Permutation-Invariant Neural Networks](https://arxiv.org/abs/1810.00825) <br> Juho Lee, Yoonho Lee, Jungtaek Kim, Adam Kosiorek, Seungjin Choi, Yee Whye Teh | |[Paper](https://arxiv.org/pdf/1810.00825)|
|![Publish](https://img.shields.io/badge/Conference-ICML'20-blue) <br>[Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention](https://arxiv.org/abs/2006.16236) <br> Angelos Katharopoulos, Apoorv Vyas, Nikolaos Pappas, François Fleuret | |[Paper](https://arxiv.org/pdf/2006.16236)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'21-red) <br>[Rethinking Attention with Performers](https://arxiv.org/abs/2009.14794) <br> Krzysztof Choromanski, Valerii Likhosherstov, David Dohan, Xingyou Song, Andreea Gane, Tamas Sarlos, Peter Hawkins, Jared Davis, Afroz Mohiuddin, Lukasz Kaiser, et al. | |[Paper](https://arxiv.org/pdf/2009.14794)|
---

<a id="MoE"></a>
🏆 本领域经典论文之Mixture of Experts

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-ICLR'17-red) <br>[Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer](https://arxiv.org/abs/1701.06538) <br> Noam Shazeer, Azalia Mirhoseini, Krzysztof Maziarz, Andy Davis, Quoc Le, Geoffrey Hinton, Jeff Dean | |[Paper](https://arxiv.org/pdf/1701.06538)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'21-red) <br>[GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding](https://arxiv.org/abs/2006.16668) <br> Dmitry Lepikhin, HyoukJoong Lee, Yuanzhong Xu, Dehao Chen, Orhan Firat, Yanping Huang, Maxim Krikun, Noam Shazeer, Zhifeng Chen | |[Paper](https://arxiv.org/pdf/2006.16668)|
|![Publish](https://img.shields.io/badge/Journal-JMLR'22-blue) <br>[Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity](https://arxiv.org/abs/2101.03961) <br> William Fedus, Barret Zoph, Noam Shazeer | |[Paper](https://arxiv.org/pdf/2101.03961)|
|![Publish](https://img.shields.io/badge/Conference-ICML'21-blue) <br>[BASE Layers: Simplifying Training of Large, Sparse Models](https://arxiv.org/abs/2103.16716) <br> Mike Lewis, Shruti Bhosale, Tim Dettmers, Naman Goyal, Luke Zettlemoyer | |[Paper](https://arxiv.org/pdf/2103.16716)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'22-purple) <br>[Mixture-of-Experts with Expert Choice Routing](https://arxiv.org/abs/2202.09368) <br> Yanqi Zhou, Tao Lei, Hanxiao Liu, Nan Du, Yanping Huang, Vincent Zhao, Andrew M. Dai, Quoc V. Le, James Laudon | |[Paper](https://arxiv.org/pdf/2202.09368)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[From Sparse to Soft Mixtures of Experts](https://arxiv.org/abs/2308.00951) <br> Joan Puigcerver, Carlos Riquelme Ruiz, Basil Mustafa, Neil Houlsby | |[Paper](https://arxiv.org/pdf/2308.00951)|
|![Publish](https://img.shields.io/badge/Conference-ICML'22-blue) <br>[DeepSpeed-MoE: Advancing Mixture-of-Experts Inference and Training to Power Next-Generation AI Scale](https://arxiv.org/abs/2201.05596) <br> Samyam Rajbhandari, Conglong Li, Zhewei Yao, Minjia Zhang, Reza Yazdani Aminabadi, Ammar Ahmad Awan, Jeff Rasley, Yuxiong He | |[Paper](https://arxiv.org/pdf/2201.05596)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24-brightgreen) <br>[DeepSeekMoE: Towards Ultimate Expert Specialization in Mixture-of-Experts Language Models](https://arxiv.org/abs/2401.06066) <br> Damai Dai, Chengqi Deng, Chenggang Zhao, RX Xu, Huazuo Gao, Deli Chen, Jiashi Li, Wangding Zeng, Xingkai Yu, Yu Wu, et al. | |[Paper](https://arxiv.org/pdf/2401.06066)|
---

<p align="center">
  <sub>⭐ 持续更新中 · 缺少的图片精读之后会补 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
