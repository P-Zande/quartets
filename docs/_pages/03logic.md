---
title: Logic 
author: Perry van der Zande
date: 2023-06-20
category: Jekyll
layout: page
permalink: /logic
---

## Quartets & LAMAS
Quartets seems like an easy game, however, if you look at the logic behind all of it, it becomes clear there is quite some involved. 

First of all, because everyone asks others about cards in a shared space, all announcements are made publicly. In the example before where Alice asked Bob about the 'Blij' card, Alice, Bob and any other players heard Alice ask this. 

Higher-order knowledge comes into play when players start to think about what cards other players have in possession. Both Bob and Charlie know that, because Alice asked for a card in the 'Gevoelens' set, she must have at least one card of that set in her hand. Alice also knows that Bob and Charlie know that she has a card in that set, and both Bob and Charlie know that Alice knows that they know that she has a card of the 'Gevoelens' set, etc.
It is therefore also common knowledge that the player who asked for a specific card is in possession of a card from that set. 

For now, our research question will be if there is a downside to asking for a card you want to receive. This could be because others now know you already have at least one card of that set. 

## Logic
For this project we used Public Announcement logic. There is no private communication between agents. Thus, when an agent asks another agent for a card, all agents hear this and it can thus be modelled as a public announcement. Similarly, when an agent states it does not have a certain card, or when it states it does have a card and the card is given to the asking agent, public announcements are made.
After each announcement, all agents update their knowledge base to what they now know. 

We can use the following to describe the kinds of knowledge that an agent can have:

* The statement that agent 1 knows that agent 2 has card A from set X can be described as K<sub>1</sub> H<sub>2</sub>X<sub>A</sub>, where the formula H<sub>i</sub> &phi; operator indicates that agent 2 has object &phi;.
* The statement that agent 1 knows that card A from set X is owned by either agent 2 or agent 3 can be described as K<sub>1</sub> (H<sub>2</sub>X<sub>A</sub> ∨ H<sub>3</sub>X<sub>A</sub>) ∧ K<sub>1</sub> &not; (H<sub>2</sub>X<sub>A</sub> &and; H<sub>3</sub>X<sub>A</sub>)
* The statement that agent 1 knows that agent 2 has at least one of the cards A, B, C of set X can be described as K<sub>1</sub> (H<sub>2</sub>X<sub>A</sub> ∨ H<sub>2</sub>X<sub>B</sub> ∨ H<sub>2</sub>X<sub>C</sub>), or alternatively K<sub>1</sub> H<sub>2</sub>(X<sub>A</sub> ∨ X<sub>B</sub> ∨ X<sub>C</sub>).

The three public announcements made during the game of Quartets can be formalized as follows:

* "Agent 1 asks agent 2 for card A of set X" contains two statements: &not; H<sub>1</sub> X<sub>A</sub> and H<sub>1</sub>(X<sub>A</sub> &or; X<sub>B</sub> &or; X<sub>C</sub> &or; X<sub>D</sub>). These statements correspond to the simplification that an agent cannot ask for a card it already has, and to the rule that an agent can only ask for cards if it owns at least one of the cards of the corresponding set, respectively.
* "Agent 2 does not have card A of set X" contains the statement &not; H<sub>2</sub> X<sub>A</sub>.
* "Agent 2 has card A of set X and gives it to agent 1" contains the statement H<sub>2</sub>X<sub>A</sub> and the *change* H<sub>3</sub>X<sub>A</sub>. This will be explained further in the section Model.


