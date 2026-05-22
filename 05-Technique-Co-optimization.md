<p align="center">
  <img src="https://img.shields.io/badge/Papers-14-blue?style=flat-square" alt="Paper Count">
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
- [🥇 本领域经典论文之4](#flash-attention)
- [🎯 本领域经典论文之5](#parallel)
- [⚡ 本领域经典论文之6](#compilation)

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

---

<a id="flash-attention"></a>
## 🥇 本领域经典论文之4

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---

<a id="parallel"></a>
## 🎯 本领域经典论文之5

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---


<a id="compilation"></a>
## ⚡ 本领域经典论文之6

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
| | | |

---

<p align="center">
  <sub>⭐ 持续更新中 · 缺少的图片精读之后会补 · 欢迎提交 Issue 或 PR 补充论文 ⭐</sub>
</p>
