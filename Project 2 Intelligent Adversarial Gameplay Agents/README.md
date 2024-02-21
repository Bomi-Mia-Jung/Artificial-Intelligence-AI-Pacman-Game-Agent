
## Project 2: Intelligent Adversarial Gameplay Agents
With path-finding algorithms implemented, the next step was to make my Pacman an actual **gameplay** agent, placed against enemy ghosts! 

For this project, I started out with a basic reflex agent implementation with a simple evaluation function.

Then, I continued building up a better & better adversarial search Pacman agent, using Minimax, Minimax WITH Alpha-Beta pruning, and finally, Expectimax. I also tried improving the evaluation function to lead to more efficient & effective decision-making. 

From here, you'll watch my Pacman get better & better at navigating the map and collecting food pellets while avoiding ghosts.

First is my Pacman reflex agent, who performed well on both a tiny test map and a decently-sized medium map. 

![ReflexAgentPacman](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/0981131c-9ff7-4365-89b8-3012dd74c5a1)
<!-- python pacman.py -p ReflexAgent -l testClassic -->

Although he performed well in these test maps, it must be noted that he's making decisions solely based on the current percepts/input from the game environment. 

Here is a slightly more sophisticated decision-making Pacman, who considers not only the current game state, but also future possible states and the strategies of his ghost opponents. 

Here's my first forward-looking adversarial Pacman agent, implemented with Minimax. This first version of adversarial Pacman is not great. Pacman is slow to think, and the way he evaluates the game states isn't great (he's not very interested in food- he just wants to avoid his adversaries). But not to worry- I keep improving him as I go!

![MinimaxPacman](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/9ed0ba58-5112-47f5-82e3-149d457bc07e)
<!-- python pacman.py -p MinimaxAgent -a depth=3 -l smallClassic) -->

Next is my implementation of a MinimaxAgent WITH alpha-beta pruning. This Pacman is faster to think, and ends up with a slightly better score, but we could be doing better.
![AlphaBetaPacman](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/6096784d-93d4-4d4e-aa12-e2f1664df55b)
<!-- python pacman.py -p AlphaBetaAgent -a depth=3 -l smallClassic -->

The problem is that the minimax algorithm assumes **optimal** behavior of opponents, but the ghosts I'm putting Pacman against are moving in with a certain degree of randomness. 

We can make Pacman perform better in uncertain environments involving chance by using the Expectimax algorithm. Here is my **final food-chomping, ghost-busting Pacman** with Expectimax, combined with a better evaluation function:

![ExpectimaxPacman](https://github.com/Bomi-Mia-Jung/Artificial-Intelligence-AI-Pacman-Game-Agent/assets/77511489/3540867b-82a8-4ff1-b99f-f35f1fbc7c81)
<!-- python pacman.py -p ExpectimaxAgent -a depth=3 -l smallClassic --frameTime=0.05 (using betterEvaluationFunction) -->
