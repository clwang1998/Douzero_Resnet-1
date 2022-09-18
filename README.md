# 基于深度蒙特卡洛的斗地主算法

Computer game is the core problem of artificial intelligence research at this stage.Computer
game can promote AI from cognitive intelligence to decision intelligence. In the perfect
information game, Deep Reinforcement Learning techniques such as AlphaGo and AlphaGo Zero have made major breakthroughs in Go, defeating top human players. In the
imperfect information game, Carnegie Mellon University and the University of Alberta
also made strides in solving Texas Hold’em. The Imperfect Information Game is an
abstraction and simulation of many real-world problems that have the characteristics of
private game information, a random game environment, dynamic information changes,
and a complex state space, making its exploration and solution a major challenge.
Doudizhu is a typical game with imperfect information and is characterized by
the coexistence of cooperative competition, complex fixed pieces, and long decision
sequences. These problems makes its research a unique challenge. In recent years,
the Doudizhu algorithm represented by DouZero has adopted the Deep Monte Carlo
method and demonstrated a high level of intelligence in the real world. However, the
existing Doudizhu algorithms have the following three problems. First, the initial cards
are distributed randomly, and the winning of the game is affected by luck, making the
performance of the agent unstable. Second, the deep Monte Carlo method requires a
large number of games records as samples. However, the random initialization of the
agent causes the model to generate mainly sparse rewards in the initial phase, resulting
in the vast majority of samples in the experience pool not receiving useful value signals.
The random selection of samples in the experience pool leads to low sample utilization.
Third, due to the unequal status of landowners and farmers in the game, there are differences in the intelligence level of the different agents, and the winning Percentage and
of Peasants are significantly higher than those of landlord, indicating that the intelligence level of landlord is weaker. In order to solve the above problems, three aspects
are studied in this paper: the design of the network structure, the sampling methods and
the intelligence training methods.

1. For unstable performance of DouZero, we use a residual network for reinforcement learning’s 𝑄-network. In order to improve the generalization ability of the network, the residual network model is introduced to design 𝑄-network for reinforcement
learning. Using the residual network and the long- and short term memory network as
state network, we extracted the bucket features such as deeper situation information and
history records in Doudizhu. At the same time, we combined the deep Monte Carlo
method of residual networks to reduce the variance of the agent’s winning percentage
and the average difference in point after training. That improved the overall intelligence
of the Doudizhu algorithm and beat the current leading DouZero algorithm with an
average winning fraction of 0.544.
2. For low sample utilization, the prioritized experience replay is introduced to
deep Monte Carlo method.In this paper, the sample priority is defined by TD-error,
and the probability of sampling at the time of sampling is proportional to the priority,
so that the model can preferentially use the samples with the larger TD-error in the
experience pool. Since prioritized experience replay is also randomized, all samples
have a chance of being captured, and sample diversity is also increased. By combining
the deep Monte Carlo method with prioritized experience replay, we can significantly
reduce the convergence time of the model and improve the use of samples in the model.
3. For landlords’low intelligence problem, multi-body learning algorithm is introduced as a training method for the agents. In this work, based on the multi-agent reinforcement learning algorithm, different agents are trained differently to cope with different roles in the game, and the multi-body cooperation is achieved by interactive learning
of the decision task. By dividing the players into two groups: Peasants and landlords,
forming two-team zero-sum game and solving the Nash equilibrium, the landlord is then
trained individually with the Minmax Q-learning. We combine a Deep Monte Carlo approach with multi-agent reinforcement learning to significantly improve the landlords’
winning percentage and increase their intelligence.
Keywords: Imperfect Information Game, Doudizhu, Deep Monte Carlo, Residual Network, Prioritized Experience Replay, Multi - agent reinforcement learning
