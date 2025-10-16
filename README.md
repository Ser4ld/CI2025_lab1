## CI2025 — Lab 1: Knapsack with Simulated Annealing

### Algorithm sketch
1. Start from a feasible solution (random or greedy).
2. Propose a neighbor (e.g., flip one item; repair or reject if the capacity is violated).
3. Acceptance: always accept improvements; accept worsenings with probability p = exp(−Δ/T).
4. Cooling: reduce temperature T until a stop condition is met.

### Key functions

`update_solution`: Perform a random modification to the current solution (add/remove/swap items between knapsacks)

`fit`: Compute the value of the solution. Returns -100 if the solution is infeasible.

`is_feasible`: Check whether the solution satisfies the problem constraints (no duplicate items and weights below the limit)

`to_feasible`: Iteratively modify the solution until it becomes feasible

`simulated_annealing_solver`: Simulated Annealing algorithm for searching the optimal solution

### Collaborators
- Stefano Paoloni (346297)
- Michelangelo Marconi (342709)



