# 论文清单：VLA、WM、MBRL 与 WAM

## 阅读标记

- **S0｜必读**：建立共同语言，建议精读摘要、方法图、损失函数和实验结论。
- **S1｜主线**：按研究方向选择精读。
- **S2｜扩展**：遇到具体问题时再读。

## S0｜模型基础

这些论文先于具体 VLA/WM 论文阅读，用来建立“backbone、训练目标、采样器”三者的边界。配套的张量流见 [模型基础](model-basics.md)。

| 原语 | 论文 | 为什么读 | 代码入口 |
| --- | --- | --- | --- |
| Transformer | Attention Is All You Need | self-attention、位置编码、causal mask 与序列建模骨架 | [Transformers](https://github.com/huggingface/transformers) |
| Diffusion | Denoising Diffusion Probabilistic Models | 前向加噪、反向去噪、噪声预测目标与采样 | [Diffusers](https://github.com/huggingface/diffusers) |
| Flow Matching | Flow Matching for Generative Modeling | probability path、条件速度场和 ODE 生成 | [Flow Matching](https://github.com/facebookresearch/flow_matching) |
| DiT | Scalable Diffusion Models with Transformers | Transformer 作为扩散/视频生成 backbone 的实现范式 | [DiT](https://github.com/facebookresearch/DiT) |

## S0｜最短主线

| 顺序 | 论文 | 为什么读 | 入口 |
| --- | --- | --- | --- |
| 1 | Reinforcement Learning: An Introduction, 2nd ed. | MDP、价值函数、TD、策略梯度的统一底座 | [Book PDF](https://incompleteideas.net/book/RLbook2020.pdf) |
| 2 | Offline Reinforcement Learning: Tutorial, Review, and Perspectives | 理解固定数据集、分布偏移与保守学习 | [arXiv](https://arxiv.org/abs/2005.01643) |
| 3 | World Models | 理解 latent dynamics + controller 的经典 MBRL 前身 | [arXiv](https://arxiv.org/abs/1803.10122) · [Project](https://worldmodels.github.io/) |
| 4 | Diffusion Policy | 机器人动作生成、action chunk 与多峰行为的代表作 | [arXiv](https://arxiv.org/abs/2303.04137) · [Code](https://github.com/real-stanford/diffusion_policy) |
| 5 | π0: A Vision-Language-Action Flow Model for General Robot Control | 理解 VLM backbone、flow matching action expert 与通用策略 | [arXiv](https://arxiv.org/abs/2410.24164) · [Project](https://www.pi.website/blog/pi0) |
| 6 | π0.5: A Vision-Language-Action Model with Open-World Generalization | 异构协同训练、高层语义与开放世界长时程泛化 | [arXiv](https://arxiv.org/abs/2504.16054) · [Project](https://www.pi.website/blog/pi05) · [Code](https://github.com/Physical-Intelligence/openpi) |
| 7 | V-JEPA 2: Self-Supervised Video Models Enable Understanding, Prediction and Planning | 现代 JEPA 世界表征、物理理解与预测接口 | [arXiv](https://arxiv.org/abs/2506.09985) · [Code](https://github.com/facebookresearch/vjepa2) |
| 8 | World Action Models: The Next Frontier in Embodied AI | 用级联式/联合式框架建立 WAM 的系统分类 | [arXiv](https://arxiv.org/abs/2605.12090) · [Resources](https://github.com/OpenMOSS/Awesome-WAM) |
| 9 | Fast-WAM: Do World Action Models Need Test-time Future Imagination? | 区分训练期视频建模收益和测试期显式想象成本 | [arXiv](https://arxiv.org/abs/2603.16666) · [Project](https://yuantianyuan01.github.io/FastWAM/) · [Code](https://github.com/yuantianyuan01/FastWAM) |
| 10 | StarVLA: A Lego-like Codebase for Vision-Language-Action Model Developing | 把 VLA 研究拆为可替换 backbone、action head、训练与部署模块 | [arXiv](https://arxiv.org/abs/2604.05014) · [Code](https://github.com/starVLA/starVLA) |
| 11 | RLinf: Flexible and Efficient Large-scale Reinforcement Learning via Macro-to-Micro Flow Transformation | 理解 VLA/基础模型 RL 后训练的系统问题 | [arXiv](https://arxiv.org/abs/2509.15965) · [Code](https://github.com/RLinf/RLinf) |

## S1｜VLA 与动作策略

| 论文 | 抓住一个关键点 | 入口 |
| --- | --- | --- |
| OpenVLA: An Open-Source Vision-Language-Action Model | 开源 VLA 训练、微调与评测范式 | [arXiv](https://arxiv.org/abs/2406.09246) · [Code](https://github.com/openvla/openvla) |
| OpenVLA-OFT: An Open-Source Fine-Tuning Recipe for OpenVLA | OpenVLA 的高效微调与推理优化 | [arXiv](https://arxiv.org/abs/2501.19645) · [Code](https://github.com/moojink/openvla-oft) |
| π0.5: A Vision-Language-Action Model with Open-World Generalization | 异构机器人数据协同、语义子任务与开放世界泛化 | [arXiv](https://arxiv.org/abs/2504.16054) · [Code](https://github.com/Physical-Intelligence/openpi) |
| Open X-Embodiment: Robotic Learning Datasets and RT-X Models | 跨本体数据混合与通用策略 | [arXiv](https://arxiv.org/abs/2310.08864) · [Project](https://robotics-transformer-x.github.io/) |
| Octo: An Open-Source Generalist Robot Policy | 开源通用策略、数据混合与轻量适配 | [arXiv](https://arxiv.org/abs/2405.12213) · [Code](https://github.com/octo-models/octo) |
| Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware (ACT) | 动作分块与 CVAE 在双臂长序列控制中的作用 | [arXiv](https://arxiv.org/abs/2304.13705) · [Code](https://github.com/tonyzhaozh/act) |
| Diffusion Policy | 以条件去噪建模多峰连续动作分布 | [arXiv](https://arxiv.org/abs/2303.04137) · [Code](https://github.com/real-stanford/diffusion_policy) |
| A Survey on Vision-Language-Action Models for Embodied AI | 从组件、训练目标、任务和架构补齐全景 | [arXiv](https://arxiv.org/abs/2405.14093) |

## S1｜World Model：JEPA、视频与 3D

| 论文 | 抓住一个关键点 | 入口 |
| --- | --- | --- |
| V-JEPA 2: Self-Supervised Video Models Enable Understanding, Prediction and Planning | 预测 latent representation 而不是逐像素重建，并连接物理理解与规划 | [arXiv](https://arxiv.org/abs/2506.09985) · [Code](https://github.com/facebookresearch/vjepa2) |
| Genie: Generative Interactive Environments | 从视频学习可交互的潜在环境与动作条件未来 | [arXiv](https://arxiv.org/abs/2402.15391) · [Project](https://sites.google.com/view/genie-2024/home) |
| VGGT: Visual Geometry Grounded Transformer | 多视图几何、相机和 3D 场景表征，可作为 3D WM 的结构化前端 | [arXiv](https://arxiv.org/abs/2503.11651) · [Code](https://github.com/facebookresearch/vggt) |
| A Comprehensive Survey on World Models for Embodied AI | 从表征、时间建模、空间建模和决策用途区分 WM 路线 | [arXiv](https://arxiv.org/abs/2510.16732) |

这里的 WM 是广义环境表征/预测/生成范式；JEPA、视频和 3D/4D 路线不要求自带 planner 或 actor-critic。只有加入动作条件与决策收益证据，才应进一步主张其控制价值。

## S1｜Model-based RL

| 论文 | 抓住一个关键点 | 入口 |
| --- | --- | --- |
| World Models | latent dynamics 与 controller 的经典 MBRL 前身 | [arXiv](https://arxiv.org/abs/1803.10122) · [Project](https://worldmodels.github.io/) |
| PlaNet: Learning Latent Dynamics for Planning from Pixels | 从像素学习潜空间动力学并做在线规划 | [arXiv](https://arxiv.org/abs/1811.04551) |
| Dream to Control: Learning Behaviors by Latent Imagination | 在潜空间 imagined rollout 上学习 actor-critic | [arXiv](https://arxiv.org/abs/1912.01603) |
| DreamerV3: Mastering Diverse Domains through World Models | 统一超参数、跨域扩展与稳定训练 | [arXiv](https://arxiv.org/abs/2301.04104) · [Code](https://github.com/danijar/dreamerv3) |
| MuZero: Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model | 只学习决策所需的动态、奖励与价值 | [arXiv](https://arxiv.org/abs/1911.08265) |
| MBPO: When to Trust Your Model | 短模型 rollout 如何权衡模型偏差和样本效率 | [arXiv](https://arxiv.org/abs/1906.08253) |
| TD-MPC2: Scalable, Robust World Models for Continuous Control | 隐式潜空间动力学、价值学习与 MPC 的结合 | [arXiv](https://arxiv.org/abs/2310.16828) · [Project](https://www.tdmpc2.com/) · [Code](https://github.com/nicklashansen/tdmpc2) |

## S1｜Offline / Online RL

| 类别 | 论文 | 核心问题 | 入口 |
| --- | --- | --- | --- |
| Online, on-policy | Proximal Policy Optimization Algorithms (PPO) | 如何用 clipped surrogate 稳定策略更新 | [arXiv](https://arxiv.org/abs/1707.06347) |
| Online, off-policy | Soft Actor-Critic (SAC) | 最大熵目标、样本复用与连续控制 | [arXiv](https://arxiv.org/abs/1801.01290) |
| Online, value-based | Human-level control through deep reinforcement learning (DQN) | 离散动作 Q-learning、target network 与 replay buffer | [Nature](https://www.nature.com/articles/nature14236) · [Code](https://github.com/google-deepmind/dqn_zoo) |
| Offline, value-based | Conservative Q-Learning (CQL) | 通过保守 Q 估计抑制 OOD 动作过估计 | [arXiv](https://arxiv.org/abs/2006.04779) |
| Offline, value-based | Implicit Q-Learning (IQL) | 不显式查询数据外动作的价值学习 | [arXiv](https://arxiv.org/abs/2110.06169) |
| Offline, sequence | Decision Transformer | 把控制重写为回报条件序列建模 | [arXiv](https://arxiv.org/abs/2106.01345) · [Code](https://github.com/kzl/decision-transformer) |
| Offline, model-based | MOPO | 用不确定性惩罚模型 rollout 的分布外区域 | [arXiv](https://arxiv.org/abs/2005.13239) |
| Offline, model-based | COMBO | 保守价值学习与模型生成数据结合 | [arXiv](https://arxiv.org/abs/2102.08363) |

## S2｜数据、基准与评测

| 论文/项目 | 用途 | 入口 |
| --- | --- | --- |
| D4RL: Datasets for Deep Data-Driven Reinforcement Learning | Offline RL 经典数据与评测协议 | [arXiv](https://arxiv.org/abs/2004.07219) · [Code](https://github.com/Farama-Foundation/D4RL) |
| LIBERO: Benchmarking Knowledge Transfer for Lifelong Robot Learning | 语言条件操作与知识迁移评测 | [arXiv](https://arxiv.org/abs/2306.03310) · [Project](https://libero-project.github.io/main.html) |
| CALVIN: A Benchmark for Language-Conditioned Policy Learning for Long-Horizon Robot Manipulation Tasks | 语言条件长时程闭环与任务链 | [arXiv](https://arxiv.org/abs/2112.03227) · [Code](https://github.com/mees/calvin) |
| ManiSkill2 | 大规模操作任务、数据生成与仿真评测 | [arXiv](https://arxiv.org/abs/2302.04659) · [Code](https://github.com/haosulab/ManiSkill) |
| Meta-World: A Benchmark and Evaluation for Multi-Task and Meta Reinforcement Learning | 多任务操作与组合泛化 | [Project](https://meta-world.github.io/) · [Code](https://github.com/Farama-Foundation/Metaworld) |
| RoboTwin 2.0 | 双臂数字孪生、数据生成与跨场景泛化 | [Code](https://github.com/RoboTwin-Platform/RoboTwin) |
| RoboCasa | 家庭厨房中的长时程操作与接触任务 | [Code](https://github.com/robocasa/robocasa) |
| Open X-Embodiment | 跨机器人数据规模化与跨本体迁移 | [arXiv](https://arxiv.org/abs/2310.08864) · [Project](https://robotics-transformer-x.github.io/) |
