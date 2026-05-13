<p align="center">
  <img src="https://img.shields.io/badge/Papers-43-blue?style=flat-square" alt="Paper Count">
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
| 12 | **Structured Pruning for Deep Convolutional Neural Networks: A Survey** | 2023 | IEEE TPAMI `IF=18.6` | `结构化剪枝`：滤波器/通道/层/块级剪枝 + 重要性评估准则 + 训练/免训练范式 | CNN结构化剪枝领域最权威综述之一，系统梳理从权重重要性到架构搜索的剪枝方法论，为LLM结构化剪枝提供扎实的理论与技术基础 |
| 13 | **Pruning and Quantization for Deep Neural Network Acceleration: A Survey** | 2021 | Neurocomputing `IF=6.5` | `剪枝+量化联合`：结构化/非结构化/量化感知/硬件加速 | 系统整合剪枝与量化两大压缩路线，覆盖从算法原理到硬件加速的端到端优化流程 |
| 14 | 🔥 **Survey on Knowledge Distillation for LLMs: Methods, Evaluation, and Application** | 2025 | ACM TIST `IF=6.6` | `KD范式`：白盒(Logits/Hint) + 黑盒(ICL/CoT/Instruction Following) + `鲁棒性评估` | 首次提出白盒/黑盒二分法用于LLM KD分类，清晰区分了可访问内部参数（白盒）和仅可访问API输出（黑盒）的两类方法；首篇从鲁棒性视角统一评估LLM蒸馏算法的综述；MiniLLM在GPT-2上对抗及OOD鲁棒性最优 |
| 15 | 📖 **A Survey on Symbolic Knowledge Distillation of LLMs** | 2024 | IEEE TAI | `直接蒸馏` / `多级蒸馏` / `RL策略蒸馏` 三类 | 首篇LLM符号化知识蒸馏综述，系统梳理将隐式知识转化为可解释符号规则（知识图谱/决策树/逻辑规则）的全流程方法 |

---

