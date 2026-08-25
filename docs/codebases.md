# 代码仓、数据与基准

优先链接官方仓库或官方项目页。版本、硬件和许可证可能变化，实际使用前请查看对应仓库的 README 与 release。

## 1. 用户指定的核心仓库

| 项目 | 定位 | 推荐入口 |
| --- | --- | --- |
| StarVLA | 模块化 VLA 研究与工程平台 | [GitHub](https://github.com/starVLA/starVLA) · [Docs/Project](https://starvla.github.io/) · [Paper](https://arxiv.org/abs/2604.05014) |
| RLinf | 面向具身/智能体基础模型的可扩展 RL 后训练基础设施 | [GitHub](https://github.com/RLinf/RLinf) · [Docs](https://rlinf.readthedocs.io/) · [Paper](https://arxiv.org/abs/2509.15965) |
| FastWAM | Fast-WAM 官方训练与评测代码 | [GitHub](https://github.com/yuantianyuan01/FastWAM) · [Project](https://yuantianyuan01.github.io/FastWAM/) · [Paper](https://arxiv.org/abs/2603.16666) |
| OpenPI | Physical Intelligence 的 π0 / π0.5 开源实现与模型入口 | [GitHub](https://github.com/Physical-Intelligence/openpi) · [π0.5 Paper](https://arxiv.org/abs/2504.16054) |

StarVLA 与 RLinf 的直接组合示例：

- [RL on StarVLA Models](https://rlinf.readthedocs.io/en/latest/rst_source/examples/embodied/starvla.html)
- [RL with ManiSkill Benchmark](https://rlinf.readthedocs.io/en/latest/rst_source/examples/embodied/maniskill.html)

## 2. VLA / 模仿学习

| 项目 | 适合做什么 | 链接 |
| --- | --- | --- |
| OpenVLA | 阅读一个完整开源 VLA 的训练、微调和部署 | [GitHub](https://github.com/openvla/openvla) |
| Octo | 通用机器人策略与多数据集预训练/微调 | [GitHub](https://github.com/octo-models/octo) |
| LeRobot | 低门槛真实机器人数据、策略、训练与设备生态 | [GitHub](https://github.com/huggingface/lerobot) · [Docs](https://huggingface.co/docs/lerobot/) |
| robomimic | 行为克隆与离线示范学习的干净基线 | [GitHub](https://github.com/ARISE-Initiative/robomimic) · [Project](https://robomimic.github.io/) |
| Diffusion Policy | diffusion 动作策略的官方实现 | [GitHub](https://github.com/real-stanford/diffusion_policy) |
| ACT | 低成本双臂操作与 action chunking | [GitHub](https://github.com/tonyzhaozh/act) |
| CALVIN | 长时程语言条件操作与评测 | [GitHub](https://github.com/mees/calvin) · [Paper](https://arxiv.org/abs/2112.03227) |

## 3. RL 与 World Model

| 项目 | 类型 | 链接 |
| --- | --- | --- |
| RLinf | VLA/基础模型的大规模 RL 后训练 | [GitHub](https://github.com/RLinf/RLinf) |
| CleanRL | 单文件 RL 实现，适合学习 PPO/SAC 等算法细节 | [GitHub](https://github.com/vwxyzjn/cleanrl) · [Docs](https://docs.cleanrl.dev/) |
| Stable-Baselines3 | 易用的经典 model-free RL 基线 | [GitHub](https://github.com/DLR-RM/stable-baselines3) · [Docs](https://stable-baselines3.readthedocs.io/) |
| d3rlpy | Offline RL 算法与数据接口 | [GitHub](https://github.com/takuseno/d3rlpy) · [Docs](https://d3rlpy.readthedocs.io/) |
| TD-MPC2 | 潜空间 world model + MPC，覆盖 online 与 multi-task offline | [GitHub](https://github.com/nicklashansen/tdmpc2) · [Project](https://www.tdmpc2.com/) |
| DreamerV3 | 潜空间想象式 model-based RL | [GitHub](https://github.com/danijar/dreamerv3) |
| Minari | Offline RL 数据集 API 与数据目录 | [GitHub](https://github.com/Farama-Foundation/Minari) · [Docs](https://minari.farama.org/) |

## 4. 仿真、环境与基准

| 项目 | 特点 | 推荐用途 | 链接 |
| --- | --- | --- | --- |
| MuJoCo | 成熟、通用的接触动力学仿真 | 经典控制、算法原型 | [GitHub](https://github.com/google-deepmind/mujoco) · [Docs](https://mujoco.readthedocs.io/) |
| Gymnasium | 标准 RL 环境 API | 算法接口与小实验 | [GitHub](https://github.com/Farama-Foundation/Gymnasium) · [Docs](https://gymnasium.farama.org/) |
| ManiSkill | GPU 并行机器人操作、数据生成与评测 | 单机仿真操作、VLA/RL 评测 | [GitHub](https://github.com/mani-skill/ManiSkill) · [Project](https://maniskill.ai/) |
| Isaac Lab | 基于 Isaac Sim 的 GPU 加速机器人学习框架 | 大规模 RL、sim-to-real、复杂传感器 | [GitHub](https://github.com/isaac-sim/IsaacLab) · [Docs](https://isaac-sim.github.io/IsaacLab/) |
| robosuite | MuJoCo 机器人操作任务框架 | 模仿学习、控制器对比 | [GitHub](https://github.com/ARISE-Initiative/robosuite) · [Docs](https://robosuite.ai/) |
| LIBERO | 语言条件、知识迁移与 lifelong 操作 | VLA/IL 标准化评测 | [Project](https://libero-project.github.io/main.html) · [GitHub](https://github.com/Lifelong-Robot-Learning/LIBERO) |
| RoboTwin | 数字孪生数据生成与双臂操作任务 | 操作泛化与大规模数据 | [GitHub](https://github.com/RoboTwin-Platform/RoboTwin) |

## 5. 机器人数据入口

| 数据/生态 | 内容 | 链接 |
| --- | --- | --- |
| Open X-Embodiment | 多机构、多本体机器人轨迹集合 | [Project](https://robotics-transformer-x.github.io/) |
| DROID | 大规模、场景多样的真实机器人操作数据 | [Project](https://droid-dataset.github.io/) |
| BridgeData V2 | 通用机器人操作轨迹 | [Project](https://rail-berkeley.github.io/bridgedata/) |
| LeRobot Datasets | 与 LeRobot policy/device 工具统一的数据格式与社区数据 | [Hugging Face](https://huggingface.co/lerobot) |
| robomimic Datasets | 多质量示范、状态/图像操作数据 | [Docs](https://robomimic.github.io/docs/datasets/overview.html) |

## 6. 按目标选技术栈

| 目标 | 最小组合 | 原因 |
| --- | --- | --- |
| 第一次跑机器人行为克隆 | robomimic + robosuite | 文档完整、数据和基线清晰 |
| 低成本真实机器人入门 | LeRobot + 支持的硬件 | 数据采集、训练和部署接口较统一 |
| 单机 GPU 做操作 RL | ManiSkill + CleanRL/SB3 | GPU 并行环境与算法基线组合直接 |
| 学 model-based RL | TD-MPC2 + DMControl/ManiSkill | 世界模型、价值和 MPC 路径清晰 |
| 学开源 VLA | OpenVLA 或 StarVLA + LIBERO | 代码可读，并有常见评测入口 |
| 做 VLA 的 RL 后训练 | StarVLA + RLinf + LIBERO/ManiSkill | 已有直接集成示例 |
| 研究 WAM 推理效率 | FastWAM + LIBERO/RoboTwin | 对应论文的训练/测试设定 |
| 大规模 sim-to-real | Isaac Lab + RL 框架 | 高吞吐仿真与传感器/机器人生态 |

## 7. 复现实验前的检查单

- [ ] 论文与代码是否对应同一版本/commit？
- [ ] checkpoint、数据集和归一化统计是否匹配？
- [ ] 观测相机数量、分辨率、历史长度是否一致？
- [ ] 动作空间是关节、末端位姿还是 delta control？控制频率是多少？
- [ ] 是否使用 action chunk、temporal ensemble 或 replanning？
- [ ] 评测 seed、任务初始状态与成功判定是否一致？
- [ ] 是否区分训练 GPU 时、环境步数和真实机器人小时数？
- [ ] 推理延迟是否包含视觉编码、未来生成、规划和控制接口？

## 8. 不建议一开始做的事

- 同时安装多个重型仿真器；先选一个跑通闭环。
- 一上来训练 7B 级 VLA；先用预训练 checkpoint 做推理或小规模微调。
- 只比较 success rate，不记录数据量、算力、环境步数与延迟。
- 把视频生成质量当成机器人控制质量；WAM 需要闭环任务指标。
