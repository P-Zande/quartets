---
title: Model 
author: Lotte Bouma
date: 2023-06-20
category: Jekyll
layout: page
permalink: /model
---


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
* Fact: a fact contains a simple piece of knowledge about whether a specific agent does or does not have a specific card.
* Disjunction: a disjunction contains a collection of facts of which at least one must be true. This is used to represent the statement that an agent has at least one of a given set of cards.
* ExclusiveOr: an ExclusiveOr contains a collection of fact of which exactly one must be true. This is used to represent the statement that a given card can be owned by any agents in a given set, but only one agent can own it.


## Strategies

We have implemented four different strategies that the agents can use to determine what card to ask for and to whom. All strategies take into account the rule that a card can only be requested when the agent already has at least one card of the corresponding quartet group.

Some strategies use a very rudimentary form of probability estimation to determine what card to ask for. For example, according to agent 1, agent 2 is more likely to have card A than card B, because only one other agent than agent 2 could have card A, whereas card B could be owned by one of all 4 other agents. This kind of probability estimation can improve the chances of an agent to win. However, note that an agent's beliefs are not explicitly modelled, and all knowledge in an agent's knowledge base must be true.

### Random strategy
The random strategy is the most simple one. They ask for a random card they still need from a random other agent. It does not consider any knowledge as to who can or cannot be the owner of that card.


### Owner strategy
The owner strategy is a more advanced strategy. The agent starts by asking for all the cards of which the agent knows who possesses that card. When that is done and all ``certain'' cards are obtained, the agent then randomly chooses one of the cards it still needs and asks it from one of the agent it knows could possess it. 
<!-- the agent starts looking in its knowledge base to see if it knows which of the agents could possibly have a card they are looking for.  -->


### Defensive strategy

The defensive strategy begins by identifying and requesting all the cards that the agent is certain about who possesses them, following the same approach as the owner strategy. Next, the agent assesses which card will bring it closest to completing a set. If there exists a set where the agent needs only one more card, it will randomly select an agent from the list of potential owners and ask for that specific card. In cases where the agent needs one more card for multiple sets, it prioritizes the cards it has the least uncertainty about, that is, the cards with the fewest possible owners. If there are no sets requiring only one more card, the agent will apply the same rules for sets that require two more cards and request a card accordingly.

### Aggressive strategy

The aggressive strategy starts the same way as the owner and defensive strategy, by identifying and requesting all the cards that the agent is certain about who possesses them. Then, the agent will identify the agent who forms ``biggest threat'' to win the game and will requests cards from that agent, as long as that agent could possess cards the current agent can ask for. The strategy prioritizes requesting cards which the best-scoring agent is most likely to have, that is, cards for which the fewest number of agents have the possibility of possessing. If the top-scoring agent cannot have any card that the current agent can ask for, the second-highest agent will be asked instead, et cetera.


## Knowledge updates

At the start of the run, each agent gets some cards. For all other cards, it add an ExclusiveOr object to its knowledge base, which represents that for each card, it must be owned by one of the other agents.

After every public announcement, each agent updates the knowledge base of the corresponding quartet group. The specific shape of the announcements is discussed in section Logic. Whenever an agent learns a new Fact, it iterates over all pieces of knowledge it already has and updates them accordingly. If the new fact satisfies a Disjunction or ExclusiveOr, this knowledge can be removed as it no longer contains additional information. If it makes a certain fact in a Disjunction or ExclusiveOr impossible, the agent knows that one of the other facts then must be true. The fact that has been made impossible will be removed from the Disjunction or ExclusiveOr. If it makes another Fact impossible, that means that the new Fact indicates a change of ownership of the cards. The old fact will be deleted. Additionally, if an agent learns that a specific agent owns a card, it will also add to its knowledge base the facts that all other agents do not own that card.

If one of the Disjunction or ExclusiveOr objects eventually contains only a single fact, we can conclude that that given fact must be true; all other facts that were previously part of the object have been deemed to be impossible. This new fact is the also added to the knowledge base, using the protocol described above. 




<!--

negation: ¬
implies: →
twee kanten implies: ↔

or: ∨
and: ∧
exclusive or: ⊕

dinges: ⊢
andere kant op dinges: ⊣
modeldinges: ⊨
-->


