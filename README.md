two possible solutions to the Multi-Dimensional Multi-Knapsack Problem 

1. Simulated Annealing: 
It explores the solution space by randomly adding/removing items between knapsacks, sometimes accepting worse solutions to escape local optima

   - Acceptance: Always accepts improvements; accepts worse moves with probability exp(Δvalue / T)
   - Temperature decreases gradually (T *= alpha)

1. Tabu Search:
Local search using short-term memory to avoid cycling

   - Moves: as for previous solution, move or remove an item from a knapsack
   - Tabu List: Stores recent moves to prevent revisiting them
   - Dynamic Tabu Adjustment (I found this idea online): Tabu tenure is increased when search is active and decreased when stagnating (maybe too many moves are forbidden, so it might be better to reduce the queue)
   - Restart mechanism: After some moves without improvement, the algorithm can restart from a new random solution