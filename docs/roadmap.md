# 8 周具身智能入门路线

默认每周投入 8–12 小时。目标是形成一个能运行、能比较、能解释的最小研究闭环，而不是读完所有论文。

## 总览

| 周 | 主题 | 最小产出 |
| --- | --- | --- |
| 1 | MDP、控制与机器人接口 | 手写一页 MDP/控制频率/动作空间说明 |
| 2 | 行为克隆与 Offline RL | 跑通 BC，解释分布偏移 |
| 3 | Online RL | 跑通 PPO 或 SAC，画学习曲线 |
| 4 | World Model / Model-based RL | 跑一个 TD-MPC2 或 Dreamer 类实验 |
| 5 | VLM → VLA | 拆解 OpenVLA/StarVLA 的数据流 |
| 6 | π0.5 与开放世界泛化 | 做论文复盘与 ablation 设计 |
| 7 | WAM 与 Fast-WAM | 画清训练期/测试期计算图并比较延迟 |
| 8 | RL 后训练与综合项目 | 在统一基准形成可复现实验报告 |

## Week 1｜MDP、控制与机器人数据

### 学什么

- 状态 $s$、观测 $o$、动作 $a$、奖励 $r$、折扣 $\gamma$。
- 部分可观测性：相机图像通常不是完整状态。
- 动作空间：joint position / velocity / torque、end-effector pose、delta action。
- policy rate、control rate、action horizon、闭环 replanning。

### 做什么

1. 阅读 Sutton & Barto 的 MDP、TD 和 policy gradient 相关章节。
2. 在 Gymnasium 或 MuJoCo 跑一个随机策略并记录 transition。
3. 为一个机械臂任务写出 observation、action、reward 和 termination。

### 验收

你能解释“图像输入 + 末端位姿 delta 输出”的策略为何是 POMDP，以及提高 action chunk 长度会带来什么延迟/反馈权衡。

## Week 2｜行为克隆与 Offline RL

### 学什么

- 最大似然行为克隆、covariate shift、DAgger 思想。
- Offline RL 的分布外动作与 Q 过估计。
- CQL、IQL、Decision Transformer 三条路线的差异。

### 做什么

- 用 robomimic 跑一个 BC baseline，或用 LeRobot 训练一个小策略。
- 改变示范数量/质量，记录成功率。
- 读 Offline RL Tutorial，再选 CQL 或 IQL 精读。

### 验收

提交一张表：示范数、训练 loss、闭环成功率、三个主要失败模式。不要用训练 loss 代替控制效果。

## Week 3｜Online Model-free RL

### 学什么

- on-policy vs off-policy。
- PPO 的 clipped update；SAC 的最大熵与 replay buffer。
- reward design、探索、样本效率与安全。

### 做什么

- 在简单连续控制任务上跑 PPO 或 SAC。
- 至少做 3 个 seed，画均值和方差。
- 记录环境步数，而不只记录 wall-clock 时间。

### 验收

你能说明 PPO 和 SAC 分别在哪些数据复用、稳定性和实现复杂度上取舍。

## Week 4｜World Model 与 Model-based RL

### 学什么

- 表征模型、潜空间动力学、奖励/终止预测。
- imagined rollout、MPC、actor-critic through imagination。
- model bias、uncertainty 与 planning horizon。

### 做什么

- 精读 World Models、Dreamer 或 TD-MPC2。
- 运行 TD-MPC2 的小环境配置，或复现一个潜空间 rollout。
- 对比 model-free 基线的环境步数与训练计算量。

### 验收

画出训练和部署两张计算图，标出真实环境数据、模型生成数据和策略更新分别在哪里发生。

## Week 5｜从 VLM 到 VLA

### 学什么

- vision encoder / VLM backbone、语言指令、action head。
- 离散 action token、连续回归、diffusion、flow matching。
- action chunking、temporal ensemble、跨本体动作归一化。

### 做什么

- 读 RT-1/RT-2，再读 OpenVLA 或 π0。
- 在 OpenVLA 或 StarVLA 中定位：dataset、processor、backbone、action head、loss、rollout evaluator。
- 用预训练 checkpoint 完成一次推理或离线 batch 前向。

### 验收

提交一张模块表：输入/输出 shape、token/连续动作、loss、训练数据、推理频率、机器人适配点。

## Week 6｜π0.5 与开放世界泛化

### 学什么

- 异构数据协同训练：多机器人数据、web 数据、语义子任务与动作监督。
- 高层语义预测和低层动作之间的关系。
- seen / unseen environment、task、object、embodiment 的不同泛化层级。

### 做什么

- 精读 π0.5 方法图、数据混合和 ablation。
- 阅读 OpenPI 中 π0.5 的配置与 policy 接口。
- 设计一个不需要大规模训练的 ablation：例如移除语言、缩短历史或改变 action horizon。

### 验收

能区分“语言理解泛化”“视觉场景泛化”“技能组合泛化”“跨本体迁移”，并为每项选择不同评测。

## Week 7｜WAM 与 Fast-WAM

### 学什么

- WAM 的级联式和联合式路线。
- 显式未来生成 vs 潜空间未来表征。
- 视频协同训练的表征收益与测试时生成成本。

### 做什么

- 先读 WAM survey 的定义与 taxonomy，再读 Fast-WAM。
- 在 FastWAM 代码里定位 video objective、action objective 和 inference path。
- 设计统一延迟评测：相同硬件、batch size、相机数、分辨率和 action horizon。

### 验收

提交一张二维表：是否训练期预测未来 × 是否测试期生成未来，并填写性能、延迟、显存和失败模式。

## Week 8｜RL 后训练与综合项目

### 推荐题目

**在 LIBERO 或 ManiSkill 上比较 BC/VLA baseline 与 RL 后训练版本。**

### 路线

1. 固定任务、数据、初始 checkpoint 与评测协议。
2. 跑通 StarVLA baseline。
3. 参考 RLinf 的 StarVLA/ManiSkill 示例做 RL 后训练。
4. 比较成功率、环境步数、GPU 时、推理延迟和 OOD 任务。
5. 分析 reward hacking、灾难性遗忘与训练不稳定。

### 最终报告模板

```text
1. 问题与假设
2. 环境、数据和策略接口
3. 基线与唯一改动
4. 训练预算与评测协议
5. 主结果（均值、方差、seed）
6. 失败案例
7. 计算成本和推理延迟
8. 结论、局限与下一步
```

## 硬件较少时的替代路线

| 条件 | 建议 |
| --- | --- |
| 无 GPU | 阅读 + Gymnasium 小任务 + 代码结构追踪 |
| 单张消费级 GPU | robomimic/ManiSkill 小任务、预训练 VLA 推理或参数高效微调 |
| 无真实机器人 | LIBERO、ManiSkill、robosuite；重点做评测严谨性 |
| 有低成本机械臂 | 先用 LeRobot 做数据采集和 BC，不立即做在线 RL |
| 多 GPU | 再考虑 StarVLA + RLinf、较大 VLA/WAM 微调 |

## 每周复盘的五个问题

1. 我本周真正跑通了什么？
2. 训练信号来自示范、奖励还是未来预测？
3. 最主要的分布偏移是什么？
4. 成功率之外，成本和失败模式如何？
5. 下周只允许改一个变量，会改什么？

