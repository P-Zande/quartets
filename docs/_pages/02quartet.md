---
title: Quartet 
author: Lotte Bouma
date: 2023-06-20
category: Jekyll
layout: page
permalink: /quartet
---

## The Rules
Quartets is a card game which can be played by two or more people, where the objective is to collect the most sets of four cards. These sets can be of any theme: animals, colours, people, etc. All cards show the names of the other three cards that belong to the set as well:


[![Example of a quartet set](https://www.semmie.net//Files/7/113000/113715/ProductPhotos/1920x1080/360305641.jpg)](https://www.semmie.net//Files/7/113000/113715/ProductPhotos/1920x1080/360305641.jpg)
<!-- [![Example of a quartet set](/assets/images/kwartet1.jpg)](https://www.semmie.net//Files/7/113000/113715/ProductPhotos/1920x1080/360305641.jpg) -->
<!-- [![Example of a quartet set]({{ page.image | relative_url }})](https://www.semmie.net//Files/7/113000/113715/ProductPhotos/1920x1080/360305641.jpg) -->
<!-- <img src="/assets/images/kwartet1.jpg" alt="Example of a quartet set"> -->
*Figure 1: An example of a full quartet set*

The number of sets usually depends on the company that publishes the set. The game starts by giving each player 7 cards. The rest of the cards are made into the draw pile. Rules around who can start depend per household, sometimes the youngest player can start, sometimes the player left of the dealer. Each round is the same, which will be explained in the example below:

For our example we have three players: Alice, Bob, and Charlie.
It's Alice's turn, and she asks another player, in this case Bob, for a card by saying out loud: "Bob, do you have the card 'Blij' of the set 'Gevoelens'?" (See Figure 1). All players hear this statement. Alice is only allowed to ask Bob for a card from a certain set if she is in possession of at least one of the other cards of this set. Now two scenarios can happen:

1. Bob is in possession of the 'Blij' card, and has to give it to Alice. Alice can now ask another question to either Bob or another player (Charlie).
2. Bob does not have the 'Blij' card. Now Alice has to draw a card from the draw pile and Bob (the person Alice asked the question to) can now start his turn.

When a player has completed a set, they place this set on the table in front of them. This indicates to all players which sets have been completed and how many completed sets each player has. When all sets of cards have been placed on the table, i.e. when no player holds any cards in their hands anymore and the draw pile is empty, the game is finished. The player with the most complete sets wins the game.

A key difference between this game and the game 'Go Fish' is that, in this game, the player requests a specific card from a set, whereas in Go Fish, the player requests any and all cards from a specific set. This also has consequences for what knowledge can be deduced from the questions and answers. Players are allowed to ask others for cards they already have, in an effort to confuse others or to avoid others having knowledge about them.

## Simplifications
We have made some simplifications to the game mechanics and setup. To ensure the number of possible states does not explode, we have limited the number of players and card sets to NOG EVEN INVULLEN. 
Other simplifications include fixing the order of getting turns. In the original game, the agent that is asked a question (and is not in possession of the asked card) can then ask some other agent for a card. We made sure to just go clockwise, where the agents are always in the same order. Lastly, in the original game there is a draw pile, which we eliminated. This allows the agents to deduce more information from the announcement that a given agent does not have a given card. Whenever that agent would draw from the pile, there would be uncertainty once again about whether that agent has the given card.
It must be mentioned that some people do not play with a draw pile anyway, so it might not even be a simplification, just another version of the game. 

Apart from the game mechanics, we also simplified some of the rules. Firstly, agents are not allowed to ask others for cards they already have in possession. This ensures there can be more information deduced from agents that ask a question. Secondly, players are not allowed to skip turns. This means that agents always have to ask for a card whenever they can.
