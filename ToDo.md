---
layout: default
---

## Misc. items to be categorized


### Jargons
- Markov Decision Processes
Given a specific model, the MDP tries to predict your future state based on your last state and your last action. Keep in mind that after each action, the decision maker is given a reward. The algorithm tries to decide the best course of action to maximize the reward.

In your model, you need a graph of all states, all possible actions for each states and a transition probability matrix : probability of going to state s2 from state 1 choosing action a1. You also need the reward value from transition from state s_i to state s_i+1.

- Hidden Markov Models
For HMM, you have a graph of states. A probability of state transitions. When you transition from state i to state k, the HMM emits a symbol with probability j. In a HMM the states are always hidden and you cannot observe them. However you can emit the 'guess state' as the emission symbol.

Being in state i, if you have observation y, you have v chance of emitting symbol w.

- Bayesian Networks
Where Markov Models only based their result on the last state (one variable), bayesian network based their result on n variables. In a Bayesian network, you can ask questions like what is the chance of z given that w,k,z.

