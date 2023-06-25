---
title: Discussion 
author: Lotte Bouma
date: 2023-06-20
category: Jekyll
layout: page
permalink: /discussion
---


## Conclusion
What we found in the results is that for some strategies it is advantageous to start first. There is a small advantage when using simple strategies to be able to ask for cards first. With more complicated strategies, this advantage was not seen as clearly.

When putting the different strategies against each other, we found that the defensive strategy was the best. The random strategy was the worst followed by the owner strategy, which makes sense. It is interesting that the defensive strategy is the best. This could be because in this strategy the agent will ask for cards that are most likely to help the agents complete a set. This makes this strategy the most focused on winning. The aggressive strategy is also good, but its aim is to take cards away from agents with the highest scores, which doesn't always help the agent win.

When comparing the advantage of starting to the disadvantage of using a slightly worse strategy, we found that the strategy matters more than the play order. This means that even though starting can give a slight advantage, it's not enough of an advantage if the other player is simply better.

The answer to our research question is that the defensive strategy gives the highest chance to win and play order influences the chance to win slightly, but this is only noticable when every player uses exactly the same strategy.


## Limitations and future work

One of the simplifications we made was that the order of turns was fixed, after an agent unsuccessfully requested a card. Given that the results have shown that the order of turns matter, using a fixed order instead of a dynamic order is likely to have affected the results. Further research could compare these two situations to investigate this.


Another noteworthy limitation to our study was that we had eliminated the draw pile, which is often used when Quartets is played in real life. A draw pile would limit the knowledge advantage that agents that do not start have, while not directly limiting the advantage gained by going first. We expect the advantage of the first agent to increase in this scenario, but an experiment to confirm our suspicion is outside the scope of this project.

A third possible direction of research could be to investigate whether there could be any strategic advantage for an agent to ask for a card it already owns. In our project, we have disallowed agents to do this, although it is possible that there would be value in allowing agents to do so.