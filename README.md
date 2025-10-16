## CI2025 — Lab 1: Knapsack with Simulated Annealing

### Why Simulated Annealing (very short)
- The 0/1 knapsack is NP-hard. Exact methods may become expensive on large instances or when extra constraints/variants are added.
- Simulated Annealing (SA) can escape local optima by occasionally accepting worse moves with a temperature-controlled probability, often reaching high-quality solutions within a reasonable time.
- It is simple to implement, flexible (easy to add penalties/constraints), and only needs an objective function and a neighborhood.

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



