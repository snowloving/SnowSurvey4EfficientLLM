<p align="center">
  <img src="https://img.shields.io/badge/Papers-29-blue?style=flat-square" alt="Paper Count">
  <img src="https://img.shields.io/badge/Status-Actively%20Updating-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/PRs-Welcome-yellow?style=flat-square" alt="PRs Welcome">
</p>

# 🚀 Technique Co-optimization

> **涵盖领域**: PEFT+量化 · PEFT+KD
\
---

## 📖 目录

- [🔥 本领域经典论文之PEFT+Quantization](#peft-quant)
- [🏆 本领域经典论文之PEFT+Pruning](#peft-pruning)
- [💎 本领域经典论文之KD+Quantization](#kd-quant)
- [🥇 本领域经典论文之KD+Pruning](#kd-pruning)
- [🎯 本领域经典论文之KD+Other](#kd-other)
- [⚡ 本领域经典论文之Architecture+Inference](#arch-infer)

---

<a id="peft-quant"></a>
## 🔥 本领域经典论文之PEFT+Quantization

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[QLoRA: Efficient Finetuning of Quantized LLMs](https://arxiv.org/abs/2305.14314) <br> Tim Dettmers, Artidoro Pagnoni, Ari Holtzman, Luke Zettlemoyer | |[Paper](https://arxiv.org/pdf/2305.14314)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[Memory-Efficient Fine-Tuning of Compressed Large Language Models via Sub-4-bit Integer Quantization](https://arxiv.org/abs/2305.14714) <br> Jeonghoon Kim, Jung Hyun Lee, Sungdong Kim, Joonsuk Park, Kang Min Yoo, Se Jung Kwon, Dongsoo Lee | |[Paper](https://arxiv.org/pdf/2305.14714)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[QA-LoRA: Quantization-Aware Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2309.14717) <br> Yuhui Xu, Lingxi Xie, Xiaotao Gu, Xin Chen, Heng Chang, Hengheng Zhang, Zhengsu Chen, Xiaopeng Zhang, Qi Tian | |[Paper](https://arxiv.org/pdf/2309.14717)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[LQ-LoRA: Low-Rank Plus Quantized Matrix Decomposition for Efficient Language Model Finetuning](https://arxiv.org/abs/2311.12023) <br> Han Guo, Philip Greengard, Eric Xing, Yoon Kim | |[Paper](https://arxiv.org/pdf/2311.12023)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[LoftQ: LoRA-Fine-Tuning-Aware Quantization for Large Language Models](https://arxiv.org/abs/2310.08659) <br> Yixiao Li, Yifan Yu, Chen Liang, Pengcheng He, Nikos Karampatziakis, Weizhu Chen, Tuo Zhao | |[Paper](https://arxiv.org/pdf/2310.08659)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[IR-QLoRA: Accurate LoRA-Finetuning Quantization of LLMs via Information Retention](https://arxiv.org/abs/2402.05445) <br> Haotong Qin, Xudong Ma, Xingyu Zheng, Xiaoyang Li, Yang Zhang, Shouda Liu, Jie Luo, Xianglong Liu, Michele Magno | |[Paper](https://arxiv.org/pdf/2402.05445)|
|![Publish](https://img.shields.io/badge/Conference-ACL'25_Findings-brightgreen) <br>[MeMoTune: A Measure and Moment-Driven Fine-Tuning Framework for Quantized Large Language Models](https://arxiv.org/abs/2501.12345) <br> Yun Zhang, Xue Geng, Lizi Liao, Jintong Sun, Minghe Yu, Ge Yu | |[Paper](https://arxiv.org/pdf/2501.12345)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'25-b31b1b) <br>[Quantum-PEFT: Ultra Parameter-Efficient Fine-Tuning](https://arxiv.org/abs/2503.05431) <br> Toshiaki Koike-Akino, Francesco Tonin, Yongtao Wu, Frank Zhengqing Wu, Leyla Naz Candogan, Volkan Cevher | |[Paper](https://arxiv.org/pdf/2503.05431)|

---

<a id="peft-pruning"></a>
## 🏆 本领域经典论文之PEFT+Pruning

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[LLM-Pruner: On the Structural Pruning of Large Language Models](https://arxiv.org/abs/2305.11627) <br> Xinyin Ma, Gongfan Fang, Xinchao Wang | |[Paper](https://arxiv.org/pdf/2305.11627)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24_Findings-brightgreen) <br>[LoRAPrune: Structured Pruning Meets Low-Rank Parameter-Efficient Fine-Tuning](https://arxiv.org/abs/2305.18403) <br> Mingyang Zhang, Hao Chen, Chunhua Shen, Zhen Yang, Linlin Ou, Xinyi Yu, Bohan Zhuang | |[Paper](https://arxiv.org/pdf/2305.18403)|
|![Publish](https://img.shields.io/badge/Workshop-OPT'25-lightgrey) <br>[Simultaneous Fine-Tuning and Pruning of LLMs](https://arxiv.org/abs/2501.12345) <br> Finn Reinecke, Jörg K.H. Franke, Frank Hutter, Michael Hefenbrock | |[Paper](https://arxiv.org/pdf/2501.12345)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'26-b31b1b) <br>[S²FT: Parameter-Efficient Fine-Tuning in Sparse Spectrum Domain](https://arxiv.org/abs/2605.08589) <br> Baoquan Zhang, Zhehao Yu, Lisai Zhang, Kenghong Lin, Tianran Chen, Yuxi Sun, Yunming Ye, Yao He | |[Paper](https://arxiv.org/pdf/2605.08589)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'22_Findings-green) <br>[SparseAdapter: An Easy Approach for Improving the Parameter-Efficiency of Adapters](https://arxiv.org/abs/2210.04284) <br> Shwai He, Liang Ding, Daize Dong, Jeremy Zhang, Dacheng Tao | |[Paper](https://arxiv.org/pdf/2210.04284)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[MoSA: Mixture of Sparse Adapters for Visual Efficient Tuning](https://arxiv.org/abs/2312.02923) <br> Qizhe Zhang, Bocheng Zou, Ruichuan An, Jiaming Liu, Shanghang Zhang | |[Paper](https://arxiv.org/pdf/2312.02923)|

---

<a id="kd-quant"></a>
## 💎 本领域经典论文之KD+Quantization

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-ACL'24_Findings-brightgreen) <br>[LLM-QAT: Data-Free Quantization Aware Training for Large Language Models](https://arxiv.org/abs/2305.17888) <br> Zechun Liu, Barlas Oguz, Changsheng Zhao, Ernie Chang, Pierre Stock, Yashar Mehdad, Yangyang Shi, Raghuraman Krishnamoorthi, Vikas Chandra | |[Paper](https://arxiv.org/pdf/2305.17888)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24-brightgreen) <br>[BitDistiller: Unleashing the Potential of Sub-4-Bit LLMs via Self-Distillation](https://arxiv.org/abs/2402.10631) <br> Dayou Du, Yijia Zhang, Shijie Cao, Jiaqi Guo, Ting Cao, Xiaowen Chu, Ningyi Xu | |[Paper](https://arxiv.org/pdf/2402.10631)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[OneBit: Towards Extremely Low-Bit Large Language Models](https://arxiv.org/abs/2402.11295) <br> Yuzhuang Xu, Xu Han, Zonghan Yang, Shuo Wang, Qingfu Zhu, Zhiyuan Liu, Weidong Liu, Wanxiang Che | |[Paper](https://arxiv.org/pdf/2402.11295)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[QFT: Quantized Full-Parameter Tuning of LLMs with Affordable Resources](https://arxiv.org/abs/2310.07147) <br> Zhikai Li, Xiaoxuan Liu, Banghua Zhu, Zhen Dong, Qingyi Gu, Kurt Keutzer | |[Paper](https://arxiv.org/pdf/2310.07147)|

---

<a id="kd-pruning"></a>
## 🥇 本领域经典论文之KD+Pruning

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[LLM-Pruner: On the Structural Pruning of Large Language Models](https://arxiv.org/abs/2305.11627) <br> Xinyin Ma, Gongfan Fang, Xinchao Wang | |[Paper](https://arxiv.org/pdf/2305.11627)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[Compresso: Structured Pruning with Collaborative Prompting Learns Compact Large Language Models](https://arxiv.org/abs/2310.05015) <br> Song Guo, Jiahang Xu, Li Lyna Zhang, Mao Yang | |[Paper](https://arxiv.org/pdf/2310.05015)|
|![Publish](https://img.shields.io/badge/Conference-ACL'25_Findings-brightgreen) <br>[ShortGPT: Layers in Large Language Models are More Redundant Than You Expect](https://arxiv.org/abs/2403.03853) <br> Xin Men, Mingyu Xu, Qingyu Zhang, Qianhao Yuan, Bingning Wang, Hongyu Lin, Yaojie Lu, Xianpei Han, Weipeng Chen | |[Paper](https://arxiv.org/pdf/2403.03853)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[Shortened LLaMA: Depth Pruning for Large Language Models with Comparison of Retraining Methods](https://arxiv.org/abs/2402.02834) <br> Bo-Kyeong Kim, Geonmin Kim, Tae-Ho Kim, Thibault Castells, Shinkook Choi, Junho Shin, Hyoung-Kyu Song | |[Paper](https://arxiv.org/pdf/2402.02834)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[Sheared LLaMA: Accelerating Language Model Pre-training via Structured Pruning](https://arxiv.org/abs/2310.06694) <br> Mengzhou Xia, Tianyu Gao, Zhiyuan Zeng, Danqi Chen | |[Paper](https://arxiv.org/pdf/2310.06694)|

---

<a id="kd-other"></a>
## 🎯 本领域经典论文之KD+Other

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |
|![Publish](https://img.shields.io/badge/Conference-ACL'23_Findings-brightgreen) <br>[Distilling Step-by-Step! Outperforming Larger Language Models with Less Training Data and Smaller Model Sizes](https://arxiv.org/abs/2305.02301) <br> Cheng-Yu Hsieh, Chun-Liang Li, Chih-Kuan Yeh, Hootan Nakhost, Yasuhisa Fujii, Alex Ratner, Ranjay Krishna, Chen-Yu Lee, Tomas Pfister | |[Paper](https://arxiv.org/pdf/2305.02301)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[GKD: On-Policy Distillation of Language Models: Learning from Self-Generated Mistakes](https://arxiv.org/abs/2306.13649) <br> Rishabh Agarwal, Nino Vieillard, Yongchao Zhou, Piotr Stanczyk, Sabela Ramos Garea, Matthieu Geist, Olivier Bachem | |[Paper](https://arxiv.org/pdf/2306.13649)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[DistillSpec: Improving Speculative Decoding via Knowledge Distillation](https://arxiv.org/abs/2310.08461) <br> Yongchao Zhou, Kaifeng Lyu, Ankit Singh Rawat, Aditya Krishna Menon, Afshin Rostamizadeh, Sanjiv Kumar, Jean-François Kagy, Rishabh Agarwal | |[Paper](https://arxiv.org/pdf/2310.08461)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'24-green) <br>[Ouroboros: Generating Longer Drafts Phrase by Phrase for Faster Speculative Decoding](https://arxiv.org/abs/2406.12345) <br> Weilin Zhao, Yuxiang Huang, Xu Han, Wang Xu, Chaojun Xiao, Xinrong Zhang, Yewei Fang, Kaihuo Zhang, Zhiyuan Liu, Maosong Sun | |[Paper](https://arxiv.org/pdf/2406.12345)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'22-b31b1b) <br>[Sparse Upcycling: Training Mixture-of-Experts from Dense Checkpoints](https://arxiv.org/abs/2212.05055) <br> Aran Komatsuzaki, Joan Puigcerver, James Lee-Thorp, Carlos Riquelme Ruiz, Basil Mustafa, Joshua Ainslie, Yi Tay, Mostafa Dehghani, Neil Houlsby | |[Paper](https://arxiv.org/pdf/2212.05055)|
|![Publish](https://img.shields.io/badge/Conference-ACL'24_Findings-brightgreen) <br>[LLMLingua-2: Data Distillation for Efficient and Faithful Task-Agnostic Prompt Compression](https://arxiv.org/abs/2403.12968) <br> Zhuoshi Pan, Qianhui Wu, Huiqiang Jiang, Menglin Xia, Xufang Luo, Jue Zhang, Qingwei Lin, Victor Rühle, Yuqing Yang, Chin-Yew Lin, et al. | |[Paper](https://arxiv.org/pdf/2403.12968)|

---


<a id="arch-infer"></a>
## ⚡ 本领域经典论文之Architecture+Inference

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---

<p align="center">
  <sub>⭐ 持续更新中 · 缺少的图片精读之后会补 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
