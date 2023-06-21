---
title: Model 
author: Lotte Bouma
date: 2023-06-20
category: Jekyll
layout: page
permalink: /model
---

# Dit moet nog in 'wat we hebben gedaan taal' (en er moet in wat we echt hebben gedaan)

## Game implementation
As a visual representation of the game, we envision different agents sitting around a table, each holding their cards. All completed sets are shown on the table. To implement this, we want to create 'agent' objects that have their own knowledge about the game. All agents know of the existence of every card, but agents might not know where a certain card is at a certain point in time. Whenever a public announcement is made (in the form of an agent asking a question and the other agent responding), each agent on the table updates their knowledge about the location of each card.

## Simplifications
* Limiting the number of players and card sets, which limits the possible state explosion.
* Fixing the order of getting turns, i.e. instead of a player getting the turn after being asked something, we just go clockwise.
* Eliminating the draw pile, which makes the "I do not have that card" announcement more informative. When that agent draws a card, there is no new uncertainty for other agents about whether that agent still does not have that card. It must be mentioned that some people do not play with a draw pile anyway, so it might not even be a simplification, just another version of the game.
* Not allowing agents to ask others for cards they already have, so that more can be deduced from an agent asking a question.
* If agents can ask for a card, they have to (aka they cannot skip a turn if not necessary)