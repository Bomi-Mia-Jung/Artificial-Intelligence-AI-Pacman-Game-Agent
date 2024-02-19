# Artificial-Intelligence-AI-Pacman-Game-Agent
![image](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/9e7ad900-d314-47c9-ac7b-da4b15bdf206)

This repo contains my journey of implementing and training Artificially Intelligent Pacman Game Agents using Python!

This project implements and extends the AI Pacman Project developed by U.C. Berkely. (Attribution to their website here: [http://ai.berkeley.edu](http://ai.berkeley.edu/project_overview.html).) 

Due to the fact that they asks those who use and extend their project to not publish solutions/implementations to their pacman projects, I only uploaded the source code as well as video clips of my implemented and trained AI agents in action in this repo.

As you walk through this, please wait for GIFs to load!

## Project 1: Intelligent Path Search Algorithms
Starting out with basic search algorithms such as BFS (breadth-first search), DFS (depth-first search), and UCS (uniform cost search), 
I ultimately built up to implementing an intelligent search algorithm, A* (A-Star), and designed a non-trivial and consistent heuristic 
(one that combines multiple heuristics appropriately) to incorporate domain knowledge into the Pacman Agent's 
path-finding search through the maze to collect food pellets and power capsules.

Watch the gifs below to watch my intelligent search Pacman agent in action! 
(GIFs may take some time to show up on your screen if connection is slow)

Pacman using A* search to find best path to food pellets in the outer corners of the maze:
![A_Star_Corners_Heuristic](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/c05880b8-9851-4497-96e8-ced7551edad8)
<br />

Pacman using A* search to navigate a big, complex maze towards a food pellet far away:
![A_Star_Food_Search](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/ef415cd7-6f0f-4c83-b020-9ea7aee7e0a9)
<br />

## Project 2: Intelligent Adversarial Gameplay Agents
With path-finding algorithms implemented, the next step was to make my Pacman an actual gameplay agent, placed against enemy ghosts! For this project, I started out with a basic reflex agent implementation with a simple evaluation function, then continued building and creating an adversarial search pacman agent using minimax, alpha-beta pruning, then finally expectimax. I also tried my hand at improving the function to lead to a more efficient and effective decision-making as pacman tried to navigate the map, collect food pellets, all while avoiding game states in which it could run into a ghost and die.

First is my Pacman reflex agent, who performed well on both this tiny test map and this decently sized medium map. Although he performed well in these test maps, it must be noted that he's making decisions solely based on the current percept / input from the environment. 

![reflextAgentGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/548708c4-9e39-426c-992d-ed7e87922804)
(python pacman.py -p ReflexAgent -l testClassic)

Here is a slightly more sophisticated decision-making pacman, who considers not only the current state, but also future possible states and the strategies of his ghost opponents. 

Here's my first adversarial Pacman agent, implemented with Minimax.

![minimaxGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/d6519a2b-56b3-4b70-b633-bc072772bfeb)
(python pacman.py -p MinimaxAgent -a depth=3 -l smallClassic)

This first version of adversarial Pacman is not great- his thinking process  is very slow, and the way he evaluates game states aren't great (he's not interested in food- he just wants to avoid ending up near his adversaries for now). But not to worry- I keep improving him as I go!

Next is my implementation of a MinimaxAgent WITH alpha-beta pruning:

![AlphaBetaGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/99a349f8-e8a1-4675-b6eb-fa457a2175e3)
(python pacman.py -p AlphaBetaAgent -a depth=3 -l smallClassic)

This Pacman is faster to think and ends up with a slightly better score. 

Note that the ghosts I'm putting Pacman up against are moving in with a certain degree of randomness, but the minimax algorithm assumes optimal behavior of opponents. Using the Expectimax adversarial gameplay algorithm, we can make Pacman perform better in such uncertain environments where chance is involved. Here is my final food-chomping, ghost-busting pacman with expectimax, combined with a better evaluation function!

![ExpectimaxGameplay](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/c4ca55f5-723b-4d7c-abd7-a63a50cbf6ef)
(python pacman.py -p ExpectimaxAgent -a depth=3 -l smallClassic --frameTime=0.05 (using betterEvaluationFunction))

## Project 3: Even More Intelligent Agents, with Reinforement Learning
(readme work in progress: MDPs, Value Iteration, Optimal Policies, Q-Values/Q-Learning)

## Final Project: Capture-The-Flag Pacman
(flim + upload gifs)