<a id="quantization"></a>
## 🔥 本领域经典论文之量化 (Quantization)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'22-purple) <br>[LLM.int8(): 8-bit Matrix Multiplication for Transformers at Scale](https://arxiv.org/abs/2208.07339) <br> Tim Dettmers, Mike Lewis, Younes Belkada, Luke Zettlemoyer | |[Paper](https://arxiv.org/pdf/2208.07339)|
|![Publish](https://img.shields.io/badge/Conference-AAAI'24-red) <br>[ZeroQuant-V2: Exploring Post-Training Quantization in LLMs from Comprehensive Study to Low Rank Compensation](https://arxiv.org/abs/2303.08302) <br> Zhewei Yao, Xiaoxia Wu, Cheng Li, Stephen Youn, Yuxiong He | |[Paper](https://arxiv.org/pdf/2303.08302)|
|![Publish](https://img.shields.io/badge/Conference-ICML'23-blue) <br>[SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models](https://arxiv.org/abs/2211.10438) <br> Guangxuan Xiao, Ji Lin, Mickael Seznec, Hao Wu, Julien Demouth, Song Han | |[Paper](https://arxiv.org/pdf/2211.10438)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'23-red) <br>[GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers](https://arxiv.org/abs/2210.17323) <br> Elias Frantar, Saleh Ashkboos, Torsten Hoefler, Dan Alistarh | |[Paper](https://arxiv.org/pdf/2210.17323)|
|![Publish](https://img.shields.io/badge/Conference-ICML'24-blue) <br>[QuIP#: Even Better LLM Quantization with Hadamard Incoherence and Lattice Codebooks](https://arxiv.org/abs/2402.04396) <br> Albert Tseng, Jerry Chee, Qingyao Sun, Volodymyr Kuleshov, Christopher De Sa | |[Paper](https://arxiv.org/pdf/2402.04396)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[OmniQuant: Omnidirectionally Calibrated Quantization for Large Language Models](https://arxiv.org/abs/2308.13137) <br> Wenqi Shao, Mengzhao Chen, Zhaoyang Zhang, Peng Xu, Lirui Zhao, Zhiqian Li, Kaipeng Zhang, Peng Gao, Yu Qiao, Ping Luo | |[Paper](https://arxiv.org/pdf/2308.13137)|
|![Publish](https://img.shields.io/badge/Conference-ICML'24-blue) <br>[AQLM: Extreme Compression of Large Language Models via Additive Quantization](https://arxiv.org/abs/2401.06118) <br> Vage Egiazarian, Andrei Panferov, Denis Kuznedelev, Elias Frantar, Artem Babenko, Dan Alistarh | |[Paper](https://arxiv.org/pdf/2401.06118)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[PV-Tuning: Beyond Straight-Through Estimation for Extreme LLM Compression](https://arxiv.org/abs/2405.14852) <br> Vladimir Malinovskii, Denis Mazur, Ivan Ilin, Denis Kuznedelev, Konstantin Burlachenko, Kai Yi, Dan Alistarh, Peter Richtarik | |[Paper](https://arxiv.org/pdf/2405.14852)|
|![Publish](https://img.shields.io/badge/Conference-EMNLP'23-green) <br>[Outlier Suppression+: Accurate Quantization of Large Language Models by Equivalent and Effective Shifting and Scaling](https://arxiv.org/abs/2304.09145) <br> Xiuying Wei, Yunchen Zhang, Yuhang Li, Xiangguo Zhang, Ruihao Gong, Jinyang Guo, Xianglong Liu | |[Paper](https://arxiv.org/pdf/2304.09145)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[FineQuant: Unlocking Efficiency with Fine-Grained Weight-Only Quantization for LLMs](https://arxiv.org/abs/2308.09723) <br> Young Jin Kim, Rawn Henry, Raffy Fahim, Hany Hassan Awadalla | |[Paper](https://arxiv.org/pdf/2308.09723)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[RPTQ: Reorder-based Post-training Quantization for Large Language Models](https://arxiv.org/abs/2304.01089) <br> Zhihang Yuan, Lin Niu, Jiawei Liu, Wenyu Liu, Xinggang Wang, Yuzhang Shang, Guangyu Sun, Qiang Wu, Jiaxiang Wu, Bingzhe Wu | |[Paper](https://arxiv.org/pdf/2304.01089)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'22-purple) <br>[ZeroQuant: Efficient and Affordable Post-Training Quantization for Large-Scale Transformers](https://arxiv.org/abs/2206.01861) <br> Zhewei Yao, Reza Yazdani Aminabadi, Minjia Zhang, Xiaoxia Wu, Conglong Li, Yuxiong He | |[Paper](https://arxiv.org/pdf/2206.01861)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[ZeroQuant-FP: A Leap Forward in LLMs Post-Training W4A8 Quantization Using Floating-Point Formats](https://arxiv.org/abs/2307.09782) <br> Xiaoxia Wu, Zhewei Yao, Yuxiong He | |[Paper](https://arxiv.org/pdf/2307.09782)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[SpQR: A Sparse-Quantized Representation for Near-Lossless LLM Weight Compression](https://arxiv.org/abs/2306.03078) <br> Tim Dettmers, Ruslan Svirschevski, Vage Egiazarian, Denis Kuznedelev, Elias Frantar, Saleh Ashkboos, Alexander Borzunov, Torsten Hoefler, Dan Alistarh | |[Paper](https://arxiv.org/pdf/2306.03078)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'22-purple) <br>[Optimal Brain Compression: A Framework for Accurate Post-Training Quantization and Pruning](https://arxiv.org/abs/2208.11580) <br> Elias Frantar, Dan Alistarh | |[Paper](https://arxiv.org/pdf/2208.11580)|
|![Publish](https://img.shields.io/badge/Conference-AAAI'24-red) <br>[OWQ: Outlier-Aware Weight Quantization for Efficient Fine-Tuning and Inference of Large Language Models](https://arxiv.org/abs/2306.02272) <br> Changhun Lee, Jungyu Jin, Taesu Kim, Hyungjun Kim, Eunhyeok Park | |[Paper](https://arxiv.org/pdf/2306.02272)|
|![Publish](https://img.shields.io/badge/Conference-MLSys'24-orange) <br>[AWQ: Activation-Aware Weight Quantization for On-Device LLM Compression and Acceleration](https://arxiv.org/abs/2306.00978) <br> Ji Lin, Jiaming Tang, Haotian Tang, Shang Yang, Wei-Ming Chen, Wei-Chen Wang, Guangxuan Xiao, Xingyu Dang, Chuang Gan, Song Han | |[Paper](https://arxiv.org/pdf/2306.00978)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'24-purple) <br>[QuaRot: Outlier-Free 4-bit Inference in Rotated LLMs](https://arxiv.org/abs/2404.00456) <br> Saleh Ashkboos, Amirkeivan Mohtashami, Maximilian L. Croci, Bo Li, Pashmina Cameron, Martin Jaggi, Dan Alistarh, Torsten Hoefler, James Hensman | |[Paper](https://arxiv.org/pdf/2404.00456)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'25-red) <br>[SpinQuant: LLM Quantization with Learned Rotations](https://arxiv.org/abs/2405.16406) <br> Zechun Liu, Changsheng Zhao, Igor Fedorov, Bilge Soran, Dhruv Choudhary, Raghuraman Krishnamoorthi, Vikas Chandra, Yuandong Tian, Tijmen Blankevoort | |[Paper](https://arxiv.org/pdf/2405.16406)|

---

<a id="pruning"></a>
## 🏆 本领域经典论文之剪枝 (Pruning)

| Title & Authors | Introduction | Links |
|:--|  :----: | :---:|
|![Publish](https://img.shields.io/badge/Conference-ICML'23-blue) <br>[SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot](https://arxiv.org/abs/2301.00774) <br> Elias Frantar, Dan Alistarh | |[Paper](https://arxiv.org/pdf/2301.00774)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[Wanda: A Simple and Effective Pruning Approach for Large Language Models](https://arxiv.org/abs/2306.11695) <br> Mingjie Sun, Zhuang Liu, Anna Bair, J. Zico Kolter | |[Paper](https://arxiv.org/pdf/2306.11695)|
|![Publish](https://img.shields.io/badge/Conference-ICML'24-blue) <br>[OWL: Outlier Weighed Layerwise Sparsity - A Missing Secret Sauce for Pruning LLMs to High Sparsity](https://arxiv.org/abs/2310.05175) <br> Lu Yin, You Wu, Zhenyu Zhang, Cheng-Yu Hsieh, Yaqing Wang, Yiling Jia, Gen Li, Ajay Jaiswal, Mykola Pechenizkiy, Yi Liang, et al. | |[Paper](https://arxiv.org/pdf/2310.05175)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[BESA: Pruning Large Language Models with Blockwise Parameter-Efficient Sparsity Allocation](https://arxiv.org/abs/2402.16880) <br> Peng Xu, Wenqi Shao, Mengzhao Chen, Shitao Tang, Kaipeng Zhang, Peng Gao, Fengwei An, Yu Qiao, Ping Luo | |[Paper](https://arxiv.org/pdf/2402.16880)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'23-b31b1b) <br>[E-Sparse: Boosting the Large Language Model Inference Through Entropy-Based N:M Sparsity](https://arxiv.org/abs/2310.15929) <br> Yun Li, Lin Niu, Xipeng Zhang, Kai Liu, Jianchen Zhu, Zhanhui Kang | |[Paper](https://arxiv.org/pdf/2310.15929)|
|![Publish](https://img.shields.io/badge/Conference-NeurIPS'23-purple) <br>[LLM-Pruner: On the Structural Pruning of Large Language Models](https://arxiv.org/abs/2305.11627) <br> Xinyin Ma, Gongfan Fang, Xinchao Wang | |[Paper](https://arxiv.org/pdf/2305.11627)|
|![Publish](https://img.shields.io/badge/Conference-ICLR'24-red) <br>[SliceGPT: Compress Large Language Models by Deleting Rows and Columns](https://arxiv.org/abs/2401.15024) <br> Saleh Ashkboos, Maximilian L. Croci, Marcelo Gennari do Nascimento, Torsten Hoefler, James Hensman | |[Paper](https://arxiv.org/pdf/2401.15024)|
|![Publish](https://img.shields.io/badge/Paper-arXiv'24-b31b1b) <br>[Shortened LLaMA: Depth Pruning for Large Language Models with Comparison of Retraining Methods](https://arxiv.org/abs/2402.02834) <br> Bo-Kyeong Kim, Geonmin Kim, Tae-Ho Kim, Thibault Castells, Shinkook Choi, Junho Shin, Hyoung-Kyu Song | |[Paper](https://arxiv.org/pdf/2402.02834)|
|![Publish](https://img.shields.io/badge/Conference-ACL'25_Findings-brightgreen) <br>[ShortGPT: Layers in Large Language Models are More Redundant Than You Expect](https://arxiv.org/abs/2403.03853) <br> Xin Men, Mingyu Xu, Qingyu Zhang, Qianhao Yuan, Bingning Wang, Hongyu Lin, Yaojie Lu, Xianpei Han, Weipeng Chen | |[Paper](https://arxiv.org/pdf/2403.03853)|

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
