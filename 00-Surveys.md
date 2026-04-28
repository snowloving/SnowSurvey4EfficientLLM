## 001-General-Surveys

### Efficiently integrate large language models with visual perception: a survey from the training paradigm perspective

---

### Efficient Large Language Models: A Survey
- ⭐⭐⭐ [Efficient Large Language Models: A Survey](https://arxiv.org/abs/2312.03863)
  - *Wan et al., arXiv, 2023 (持续更新)*
  - **分类方式**：按 **模型中心 / 数据中心 / 框架中心** 三个视角组织
  - **覆盖子方向**：
    - `模型压缩` → 量化（GPTQ, AWQ, SmoothQuant）、剪枝（SparseGPT, Wanda）、蒸馏、低秩分解（LoRA, QLoRA）
    - `高效架构` → 高效注意力（GQA, MQA, FlashAttention）、MoE（Mixtral, DeepSpeed-MoE）、替代架构（Mamba, RWKV）
    - `推理优化` → KV Cache 管理（PagedAttention, StreamingLLM）、投机解码（Medusa, Eagle）、系统优化（vLLM, TensorRT-LLM）
    - `训练优化` → 高效微调（LoRA 系列, IA3）、分布式训练（ZeRO, FSDP）、混合精度训练
  - **核心结论/洞察**：算法-硬件-框架协同设计是进一步提升 LLM 效率的关键，单一维度优化已接近瓶颈
  - **附带资源**：[GitHub 持续更新](https://github.com/AIoT-MLSys-Lab/Efficient-LLMs-Survey)

---

## 002-Domain-Specific/KV-Cache
