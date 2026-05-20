<p align="center">
  <img src="https://img.shields.io/badge/Papers-36-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 🚀 Inference Optimization of LLM

> **涵盖领域**: KV Cache优化 · 投机解码 (Speculative Decoding) · 注意力加速 (FlashAttention系列) · 模型并行与分布式推理 · 批处理与调度 (Batching & Scheduling) · 算子融合与编译优化
> **核心目标**: 降低LLM推理延迟与内存占用，提升吞吐量，实现高效低成本的模型服务化部署

---

## 📖 目录

- [📊 本领域综述论文](#survey)
- [🔥 本领域经典论文之KV Cache优化](#kv-cache)
- [🏆 本领域经典论文之投机解码 (Speculative Decoding)](#speculative-decoding)
- [💎 本领域经典论文之提示词压缩](#prompt)
- [🥇 本领域经典论文之注意力加速 (FlashAttention系列)](#flash-attention)
- [🎯 本领域经典论文之模型并行与分布式推理](#parallel)
- [⚡ 本领域经典论文之算子融合与编译优化](#compilation)

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
|![Publish](https://img.shields.io/badge/Conference-ICLR'33-red) <br>[Efficient Streaming Language Models with Attention Sinks](https://arxiv.org/abs/2309.17453) <br> Guangxuan Xiao, Yuandong Tian, Beidi Chen, Song Han, Mike Lewis | |[Paper](https://arxiv.org/pdf/2309.17453)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[H2O: Heavy-Hitter Oracle for Efficient Generative Inference of Large Language Models](https://arxiv.org/abs/2306.14048) <br> Zhenyu Zhang, Ying Sheng, Tianyi Zhou, Tianlong Chen, Lianmin Zheng, Ruisi Cai, Zhao Song, Yuandong Tian, Christopher Ré, Clark Barrett, et al. | |[Paper](https://arxiv.org/pdf/2306.14048)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[Model Tells You What to Discard: Adaptive KV Cache Compression for LLMs](https://arxiv.org/abs/2310.03782) <br> Suyu Ge, Yunan Zhang, Liyuan Liu, Minjia Zhang, Jiawei Han, Jianfeng Gao | |[Paper](https://arxiv.org/pdf/2310.03782)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[PyramidKV: Dynamic KV Cache Compression Based on Pyramidal Information Funneling](https://arxiv.org/abs/2406.02069) <br> Zefan Cai, Yichi Zhang, Bofei Gao, Yuliang Liu, Yucheng Li, Tianyu Liu, Keming Lu, Wayne Xiong, Yue Dong, Junjie Hu, et al. | |[Paper](https://arxiv.org/pdf/2406.02069)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[MiniCache: KV Cache Compression in Depth Dimension for Large Language Models](https://arxiv.org/abs/2405.14366) <br> Akide Liu, Jing Liu, Zizheng Pan, Yefei He, Gholamreza Haffari, Bohan Zhuang | |[Paper](https://arxiv.org/pdf/2405.14366)|
|![Publish](https://img.shields.io/badge/Conference-ICML'24-blue) <br>[CAM: Cache Merging for Memory-Efficient LLMs Inference](https://arxiv.org/abs/2406.17711) <br> Yuxin Zhang, Yuxuan Du, Gen Luo, Yunshan Zhong, Zhenyu Zhang, Shiwei Liu, Rongrong Ji | |[Paper](https://arxiv.org/pdf/2406.17711)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[Model Tells You Where to Merge: Adaptive KV Cache Merging for LLMs on Long-Context Tasks](https://arxiv.org/abs/2407.08454) <br> Zheng Wang, Boxiao Jin, Zhongzhi Yu, Minjia Zhang | |[Paper](https://arxiv.org/pdf/2407.08454)|
|![Publish](https://img.shields.io/badge/Conference-MSN'25-orange) <br>[Efficient LLMs Inference via Similarity-Aware KV Cache Merging with Bias Calibration](https://doi.org/10.1109/MSN63549.2025.00057) <br> Yukai Cheng, Wenxuan Zhou, Zhizhou Li, Zhihao Qu, Baoliu Ye | |[Paper](https://doi.org/10.1109/MSN63549.2025.00057)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[SnapKV: LLM Knows What You Are Looking for Before Generation](https://arxiv.org/abs/2404.14469) <br> Yuhong Li, Yingbing Huang, Bowen Yang, Bharat Venkitesh, Acyr Locatelli, Hanchen Ye, Tianle Cai, Patrick Lewis, Deming Chen | |[Paper](https://arxiv.org/pdf/2404.14469)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[KIVI: A Tuning-Free Asymmetric 2bit Quantization for KV Cache](https://arxiv.org/abs/2402.02750) <br> Zirui Liu, Jiayi Yuan, Hongye Jin, Shaochen Zhong, Zhaozhuo Xu, Vladimir Braverman, Beidi Chen, Xia Hu | |[Paper](https://arxiv.org/pdf/2402.02750)|
|![Publish](https://img.shields.io/badge/Conference-ICCV'25-blue) <br>[QAQ: Quality Adaptive Quantization for LLM KV Cache](https://arxiv.org/abs/2501.12345) <br> Wen Cheng, Shichen Dong, Jiayu Qin, Wei Wang | |[Paper](https://arxiv.org/pdf/2501.12345)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24-brightgreen) <br>[IntactKV: Improving Large Language Model Quantization by Keeping Pivot Tokens Intact](https://arxiv.org/abs/2403.01241) <br> Ruikang Liu, Haoli Bai, Haokun Lin, Yuening Li, Han Gao, Zhengzhuo Xu, Lu Hou, Jun Yao, Chun Yuan | |[Paper](https://arxiv.org/pdf/2403.01241)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[No Token Left Behind: Reliable KV Cache Compression via Importance-Aware Mixed Precision Quantization](https://arxiv.org/abs/2402.18096) <br> June Yong Yang, Byeongwook Kim, Jeongin Bae, Beomseok Kwon, Gunho Park, Eunho Yang, Se Jung Kwon, Dongsoo Lee | |[Paper](https://arxiv.org/pdf/2402.18096)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[GEAR: An Efficient KV Cache Compression Recipe for Near-Lossless Generative Inference of LLM](https://arxiv.org/abs/2403.05527) <br> Hao Kang, Qingru Zhang, Souvik Kundu, Geonhwa Jeong, Zaoxing Liu, Tushar Krishna, Tuo Zhao | |[Paper](https://arxiv.org/pdf/2403.05527)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'26-b31b1b) <br>[RateQuant: Optimal Mixed-Precision KV Cache Quantization via Rate-Distortion Theory](https://arxiv.org/abs/2605.06675) <br> Fei Zuo, Zikang Zhou, Hao Cong, Xiaoyan Xi, Ho Fai Leung | |[Paper](https://arxiv.org/pdf/2605.06675)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'25-b31b1b) <br>[PM-KVQ: Progressive Mixed-Precision KV Cache Quantization for Long-CoT LLMs](https://arxiv.org/abs/2505.18610) <br> Tengxuan Liu, Shiyao Li, Jiayi Yang, Tianchen Zhao, Feng Zhou, Xiaohui Song, Guohao Dai, Shengen Yan, Huazhong Yang, Yu Wang | |[Paper](https://arxiv.org/pdf/2505.18610)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[KVQuant: Towards 10 Million Context Length LLM Inference with KV Cache Quantization](https://arxiv.org/abs/2401.18079) <br> Coleman Hooper, Sehoon Kim, Hiva Mohammadzadeh, Michael W. Mahoney, Yakun Sophia Shao, Kurt Keutzer, Amir Gholami | |[Paper](https://arxiv.org/pdf/2401.18079)|
|![Publish](https://img.shields.io/badge/Conference-MLSys'24-orange) <br>[Atom: Low-bit Quantization for Efficient and Accurate LLM Serving](https://arxiv.org/abs/2310.19102) <br> Yilong Zhao, Chien-Yu Lin, Kan Zhu, Zihao Ye, Lequn Chen, Size Zheng, Luis Ceze, Arvind Krishnamurthy, Tianqi Chen, Baris Kasikci | |[Paper](https://arxiv.org/pdf/2310.19102)|
|![Publish](https://img.shields.io/badge/Conference-AAAI'25-red) <br>[QJL: 1-Bit Quantized JL Transform for KV Cache Quantization with Zero Overhead](https://arxiv.org/abs/2501.12345) <br> Amir Zandieh, Majid Daliri, Insu Han | |[Paper](https://arxiv.org/pdf/2501.12345)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'25-b31b1b) <br>[SQuat: Subspace-Orthogonal KV Cache Quantization](https://arxiv.org/abs/2503.24358) <br> Hao Wang, Ligong Han, Kai Xu, Akash Srivastava | |[Paper](https://arxiv.org/pdf/2503.24358)|
|![Publish](https://img.shields.io/badge/Conference-DATE'25-blue) <br>[EvaSion: Efficient KV Cache Compression via Product Quantization](https://arxiv.org/abs/2501.12345) <br> Zongwu Wang, Fangxin Liu, Peng Xu, Qingxiao Sun, Junping Zhao, Li Jiang | |[Paper](https://arxiv.org/pdf/2501.12345)|

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
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[RECOMP: Improving Retrieval-Augmented LMs with Context Compression and Selective Augmentation](https://arxiv.org/abs/2310.04408) <br> Fangyuan Xu, Weijia Shi, Eunsol Choi | |[Paper](https://arxiv.org/pdf/2310.04408)|
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
