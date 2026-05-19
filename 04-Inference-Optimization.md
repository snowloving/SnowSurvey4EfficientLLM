<p align="center">
  <img src="https://img.shields.io/badge/Papers-24-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 🚀 Inference Optimization of LLM

> **涵盖领域**: KV Cache优化 · 投机解码 (Speculative Decoding) · 注意力加速 (FlashAttention系列) · 模型并行与分布式推理 · 批处理与调度 (Batching & Scheduling) · 算子融合与编译优化
> **核心目标**: 降低LLM推理延迟与内存占用，提升吞吐量，实现高效低成本的模型服务化部署

---

## 📖 目录

- [📊 本领域综述论文](#-survey)
- [🔥 本领域经典论文之KV Cache优化](#-kv-cache)
- [🏆 本领域经典论文之投机解码 (Speculative Decoding)](#-speculative-decoding)
- [💎 本领域经典论文之提示词压缩](#-prompt)
- [🥇 本领域经典论文之注意力加速 (FlashAttention系列)](#-flash-attention)
- [🎯 本领域经典论文之模型并行与分布式推理](#-parallel)
- [⚡ 本领域经典论文之算子融合与编译优化](#-compilation)

---

<a id="survey"></a>
## 📊 本领域综述论文

> **说明**: 本领域综述专注于LLM推理优化技术，覆盖KV Cache、投机解码、注意力加速、分布式推理、批处理调度等方向。

| # | 论文标题 | 年份 | 出处 | 核心分类框架 | 💡 一句话洞察 |
|:--:|---------|:----:|------|-------------|--------------|
| | | | | | |

---

<a id="kv-cache"></a>
## 🔥 本领域经典论文之KV Cache优化

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---

<a id="speculative-decoding"></a>
## 🏆 本领域经典论文之投机解码 (Speculative Decoding)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-ICML'23-blue) <br>[Fast Inference from Transformers via Speculative Decoding](https://arxiv.org/abs/2211.17192) <br> Yaniv Leviathan, Matan Kalman, Yossi Matias | |[Paper](https://arxiv.org/pdf/2211.17192)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[Accelerating Large Language Model Decoding with Speculative Sampling](https://arxiv.org/abs/2302.01318) <br> Charlie Chen, Sebastian Borgeaud, Geoffrey Irving, Jean-Baptiste Lespiau, Laurent Sifre, John Jumper | |[Paper](https://arxiv.org/pdf/2302.01318)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[DistillSpec: Improving Speculative Decoding via Knowledge Distillation](https://arxiv.org/abs/2310.08461) <br> Yongchao Zhou, Kaifeng Lyu, Ankit Singh Rawat, Aditya Krishna Menon, Afshin Rostamizadeh, Sanjiv Kumar, Jean-François Kagy, Rishabh Agarwal | |[Paper](https://arxiv.org/pdf/2310.08461)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[Speculative Decoding with Big Little Decoder](https://arxiv.org/abs/2302.07863) <br> Sehoon Kim, Karttikeya Mangalam, Suhong Moon, Jitendra Malik, Michael W. Mahoney, Amir Gholami, Kurt Keutzer | |[Paper](https://arxiv.org/pdf/2302.07863)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[LLMA: Inference with Reference: Lossless Acceleration of Large Language Models](https://arxiv.org/abs/2304.04487) <br> Nan Yang, Tao Ge, Liang Wang, Binxing Jiao, Daxin Jiang, Linjun Yang, Rangan Majumder, Furu Wei | |[Paper](https://arxiv.org/pdf/2304.04487)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[Medusa: Simple LLM Inference Acceleration Framework with Multiple Decoding Heads](https://arxiv.org/abs/2401.10774) <br> Tianle Cai, Yuhong Li, Zhengyang Geng, Hongwu Peng, Jason D. Lee, Deming Chen, Tri Dao | |[Paper](https://arxiv.org/pdf/2401.10774)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[EAGLE: Speculative Sampling Requires Rethinking Feature Uncertainty](https://arxiv.org/abs/2401.15077) <br> Yuhui Li, Fangyun Wei, Chao Zhang, Hongyang Zhang | |[Paper](https://arxiv.org/pdf/2401.15077)|
|![Publish](https://img.shields.io/badge/Conference-KDD'24-blue) <br>[Lookahead: An Inference Acceleration Framework for Large Language Model with Lossless Generation Accuracy](https://arxiv.org/abs/2312.12728) <br> Yao Zhao, Zhitian Xie, Chen Liang, Chenyi Zhuang, Jinjie Gu | |[Paper](https://arxiv.org/pdf/2312.12728)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24-brightgreen) <br>[Draft & Verify: Lossless Large Language Model Acceleration via Self-Speculative Decoding](https://arxiv.org/abs/2309.08168) <br> Jun Zhang, Jue Wang, Huan Li, Lidan Shou, Ke Chen, Gang Chen, Sharad Mehrotra | |[Paper](https://arxiv.org/pdf/2309.08168)|
|![Publish](https://img.shields.io/badge/Conference-ASPLOS'24-orange) <br>[SpecInfer: Accelerating Large Language Model Serving with Tree-Based Speculative Inference and Verification](https://arxiv.org/abs/2305.09781) <br> Xupeng Miao, Gabriele Oliaro, Zhihao Zhang, Xinhao Cheng, Zeyu Wang, Zhengxin Zhang, Rae Ying Yee Wong, Alan Zhu, Lijie Yang, Xiaoxiang Shi, et al. | |[Paper](https://arxiv.org/pdf/2305.09781)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[Cascade Speculative Drafting for Even Faster LLM Inference](https://arxiv.org/abs/2312.11462) <br> Ziyi Chen, Xiaocong Yang, Jiacheng Lin, Chenkai Sun, Kevin C. Chang, Jie Huang | |[Paper](https://arxiv.org/pdf/2312.11462)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[Accelerating LLM Inference with Staged Speculative Decoding](https://arxiv.org/abs/2308.04623) <br> Benjamin Spector, Chris Re | |[Paper](https://arxiv.org/pdf/2308.04623)|
|![Publish](https://img.shields.io/badge/Conference-NAACL'24-blue) <br>[REST: Retrieval-Based Speculative Decoding](https://arxiv.org/abs/2311.08252) <br> Zhenyu He, Zexuan Zhong, Tianle Cai, Jason Lee, Di He | |[Paper](https://arxiv.org/pdf/2311.08252)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[Sequoia: Scalable, Robust, and Hardware-Aware Speculative Decoding](https://arxiv.org/abs/2402.12374) <br> Zhuoming Chen, Avner May, Ruslan Svirschevski, Yuhsun Huang, Max Ryabinin, Zhihao Jia, Beidi Chen | |[Paper](https://arxiv.org/pdf/2402.12374)|

---

<a id="prompt"></a>
## 💎 本领域经典论文之提示词压缩

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[Compressing Context to Enhance Inference Efficiency of Large Language Models](https://arxiv.org/abs/2310.06201) <br> Yucheng Li, Bo Dong, Frank Guerin, Chenghua Lin | |[Paper](https://arxiv.org/pdf/2310.06201)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[LLMLingua: Compressing Prompts for Accelerated Inference of Large Language Models](https://arxiv.org/abs/2310.05736) <br> Huiqiang Jiang, Qianhui Wu, Chin-Yew Lin, Yuqing Yang, Lili Qiu | |[Paper](https://arxiv.org/pdf/2310.05736)|
|![Publish](https://img.shields.io/badge/Conference-ICML'20-blue) <br>[PoWER-BERT: Accelerating BERT Inference via Progressive Word-vector Elimination](https://arxiv.org/abs/2001.08950) <br> Saurabh Goyal, Anamitra Roy Choudhury, Saurabh Raje, Venkatesan Chakaravarthy, Yogish Sabharwal, Ashish Verma | |[Paper](https://arxiv.org/pdf/2001.08950)|
|![Publish](https://img.shields.io/badge/Conference-ACL'21-brightgreen) <br>[Length-Adaptive Transformer: Train Once with Length Drop, Use Anytime with Search](https://arxiv.org/abs/2010.07003) <br> Gyuwan Kim, Kyunghyun Cho | |[Paper](https://arxiv.org/pdf/2010.07003)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24-brightgreen) <br>[LongLLMLingua: Accelerating and Enhancing LLMs in Long Context Scenarios via Prompt Compression](https://arxiv.org/abs/2310.06839) <br> Huiqiang Jiang, Qianhui Wu, Xufang Luo, Dongsheng Li, Chin-Yew Lin, Yuqing Yang, Lili Qiu | |[Paper](https://arxiv.org/pdf/2310.06839)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[RECOMP: Improving Retrieval-Augmented LMs with Context Compression and Selective Augmentation](https://arxiv.org/abs/2310.04408) <br> Fangyuan Xu, Weijia Shi, Eunsol Choi | |[Paper](https://arxiv.org/pdf/2310.04408)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[Adapting Language Models to Compress Contexts](https://arxiv.org/abs/2305.14788) <br> Alexis Chevalier, Alexander Wettig, Anirudh Ajith, Danqi Chen | |[Paper](https://arxiv.org/pdf/2305.14788)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[Learning to Compress Prompts with Gist Tokens](https://arxiv.org/abs/2304.08467) <br> Jesse Mu, Xiang Lisa Li, Noah Goodman | |[Paper](https://arxiv.org/pdf/2304.08467)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[In-context Autoencoder for Context Compression in a Large Language Model](https://arxiv.org/abs/2307.06945) <br> Tao Ge, Jing Hu, Lei Wang, Xun Wang, Si-Qing Chen, Furu Wei | |[Paper](https://arxiv.org/pdf/2307.06945)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24_Findings-brightgreen) <br>[LLMLingua-2: Data Distillation for Efficient and Faithful Task-Agnostic Prompt Compression](https://arxiv.org/abs/2403.12968) <br> Zhuoshi Pan, Qianhui Wu, Huiqiang Jiang, Menglin Xia, Xufang Luo, Jue Zhang, Qingwei Lin, Victor Rühle, Yuqing Yang, Chin-Yew Lin, et al. | |[Paper](https://arxiv.org/pdf/2403.12968)|

---

<a id="flash-attention"></a>
## 🥇 本领域经典论文之注意力加速 (FlashAttention系列)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---

<a id="parallel"></a>
## 🎯 本领域经典论文之模型并行与分布式推理

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---


<a id="compilation"></a>
## ⚡ 本领域经典论文之算子融合与编译优化

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---

<p align="center">
  <sub>⭐ 持续更新中 · 缺少的图片精读之后会补 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
