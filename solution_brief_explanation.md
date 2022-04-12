I choose Othello as a two-player turn-based game.

Adversarial games:
• win of one player is a loss of the other - agents have conflicting goals.
Objectives:

Player 1: maximize the outcome

Player 2: minimize the outcome

Game Problem Formulation:
A game with two players (MAX and MIN, MAX move first, turn-taking) can be defined as a search problem with:
1. initial state: board position
2. player: player to move
3. successor function: a list of legal (move, state) pairs
4. goal test: whether the game is over – terminal states
5. utility function: gives a numeric value for the terminal states (win, loss, draw)

Othello is a deterministic, turn-taking, 2-player, zero-sum game.
- Zero-sum describes a situation in which a participant's gain or loss is exactly balanced by the losses or gains of the other participant(s)

The Othello game is an adversarial search problem with the definition of adversarial games and their formulation.

I implemented move generators and evaluation functions in the `othello.py` file.

Game playing agent based on the alpha-beta search is implemented in the `agent.py` file.

Alpha-beta pruning 

Idea: Some branches will never be played by rational players since they include sub-optimal decisions (for either player)

Definitions of α and β

α = the value of the best (highest-value) choice we have found so far at any choice point along the path for MAX 

 β = the value of the best (lowest-value) choice we have found so far at any choice point along the path for MIN 

α-β search updates the values of α and β as it goes along and prunes the remaining branches at a node as soon 
as the value of the current node is worse than the current α or β for MAX or MIN, respectively.

Increasing the search depth:

When the search depth increases, the number of nodes visited by the algorithm increases, and the algorithm grows exponentially.

Improving move ordering:

The heuristic value for each state child is calculated before reordering the nodes and recursively checking them.

Improving the evaluation function:

The improvement in the evaluation function's performance helps reduce the number of steps to reach the goal.

All these improvements help in finding an efficient solution to reach the goal. They reduce the difficulty level by using perfect move ordering.

I also implemented depth parameter(range of 5-20), two forms of evaluation function(simple and advanced),
and the move ordering parameter set to true in the GUI.
