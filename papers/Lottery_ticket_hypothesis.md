# [The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks](https://arxiv.org/pdf/1803.03635.pdf)
* **Tags**: Pruning
* **ICLR 2019**

## Key Points
1. **The Lottery Ticket Hypothesis**: Dense, randomly-initialized, feed-forward networks contain subnetworks (winning tickets) that—when trained in isolation reach test accuracy comparable to the original network in a similar number of iterations.
2. The winning tickets we find have won the initialization lottery: their connections have initial weights that make training particularly effective.
3. **Idea**: If a network can be reduced in size, why do we not train this smaller architecture instead in the interest of making training more efficient as well. 
4. "Training a pruned model from scratch performs worse than retraining a pruned model, which may indicate the difficulty of training a network with a small capacity"
5. Identifying winning tickets:
    - Identify a winning ticket by training a network and pruning its smallest-magnitude weights.
    - The remaining, unpruned connections constitute the architecture of the winning ticket.
    - Each unpruned connection’s value is then reset to its initialization from original network before it was trained.
6. **Steps**: (One Shot Pruning)
    -  Randomly initialize a neural network f(x;θ0)(where θ_0∼Dθ).
    -  Train the network for j iterations, arriving at parameters θj.
    -  Prune p% of the parameters in θj, creating a mask m.
    -  Reset the remaining parameters to their values in θ0, creating the winning ticket f(x; mθ0)
7. **Iterative pruning approach**: which repeatedly trains, prunes, and resets the network over n rounds.
Results show that iterative pruning finds winning tickets that match the accuracy of the original network at smaller sizes than does one-shot pruning.
8. **Implications**
    - Improved Training Performance
    - Design Better Networks
    - Improve theoretical understanding of neural networks.
9. **Discussion**
    - The importance of winning ticket initialization: When randomly reinitialized, a winning ticket learns more slowly and achieves lower test accuracy, suggesting that initialization is important to its success.
    - The initialization that gives rise to a winning ticket is arranged in a particular sparse architecture
    - *"larger networks might explicitly contain simpler representations"*
    - Winning tickets can reach accuracy equivalent to that of the original, unpruned network, but with significantly fewer parameters.
10. **Results**\
In deeper networks, the proposed pruning-based strategy for finding winning tickets is sensitive to the learning rate: it requires warmup to find winning tickets at higher learning rates.\ 
The winning tickets we find are 10-20% (or less) of the size of the original network. Down to that size, they meet or exceed the original network’s test accuracy(commensurate accuracy) in at most the same number of iterations (commensurate training time).\
When randomly reinitialized, winning tickets perform far worse, meaning structure alone cannot explain a winning ticket’s success.