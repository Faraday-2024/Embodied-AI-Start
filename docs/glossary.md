# 术语表

| 缩写/术语 | 英文 | 简明解释 |
| --- | --- | --- |
| Embodied AI | Embodied Artificial Intelligence | 在环境中通过感知与动作闭环完成任务的智能系统。 |
| MDP | Markov Decision Process | 用状态、动作、转移、奖励和折扣描述序贯决策。 |
| POMDP | Partially Observable MDP | 智能体只能看到不完整观测，需要用历史或记忆推断状态。 |
| Policy | Policy | 从观测/状态到动作分布的映射 $\pi(a\mid s)$。 |
| Value / Q | Value Function / Action-Value Function | 估计状态或状态-动作对的期望累计回报。 |
| RL | Reinforcement Learning | 通过最大化累计回报学习策略。 |
| Offline RL | Offline Reinforcement Learning | 只从固定数据集学习，训练时不继续与环境交互。 |
| Online RL | Online Reinforcement Learning | 训练中用当前策略继续与环境交互并收集新数据。 |
| Offline-to-Online | Offline-to-Online RL | 先用离线数据初始化，再通过在线交互继续优化。 |
| Model-free RL | Model-free Reinforcement Learning | 不显式学习并规划环境动力学，直接学习价值或策略。 |
| Model-based RL | Model-based Reinforcement Learning | 学习/使用环境模型做想象、规划、价值估计或数据生成。 |
| On-policy | On-policy RL | 主要使用当前策略采样的数据更新当前策略，例如 PPO。 |
| Off-policy | Off-policy RL | 可用其他/旧策略数据更新当前策略，例如 SAC。 |
| BC | Behavior Cloning | 用监督学习直接拟合示范动作。 |
| IL | Imitation Learning | 从专家示范学习行为的总称，BC 是最常见形式。 |
| OOD | Out-of-Distribution | 超出训练数据覆盖范围的观测、动作、任务或环境。 |
| WM | World Model | 预测环境动态或学习可用于预测/决策的内部世界表征。 |
| WAM | World Action Model | 将世界未来预测与动作生成联合或紧密耦合的具身模型范式。 |
| VLM | Vision-Language Model | 联合处理视觉和语言的多模态模型。 |
| VLA | Vision-Language-Action Model | 由视觉、语言及可能的状态历史直接生成机器人动作的模型。 |
| Action Token | Action Tokenization | 将连续动作离散化为 token，用序列模型预测。 |
| Action Chunk | Action Chunking | 一次预测未来多个时间步动作，降低决策频率并利用局部时序结构。 |
| Flow Matching | Flow Matching | 学习连续向量场，将简单分布传输到目标动作分布。 |
| Diffusion Policy | Diffusion-based Policy | 通过条件去噪过程生成动作序列的策略。 |
| MPC | Model Predictive Control | 用模型滚动预测有限时域，优化动作后只执行前几步并重新规划。 |
| Latent Dynamics | Latent Dynamics Model | 在压缩的潜空间而非原始像素/状态空间中预测演化。 |
| Imagined Rollout | Imagination Rollout | 在学习到的 world model 中生成虚拟轨迹。 |
| Model Bias | Model Bias | 学习模型与真实环境不一致导致的系统性决策误差。 |
| Sim-to-Real | Simulation-to-Reality | 将仿真中训练的策略迁移到真实机器人。 |
| Teleoperation | Teleoperation | 人类远程控制机器人，用于完成任务或采集示范。 |
| Embodiment | Embodiment | 机器人的物理形态、自由度、传感器与动作接口。 |
| Generalist Policy | Generalist Robot Policy | 试图覆盖多任务、多场景乃至多本体的通用机器人策略。 |
| Post-training | Post-training | 在预训练模型基础上进行监督微调、偏好优化或 RL 等后续训练。 |
| Rollout | Rollout | 策略在环境或模型中从起点执行得到的一段轨迹。 |
| Success Rate | Task Success Rate | 多次评测中满足成功判定的比例；需同时报告任务、初始条件和 seed。 |

## 容易混淆的概念

### Offline RL vs Off-policy RL

- **Offline RL**：训练期没有新的环境交互，数据集固定。
- **Off-policy RL**：更新策略时允许使用非当前策略产生的数据；它可以发生在 online 训练中。

### World Model vs 视频生成模型

- 视频生成模型可以是 world model 的组件，但只有在预测对动作条件敏感、并对决策有用时，才更接近具身决策中的 world model。
- 不生成可见 RGB 的潜空间动力学也可以是 world model。

### VLA vs WAM

- VLA 关注从视觉/语言到动作的策略映射。
- WAM 强调未来世界与动作之间的联合或耦合建模。
- 两者边界可能重叠；判断时应看训练目标和部署时数据流，而不只看论文自称。

### Model-based RL vs WAM

- Model-based RL 是更广泛的算法类别，常学习紧凑动力学并用于规划或价值学习。
- WAM 通常面向大规模具身基础模型，结合视觉/语言/动作，并可能由视频生成或多模态模型扩展而来。

