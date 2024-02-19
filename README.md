# Artificial-Intelligence-AI-Pacman-Game-Agent
![image](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/9e7ad900-d314-47c9-ac7b-da4b15bdf206)

This repo contains my journey of implementing and training Artificially Intelligent Pacman Game Agents using Python!

This project implements and extends the AI Pacman Project developed by U.C. Berkely. (Attribution to their website here: [http://ai.berkeley.edu](http://ai.berkeley.edu/project_overview.html).) 

Due to the fact that they asks those who use and extend their project to not publish solutions/implementations to their pacman projects, I only uploaded the source code as well as video clips of my implemented and trained AI agents in action in this repo.

## Project 1: Intelligent Path Search Algorithms
Starting out with basic search algorithms such as BFS (breadth-first search), DFS (depth-first search), and UCS (uniform cost search), 
I ultimately built up to implementing an intelligent search algorithm, A* (A-Star), and designed a non-trivial and consistent heuristic 
(one that combines multiple heuristics appropriately) to incorporate domain knowledge into the Pacman Agent's 
path-finding search through the maze to collect food pellets and power capsules.

Play the videos below to watch my intelligent search Pacman agent in action!

https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/87403b71-105e-41a5-a2fe-cfd5fb3ee1c4

https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/97442973-495b-4aa1-9c6c-e4cbaac86195

## Project 2: Intelligent Adversarial Gameplay Agents
With path-finding algorithms implemented, the next step was to make my Pacman an actual gameplay agent, placed against enemy ghosts! For this project, I started out with a basic reflex agent implementation with a simple evaluation function, then continued building and creating an adversarial search pacman agent using minimax, alpha-beta pruning, then finally expectimax. I also tried my hand at improving the function to lead to a more efficient and effective decision-making as pacman tried to navigate the map, collect food pellets, all while avoiding game states in which it could run into a ghost and die.

First is my Pacman reflex agent, who performed well on both this tiny test map and this decently sized medium map. Although he performed well in these test maps, it must be noted that he's making decisions solely based on the current percept / input from the environment. 

![reflextAgentGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/548708c4-9e39-426c-992d-ed7e87922804)
(python pacman.py -p ReflexAgent -l testClassic)

Here is a slightly more sophisticated decision-making pacman, who considers not only the current state, but also future possible states and the strategies of his ghost opponents. The following shows my adversarial Pacman with minimax- note that he isn't too great at gameplay against ghosts just yet, and he ends up dying. But don't worry- we'll make him better as we go. Here's my first adversarial Pacman agent, whose thinking process is very slow and whose gamestate evaluation methods aren't great (he's not interested in food- he just wants to avoid his adversaries for now):

![minimaxGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/d6519a2b-56b3-4b70-b633-bc072772bfeb)
(python pacman.py -p MinimaxAgent -a depth=3 -l smallClassic)

Next is my implementation of a MinimaxAgent WITH alpha-beta pruning:

![AlphaBetaGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/99a349f8-e8a1-4675-b6eb-fa457a2175e3)
(python pacman.py -p AlphaBetaAgent -a depth=3 -l smallClassic)

Pacman is faster to think and ends up with a slightly better score- but we'll try to make him even better. 

The ghosts I'm putting him up against move in with a certain degree of randomness, but minimax assumes optimal behavior of opponents. Using the Expectimax adversarial gameplay algorithm, we can make Pacman perform better in such uncertain environments where chance is involved. Here is my final food-chomping, ghost-busting pacman with expectimax, combined with a better evaluation function!

![ExpectimaxGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/c4ca55f5-723b-4d7c-abd7-a63a50cbf6ef)
(python pacman.py -p ExpectimaxAgent -a depth=3 -l smallClassic --frameTime=0.05 (using betterEvaluationFunction))

## Project 3: Even More Intelligent Agents, with Reinforement Learning

## Final Project: Capture-The-Flag Pacman
