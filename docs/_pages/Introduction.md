---
title: Introduction 
author: Lotte Bouma
date: 2023-06-20
category: Jekyll
layout: post
permalink: /introduction
---

For our project we are planning to model the card game quartets. This is a game played by children from a young age, as it is quite easy to explain and understand. We will explain how it works, how it is relevant for the course LAMAS, how we are planning to implement the game and any simplifications to the original game.

## The Game
Quartets is a card game which can be played by two or more people, where the objective is to collect the most sets of four cards. These sets can be of any theme: animals, colours, people, etc. All cards show the names of the other three cards that belong to the set as well 


![Example of a quartet set](https://github.com/P-Zande/quartets/blob/main/docs/_pages/kwartet1.jpg)

(see \autoref{fig:kwartet}, from \citet{Semmie}). The number of sets usually depends on the company that publishes the set. The game starts by giving each player 7 cards. The rest of the cards are made into the draw pile. Rules around who can start depend per household, sometimes the youngest player can start, sometimes the player left of the dealer. Each round is the same, which will be explained in the example below:

For our example we have three players: Alice, Bob, and Charlie.
It's Alice's turn, and she asks another player, in this case Bob, for a card by saying out loud: "Bob, do you have the card 'Blij' of the set 'Gevoelens'?" (See \autoref{fig:kwartet}). All players hear this statement. Alice is only allowed to ask Bob for a card from a certain set if she is in possession of at least one of the other cards of this set. Now two scenarios can happen:
* Bob is in possession of the ``Blij" card, and has to give it to Alice. Alice can now ask another question to either Bob or another player (Charlie).
* Bob does not have the ``Blij" card. Now Alice has to draw a card from the draw pile and Bob (the person Alice asked the question to) can now start his turn.

When a player has completed a set, they place this set on the table in front of them. This indicates to all players which sets have been completed and how many completed sets each player has. When all sets of cards have been placed on the table, i.e. when no player holds any cards in their hands anymore and the draw pile is empty, the game is finished. The player with the most complete sets wins the game.

A key difference between this game and the game `Go Fish' is that, in this game, the player requests a specific card from a set, whereas in Go Fish, the player requests any and all cards from a specific set. This also has consequences for what knowledge can be deduced from the questions and answers. Players are allowed to ask others for cards they already have, in an effort to confuse others or to avoid others having knowledge about them.

## Project goal