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
We have modelled the game in Python 3 using the MESA package. This package allows us to easily model multi-agent environments.


### Agent representation

In our implementation, each player is represented by an instance of the QuartetAgent class. This class encapsulates the attributes and behaviours of a player in the game. It contains the following key components:
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
Other simplifications include fixing the order of getting turns. In the original game, the agent that is asked a question (and is not in possession of the asked card) can then ask some other agent for a card. We made sure to just go clockwise, where the agents are always in the same order. Lastly, in the original game there is a draw pile, which we eliminated. This allows the agents to deduce more information from the announcement that a given agent does not have a given card. Whenever that agent would draw from the pile, there would be uncertainty once again about whether that agent has the given card.
It must be mentioned that some people do not play with a draw pile anyway, so it might not even be a simplification, just another version of the game. 

Apart from the game mechanics, we also simplified some of the rules. Firstly, agents are not allowed to ask others for cards they already have in possession. This ensures there can be more information deduced from agents that ask a question. Secondly, players are not allowed to skip turns. This means that agents always have to ask for a card whenever they can.


## Strategies

We have implemented four different strategies that the agents can use to determine what card to ask for and to whom. All strategies take into account the rule that a card can only be requested when the agent already has at least one card of the corresponding quartet group.

### Random strategy
The random strategy is the most simple one. They ask for a random card they still need from a random other agent. It does not consider any knowledge as to who can or cannot be the owner of that card.


### Owner strategy
The owner strategy is a more advanced strategy. The agent starts by asking for all the cards of which the agent knows who possesses that card. When that is done and all ``certain'' cards are obtained, the agent then randomly chooses one of the cards it still needs and asks it from one of the agent it knows could possess it. 
<!-- the agent starts looking in its knowledge base to see if it knows which of the agents could possibly have a card they are looking for.  -->


### Defensive strategy

The defensive strategy begins by identifying and requesting all the cards that the agent is certain about who possesses them, following the same approach as the owner strategy. Next, the agent assesses which card will bring it closest to completing a set. If there exists a set where the agent needs only one more card, it will randomly select an agent from the list of potential owners and ask for that specific card. In cases where the agent needs one more card for multiple sets, it prioritizes the cards it has the least uncertainty about, that is, the cards with the fewest possible owners. If there are no sets requiring only one more card, the agent will apply the same rules for sets that require two more cards and request a card accordingly.

### Aggressive strategy

The aggressive strategy starts the same way as the owner and defensive strategy, by identifying and requesting all the cards that the agent is certain about who possesses them. Then, the agent will identify the agent who forms ``biggest threat'' to win the game and will requests cards from that agent, as long as that agent could possess cards the current agent can ask for. The strategy prioritizes requesting cards which the best-scoring agent is most likely to have, that is, cards for which the fewest number of agents have the possibility of possessing.


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


