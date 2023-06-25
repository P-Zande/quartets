---
title: Results 
author: Lotte Bouma
date: 2023-06-20
category: Jekyll
layout: page
permalink: /results
---


The results of experiment 1 can be found in the following graph.
![all_wins](./assets/images/all_wins.png)
What we can see here is that the random strategy clearly does the worst. This could be expected because this strategy does not use any knowledge or logic. The next best strategy is the owner strategy. This makes sense because this strategy uses knowledge and logic to figure out what cards it should ask for, but then it just chooses randomly from the possible cards when it's uncertain about who exactly owns the cards. The two best strategies are the aggressive and defensive strategies. This is because these strategies do the same as the owner strategy, but then also use a strategy to determine what card to ask for when it's not fully certain about who owns which cards. The best strategy is the defensive strategy, which is interesting to learn.

The results of experiment 2, where all agents use the random strategy, can be seen in the following graph.
![random_wins](./assets/images/random_wins.png)
When all agents use the random strategy, the agent that starts has the highest chance of winning, although the difference is small.

The results of experiment 3, where all agents use the owner strategy, can be seen in the following graph.
![owner_wins](./assets/images/owner_wins.png)
When all agents use the owner strategy, the agent that starts has the highest chance of winning. The higher an agent is in the play order, the higher its chance of winning is. The differences are still small.

The results of experiment 4, where all agents use the defensive strategy, can be seen in the following graph.
![defensive_wins](./assets/images/defensive_wins.png)
In this case where all agents use the defensive strategy, the differences are very small. It does not seem like we are able to say which place in the running order gives an agent the highest chance of winning.

The results of experiment 5, where all agents use the aggressive strategy, can be seen in the following graph.
![aggressive_wins](./assets/images/aggressive_wins.png)
When all agents use the aggressive strategy, the differences are again very small. There does not seem to be a big advantage of being at a certain place in the play order.

In experiment 6, the first agent uses the aggressive strategy because it was shown to be second-to-best, and the rest of the agents use the defensive strategy, because it was shown to be the best. The results of this can be seen in the following graph.
![advantage_wins](./assets/images/advantage_wins.png)
We can see here that starting first in the game is not enough of an advantage for agent 1 to win the most games. This shows us that strategy still matters more than play order.