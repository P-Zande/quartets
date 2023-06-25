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
We have modelled the game in Python 3 using the MESA package. This package allows to easily model multi-agent environments.


### Agent representation

In the implementation, each player is represented by an instance of the QuartetAgent class. This class encapsulates the attributes and behaviours of a player in the game. It contains the following key components:
* Hand: an object containing all quartet groups and cards.
* Score: the current number of completed quartet sets of the agent
* Strategy: the strategy that the current agent uses to choose the questions it asks.

### Object representation

To represent the relevant objects of the game itself, we have created the following objects:

* QuartetCard: This represents an individual card. It contains the name of the card, as well as the group of cards it belongs to. In our implementation, each agent has an instance of each card in the game. The card contains an attribute to register whether or not the agent currently owns this card. 
* QuartetGroup: This represents a single Quartet group, consisting of four cards. It also contains all the knowledge the agent has on who owns what card in the group.
* Hand: This represents the collection of all QuartetGroups that an agent has. The agent interacts with its cards and its knowledge about the location of the other cards via this object.


### Knowledge representation

To represent the knowledge of an agent about the state of the game, we use the following representations:



## Simplifications
We have made some simplifications to the game mechanics and setup. To ensure the number of possible states does not explode, we have limited the number of players and card sets to NOG EVEN INVULLEN. 
Other simplifications include fixing the order of getting turns. In the original game, the agent that is asked a question (and is not in possession of the asked card) can then ask some other agent for a card. We made sure to just go clockwise, where the agents are always in the same order. Lastly, in the original game there is a draw pile, which we eliminated. This makes the "I do not have that card" announcement more informative, as when an agent can draw cards from a draw pile, there is still uncertainty for other agents about whether that agent has that card. DIT IS EEN BEEEEETJE EEN VAGE ZIN.
It must be mentioned that some people do not play with a draw pile anyway, so it might not even be a simplification, just another version of the game. 

Apart from the game mechanics, we also simplified some of the rules. Firstly, agents are not allowed to ask others for cards they already have in possession. This ensures there can be more information deduced from agents that ask a question. Secondly, players are not allowed to skip turns. This means that agents always have to ask for a card whenever they can.


## Strategies
Agents using the random strategy use barely any logic. They ask for a random card they still need (and are allowed to ask for) from a random other agent. This is done without considering whether or not that other agent is a possible owner of the card.

The owner strategy is a more advanced strategy. The agent starts by asking for all the cards it is allowed to ask for and is certain of which of the other agents is in posession of that card. When that is done and all certain cards are obtained, the agent starts looking in its knowledge base to see if it knows which of the agents could possibly have a card they are looking for. It then randomly chooses one of the cards it still needs and asks it from one of the agent it knows might posess it. 

The defensive strategy starts the same as the owner strategy, with asking for all the cards it is certain about who has that specific card. After that, it looks at which card it needs the most. If there is a set of cards where the agent only needs one more card to complete it, it will choose to ask for that card from an agent of which it knows that it could possibly have that card (chosen randomly from the list of possible owners). If there are multiple sets of cards the agent only needs one more of, it looks at which of those cards it is least uncertain about, so which of the cards has the smallest number of possible owners. If there is no set the agent only needs one more card of, it will ask for a card from a set where it needs two of, using the same rules as for needing one card.

The aggressive strategy looks at which cards other agents still need, instead of looking for completing an agents own set. It follows almost the same strategy as the defensive strategy, however, instead of looking at which card it needs the most itself, it tries to make sure the agent with the highest score is 'attacked'. BLABLA


## Logic
For this project we used Public Announcement logic. Every time an agent asks another agent for a card this is a public announcement. Each time an agent responds with either that they do have that card and proceed to give it to the other agent, or that they do not have that card, it is a public announcement. After each announcement, all agents update their knowledge base to what they now know. 

DIT MOET NOG HERSCHREVEN, DIT IS EEN NOTE VAN TIJDENS PROGRAMMEREN: We use chance in the strategies. This is not necessarily very logic, but because it is a separate thing from the knowledge base it should be okay. (We use logic to make the knowledge base, and then use some chance to be able to strategise using that knowledge)

BLABLA LOGIC SYMBOLS

negation: ¬
implies: →
twee kanten implies: ↔

or: ∨
and: ∧
exclusive or: ⊕

dinges: ⊢
andere kant op dinges: ⊣
modeldinges: ⊨


