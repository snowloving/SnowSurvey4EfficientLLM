## 001-General-Surveys

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

### A Survey on Efficient Large Language Models
- ⭐⭐⭐ [A Survey on Efficient LLMs: Principles, Algorithms, Applications, and Open Issues](https://arxiv.org/abs/2501.xxxxx)
  - *Cheng et al., IEEE TNNLS, 2025*
  - **分类方式**：按 **LLM 全生命周期** 组织：训练 → 微调 → 部署 → 推理
  - **覆盖子方向**：
    - `训练优化` → 数据筛选、课程学习、高效预训练策略
    - `微调优化` → 参数高效微调（LoRA, Adapter, Prefix-Tuning）、指令微调压缩
    - `模型压缩` → 量化（GPTQ, AWQ, QLoRA）、剪枝（结构化/非结构化）、蒸馏
    - `推理加速` → KV Cache 压缩、投机解码、算子优化（FlashAttention）、批处理调度
    - `架构创新` → MoE、轻量化变体、SSM（Mamba）、线性注意力
  - **核心结论/洞察**：当前研究重心正从"单纯追求精度"转向"精度-效率 Pareto 最优"，端侧部署需求推动 2-bit 量化和极低秩方法快速发展
  - **附带资源**：涵盖 500+ 参考文献的系统性综述


## 002-Domain-Specific/KV-Cache
