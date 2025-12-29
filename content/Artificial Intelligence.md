## Decision Tree
*It is used for decision making in classification.*

The **root node** is the most significant node of the decision tree. The **entropy** is calculated which is the amount of uncertainty in the probability.

**Entropy** is calculated using this formula where $P_n$ and $N_n$ are the number of yes and no respectively and $T_n$ is their sum.
$$
\begin{equation}
I(P_n, N_n) = -\frac{P_n}{T_n} \times \log_2(\frac{P_n}{T_n}) -\frac{N_n}{T_n} \times \log_2(\frac{N_n}{T_n})
\end{equation}
$$

1. We calculate the Entropy of the entire dataset.
2. Then we calculate the Entropy of each attribute in a column.
3. We then calculate the Information Gain of each column separately using this equation.

$$
Gain = I(Dataset) - \frac{T_n (attribute)}{T_n (dataset)} \times I(Attributes)
$$

4. The attribute with the highest Gain is made into the **root** node.

After which we repeat steps 1-4 based on the new root node. This way we get the next node as well.
## Bayes Theorem
*It is a theorem of conditional probability.*

$$
\begin{equation}
    P(A \ | \ B) = \frac{P(B \ | \ A) \times P(A)}{P(B)} 
\end{equation}
$$
It is used to calculate the probability of an event when another has already happened.
### Example
Suppose you have a two bags and each has some balls where one ball is taken out randomly from one of the bags.
`bag1` which has `Red = 2` and `Black = 3` 
`bag2` which has `Red = 3` and `Black = 4`

Now since there are two bags and each has the same chance of being chosen then:
$$
P(bag1) = P(bag2) = 1/2 = 50\%
$$
And the probabilities for picking a specific colored ball from each of these.
$$
\begin{align}
P(Red \ | \ bag1) = 2/5 \times 1/2 => 2/10 \\
P(Black \ | \ bag1) = 3/5 \times 1/2 => 3/10 \\
P(Red \ | \ bag2) = 3/7 \times 1/2 => 3/14 \\
P(Black \ | \ bag2) = 4/7 \times 1/2 => 4/14
\end{align}
$$
And the total probabilities for each type of balls.
$$
P(Red) = P(Red \ | \ bag1) + P(Red \ | \ bag2) = 2/10 + 3/14 => 41.4\%
$$
$$
P(Black) = P(Black \ | \ bag1) + P(Black \ | \ bag2) = 3/10 + 4/14 => 58.5\%
$$

This equation asks the question that if the ball that you got was a Red ball then what is the probability that it was from bag1.
$$ 
\begin{equation}
    P(bag1 \ | \ Red) = \frac{P(Red \ | \ bag1) \times P(bag1)}{P(Red)} 
\end{equation} 
$$
## Naive Bayes Classifier
*It is a supervised machine learning algorithm.*

It uses the Bayes Theorem and all of the variables used are independent.
The dataset is divided into two parts; **feature matrix** and **response vector**.
## Graph Traversal
There are two main approaches to traversing a graph.
### BFS (Breadth First Search)
It uses the queue data structure. It visits the first node and then recursively visits all the neighbours of that visited node.
### DFS (Depth First Search)
It uses the stack data structure. It the visits the first node and then recursively visits the next univisited vertex, if no unvisited vertex is found then it backtracks.

Both approaches have the same efficiency and can be implemented using **adjacency matrices** or **adjacency lists**.
## 8-Puzzle
*It is a single-player game played on a 3x3 grid where out of the 9 tiles, a single is empty. The main goal is reach the goal position by moving the empty tile around.*

8-Puzzles can be solved without heuristics or with heuristics. Theheuristics function used for it is the **Manhattan Priority Function**. 

The **Manhattan Distance** is the amount of moves required to get the tile in the correct place. At each step we calculate the manhattan distance of each tile and sum them up. We compare the summed up Manhattan Distance of each path and pick the one which is the least.
## KNN (K-Nearest Neighbours)
*It is a popular supervised machine learning algorithm for classification.*

A variable $k$ is chosen which refers to the **number of neighbours** to consider. 
A dataset is taken and then we calculate the **euclidean distance** between each datapoint and our unknown datapoint.

The ones with the **lowest value** are taken (if $k=1$; we take a single value while, if $k=3$; we take three values). Then a majority voting is done to find the prediction. 
## Recommender System
*It is an unsupervised machine learning algorithm.*

**Content-Based** -> Based on matching properties.
**Collaboration-Filtering** -> Based on the reviews by the people who have the same interests.
**Hybrid-System** -> Combines both Content-Based and Collaboration-Filtering.
### Cosine Similarity
It is the measure of similarity between two values; where 0 = no similarity and 1 = exactly same.
![[Pasted image 20240512212355.png]]
## Games with AI
*Aritificial Intelligence is used quite a lot inside of games.*

- **Minimax** Algorithms to find best possible moves in deterministic games like Chess and TicTacToe.
- **Pathfinding** Algorithms to find the shortest distance for A.I bots.
- **Suggestion** Algorithms for autofilling.
### Minimax Algorithm
*It is a specialized searching algorithm that finds the best possible moves in a given position of a game.*

It uses recursive or backtracking logic to make decisions. The time complexity and space complexity are both $O(b^m)$. where b -> branching factor and m -> maximum depth. It is a very slow algorithm because it checks every single route.

We generate a tree of all the possible outcomes and alternately find **min** and **max** values on each depth.
#### Alpha-Beta Pruning
A modified version of the minimax algorithm is the **alpha-beta pruning**, where it searches without going through every single node. Once we find the best path, we **prune** (cut-off) all the other paths.

We use two variables $\alpha, \beta$ to store the max and min values. The branches are cut-off using the property $\alpha>=\beta$.
#### Negamax Algorithm
It is another modified version of the minimax algorithm, which works because of the fact that two-player games have a zero-sum result, which means that one player's win is another's loss.

In this algorithm, we consider only the **max** value at each depth but we also make them negative.