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
As a visual representation of the game, we envision different agents sitting around a table, each holding their cards. All completed sets are shown on the table. To implement this, we have created 'agent' objects that have their own knowledge about the game. All agents know of the existence of every card, but agents might not know where a certain card is at a certain point in time. Whenever a public announcement is made (in the form of an agent asking a question and another agent responding), each agent on the table updates their knowledge about the card and its location.

## Simplifications
We have made some simplifications to the game mechanics and setup. To ensure the number of possible states does not explode, we have limited the number of players and card sets to NOG EVEN INVULLEN. 
Other simplifications include fixing the order of getting turns. In the original game, the agent that is asked a question (and is not in possession of the asked card) can then ask some other agent for a card. We made sure to just go clockwise, where the agents are always in the same order. Lastly, in the original game there is a draw pile, which we eliminated. This makes the "I do not have that card" announcement more informative, as when an agent can draw cards from a draw pile, there is still uncertainty for other agents about whether that agent has that card. DIT IS EEN BEEEEETJE EEN VAGE ZIN.
It must be mentioned that some people do not play with a draw pile anyway, so it might not even be a simplification, just another version of the game. 

Apart from the game mechanics, we also simplified some of the rules. Firstly, agents are not allowed to ask others for cards they already have in possession. This ensures there can be more information deduced from agents that ask a question. Secondly, players are not allowed to skip turns. This means that agents always have to ask for a card whenever they can.

## Logic
For this project we used Public Announcement logic. Every time an agent asks another agent for a card this is a public announcement. Each time an agent responds with either that they do have that card and proceed to give it to the other agent, or that they do not have that card, it is a public announcement. After each announcement, all agents update their knowledge base to what they now know. 

BLABLA LOGIC SYMBOLS

negation: $\neg$
implies: $\rightarrow$
twee kanten implies: $\leftrightarrow$
or: $\vee$
and: $\wedge$
dinges: $\vdash$
andere kant op dinges: $\dashv$
modeldinges: $\models$ 