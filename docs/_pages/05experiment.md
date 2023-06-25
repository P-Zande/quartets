---
title: Experiment 
author: Perry van der Zande
date: 2023-06-20
category: Jekyll
layout: page
permalink: /experiment
---

## Experimental Setup
We performed multiple experiments. For every experiment we used a setup with four agents. We made them play 1000 games for every experiment.

In the first experiment, we compared the four different strategies to each other. For every game, the four different agents each use a different strategy. Which agent uses which strategy changes every round, so that the play order does not influence this first experiment.

For the second through fifth experiment, every agent uses the same strategy. Here, we look at to what extent the play order influences the winner of the game. We do one experiment per strategy, to see whether the play order has the same impact on every strategy.

In the last experiment, we give the agent that starts every game the second-to-best strategy, and we give every other agent the best strategy. This will show us whether the play order can actually have a significant difference when an agent that normally shouldn't win gets to start first.