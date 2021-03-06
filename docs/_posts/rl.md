## 强化学习
- [莫烦强化学习的课程](https://mofanpy.com/tutorials/machine-learning/reinforcement-learning/)

### DQN


### Actor-Critic
- [Actor-Critic算法Paper](https://proceedings.neurips.cc/paper/1999/file/6449f44a102fde848669bdd9eb6b76fa-Paper.pdf)
- [A3C Paper-Asynchronous Methods for Deep Reinforcement Learning](https://arxiv.org/pdf/1602.01783.pdf)
- [TD-Regularized Actor-Critic Methods](https://arxiv.org/pdf/1812.08288.pdf)
- [PPO Paper](https://arxiv.org/pdf/1707.06347.pdf)

Actor-Critic合并了以值为基础(Q-Learning) 和 以动作概率为基础(如：Policy-Gradient)两类强化学习算法。
A3C 和 PPO 算法均基于Actor-Critic架构， AC本质上是基于时序差分来更新策略，如下图： 

![ac-arch](img/td-error.png)

