# All-Bradly-Stadie-Papers
Every one of Bradly Stadie's papers


## Chronological Order
1. Simulating the Stochastic Dynamics and Cascade Failure of Power Networks (2014)
2. Incentivizing Exploration in Reinforcement Learning with Deep Predictive Models (2015)
3. Third-Person Imitation Learning (2017)
4. One-Shot Imitation Learning (2017)
5. Some Considerations on Learning to Explore via Meta-Reinforcement Learning (2018)
6. Evolved Policy Gradients (2018)
7. Transfer Learning for Estimating Causal Effects Using Neural Networks (2018)
8. Sampling Aware Reinforcement Learning (2019)
9. Learning to Learn from Flawed, Failed, and Figurative Demonstrations (2019)
10. One-Shot Pruning of Recurrent Neural Networks by Jacobian Spectrum Evaluation (2019)
11. One-Demonstration Imitation Learning (2019)



## Sorted By Topic

Some papers appear under more than one topic due to crossover. 

### Exploration 
1. Incentivizing Exploration in Reinforcement Learning with Deep Predictive Models: At the time this paper was written, most exploration in deep RL was epsilon greedy. We wanted a more efficient method of exploration, following the intution behind "Near-Bayesian Exploration in Polynomial Time." We ended up achieving better exploration by learning a dynamics model and using the misprediction error from this model as a proxy for how well the agent understood that area of the environment. At the time of release, this paper achieved several state of the art results on Atari. 

2. Some Considerations on Learning to Explore via Meta-Reinforcement Learning: The core point of this paper is somewhat subtle. In supervised learning, the data distribution is static and typically fixed. This is false in RL. The sampled data distribution depends on the policy, which implicitly tells you how to weight each part of the state space. It turns out that this is important for second-order meta learning methods such as MAML, because the shift in data distribution has to be correctly accounted for while computing the second order gradient terms. In this paper, we draw connections between the impact of sampling on meta RL and the exploration problem. We show that accounting for the impact of sampling on learning leads to better exploration and better performance. 


### Imitation Learning 
1. Third-Person Imitation Learning: Sometimes, robots need to copy robots that are different from themselves. The other robot might look different or have cameras in different places. Most imitation techniques based on generative models can not handle this problem setting, because they rely on a discriminator that rewards the agent for generating frames that look different from the expert. However, every frame generated by the expert and the agent will look different, because the agents themselves look different! The core of this paper is an algorithm for finding a representation such that the mutual information between the representation of agent and expert states is minimized. 

2. One-Shot Imitation Learning: We use an LSTM + a novel form of attention to train a policy that can consume a video of a robot completing a task and then complete the same task itself. The agent need only consume one video of the task being completed. Hence, the imitation learning is one-shot. 

3. Learning to Learn from Flawed, Failed, and Figurative Demonstrations: We use second order meta learning plus a few tricks to train an agent that is capable of completing a task, even when the expert demonstration fails. Basically, the agent meta learns a prior that can help it to infer what the expert intended, even in the case when the expert fails.

4. One-Demonstration Imitation Learning: One of the drawbacks of One-shot imitation learning was the massive quantity of data required to train the one-shot imitation policy. Moreover, the policy had a hard time generalizing to tasks that were substantially different from the training tasks. This paper tries to address both of those problems by using unsupervised learning to generate a pseudo-uniform prior over the task space. The key idea is to use self-imitation as a metric for an unsupervised task's novelty. Using this method, we can learn to imitate an expert from only a single demonstration, with no additional demonstrations required during training time.

### Meta Learning 
1. Evolved Policy Gradients: We ponder the question of learning better reward functions in RL. We want to know if it is possible to meta learn a reward function that will still provide interesting behavior in novel environments, even when no human-provided reward is specified. Our algorithm shows how to combine a random search outer loop with a policy gradient inner loop, a process that requires the use of 1-D convolutions to become tractable. 

2. Sampling Aware Reinforcement Learning: Essentially a follow-up to Evolved Policy Gradients. This paper shows how we can use an alternative architecture with conditional layer normalization to bypass the need for a costly random search. Includes more discussion of the interplay between sampling and RL first discussed in Some Considerations on Learning to Explore via Meta-Reinforcement Learning. 


6. Transfer Learning for Estimating Causal Effects Using Neural Networks: This paper was a crossover with statistics and political science. We show how to leverage multiple related datasets in the setting of a hard political science problem. Rather than learning a large complex model that optimizes over all data-sets at once, we can instead use techniques from meta learning to learn an initialization where the gradients on future datasets will generally be large. We demonstrate the effectivness of this technique on various real world datasets wherein political scientists try to measure the impact of various voter encouragement techniques on voter turnout.  


#### Papers listed in other sections that have significant meta learning components
1. Some Considerations on Learning to Explore via Meta-Reinforcement Learning: See exploration. 

3. Learning to Learn from Flawed, Failed, and Figurative Demonstrations: See imitation learning

4. One-Demonstration Imitation Learning: See imitation learning

5. One-Shot Imitation Learning: See imitation learning

### Pruning
1. One-Shot Pruning of Recurrent Neural Networks by Jacobian Spectrum Evaluation: Some recent progress has been made on one-shot pruning of neural networks. In particular, some interesting recent work has connected the one-shot pruning objective to NTKs. This paper examines recent one-shot pruning methods in the context of recurrent neural networks, and provides some analysis of why these new techniques largely fail in this problem setting. We then derive a new method for one-shot pruning of RNNs and show it to be effective. 

### Other 
1. Simulating the Stochastic Dynamics and Cascade Failure of Power Networks: This was an early project in stochastic optimization that I worked on during my undergraduate studies. We consider a specific type of stochastic optimization problem that arises in power-systems. We also show how to solve this problem in a fairly general setting. 
