# Exploring communication in multi-agent reinforcement learning #
Two *tabula rasa* RL agents are tasked with playing a cooperative card game (inspired by [The Mind](https://boardgamegeek.com/boardgame/244992/mind)). The agents are dealt *n* cards from a deck ranging 1-*d*. At every timestep, the agents can play one of the cards in their hand or do nothing. The objective is to play all cards in ascending order. The game is considered lost if an agent plays a card that is higher than at least one card in the collective set of all players’ hands at the subsequent timestep (gameplay examples included for clarification).
<img src="https://raw.githubusercontent.com/nitrus96/RL_TheMind/master/game_examples.png" width="800">

# Algorithm #
The algorithm employed is a DQN with an integrated recurrent layer approximating observation history. At its core, this layer serves the same function as an experience replay buffer.

# Communication channel #
With every action taken, an agent can emit a message intended for their teammate. The message cannot directly reveal the agent’s hidden state (its hand) but should instead be viewed as a sort of clue. By learning to interpret clues, the agents are in a position to become more knowledgeable about the global state of the environment and refine their playing tactics accordingly.

The messages exchanged take form of a real-valued *M*-dimensional vector where *M* is a parameter regulating message length.

# Results #
The plots for 2,3,4-hand environments show that the agents leveraging communication tend to outperform their baseline counterparts.

### Two-card hand ###
<img src="https://raw.githubusercontent.com/nitrus96/RL_TheMind/master/2cards.png" width="450" height="450"/>

### Three-card hand ###
<img src="https://raw.githubusercontent.com/nitrus96/RL_TheMind/master/3cards.png" width="450" height="450"/>

### Four-card hand ###
<img src="https://raw.githubusercontent.com/nitrus96/RL_TheMind/master/4cards.png" width="450" height="450"/>

[**More about the project**](http://uu.diva-portal.org/smash/record.jsf?pid=diva2%3A1436997&dswid=2715 "Project")
