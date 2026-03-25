# Assignment 2 — Genetic Algorithm: Knapsack Problem

## Observation Report

**Student Name**  : Ellitam Vamshi
**Student ID**    : 2310040098
**Date Submitted**: 25 March 2026

---

## Before You Begin — Read the Code

### Q1. What does the `fitness()` function return? Why does an overweight solution score 0?

The `fitness()` function returns the **total value of selected items** in the knapsack.
If the total weight exceeds the maximum allowed weight (15 kg), the function returns 0.
This ensures that invalid (overweight) solutions are penalized and not selected in the algorithm.

---

### Q2. What does `tournament_select()` do? Why are higher-fitness individuals more likely to be chosen?

`tournament_select()` randomly selects a small group of individuals and chooses the one with the highest fitness.
Higher-fitness individuals are more likely to be chosen because they have a greater chance of winning the tournament due to their better fitness values.

---

### Q3. What does this line do? Why is it important?

`next_gen = [best_chromosome[:]]`

This line copies the best chromosome into the next generation (elitism).
It ensures that the best solution found so far is preserved and not lost due to crossover or mutation, helping the algorithm converge reliably.

---

## Experiment 1 — Baseline Run

| Metric                             | Your result |
| ---------------------------------- | ----------- |
| Number of generations              | 50          |
| Best value at generation 1         | 60          |
| Final best value                   | 77          |
| Total weight of best solution (kg) | 14.4        |
| Is solution valid                  | Yes         |

### Best Packing List

* Water bottle
* First aid kit
* Sleeping bag
* Torch
* Energy bars (x6)
* Rain jacket
* Map & compass
* Cooking stove
* Rope (10 m)
* Sunscreen
* Power bank

---

### Plot Observation

The graph shows a rapid increase in value during the initial generations, indicating fast improvement.
After a few generations, the curve flattens, showing that the algorithm converges and further improvements become minimal.

---

## Experiment 2 — Effect of Mutation Rate

| mutation_rate | Final best value | Weight (kg) | Valid? | Shape of curve                      |
| ------------- | ---------------- | ----------- | ------ | ----------------------------------- |
| 0.01          | 75               | 14.9        | Yes    | Rapid rise then early plateau       |
| 0.05          | 77               | 14.4        | Yes    | Smooth rise then stable convergence |
| 0.30          | 78               | 14.1        | Yes    | Fluctuating then sharp improvement  |

---

### Analysis

When mutation rate is too low (0.01), the population lacks diversity and the algorithm gets stuck early.
When mutation rate is too high (0.30), the search becomes unstable and behaves more randomly.
A moderate mutation rate (0.05) provides a balance between exploration and exploitation, leading to stable convergence.

---

### Best Mutation Rate

The mutation rate **0.30** gave the best result (value = 78).
This is because the higher mutation increased exploration and helped escape local optima, allowing the algorithm to find a better solution.

---

## Summary

| Experiment    | Key setting          | Final value | Main finding                                                    |
| ------------- | -------------------- | ----------- | --------------------------------------------------------------- |
| Baseline      | mutation_rate = 0.05 | 77          | Converges quickly to a stable solution                          |
| Mutation rate | mutation_rate = 0.30 | 78          | Higher mutation improves exploration and finds better solutions |

---

## Reflection

From these experiments, I learned that mutation rate is a critical parameter in Genetic Algorithms.
Low mutation reduces diversity and may cause premature convergence.
Moderate mutation provides stable and reliable performance.
Higher mutation increases exploration and can find better solutions, but may also introduce instability.
Thus, choosing the right mutation rate is essential for achieving optimal results.

---

## Submission Checklist

- [x] Student name and ID filled
- [x] Q1, Q2, Q3 answered
- [x] Experiment 1 completed
- [x] Experiment 2 completed
- [x] Summary completed
- [x] plots/ contains all required images
