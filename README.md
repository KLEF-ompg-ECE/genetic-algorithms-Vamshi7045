# Assignment 2 — Genetic Algorithm: Knapsack Problem

## Observation Report

Student Name  : Ellitam Vamshi  
Student ID    : 2310040098  
Date Submitted: 25 March 2026  

---

## Before You Begin — Read the Code

Q1. What does the `fitness()` function return? Why does an overweight solution score 0?

The fitness() function returns the total value of selected items. If the total weight exceeds the maximum allowed weight, it returns 0 to penalize invalid solutions.

---

Q2. What does `tournament_select()` do? Why are higher-fitness individuals more likely to be chosen?

tournament_select() randomly selects a small group of individuals and returns the one with the highest fitness. Higher-fitness individuals are more likely to be chosen because they have a better chance of winning the selection process.

---

Q3. Look at the `run_ga()` loop. What does this line do? Why is it important?

next_gen = [best_chromosome[:]]

This line copies the best chromosome into the next generation. It ensures that the best solution is preserved and not lost during crossover or mutation.

---

## Experiment 1 — Baseline Run

| Metric | Your result |
|--------|-------------|
| Number of generations | 50 |
| Best value at generation 1 | 60 |
| Final best value | 77 |
| Total weight of best solution (kg) | 14.4 |
| Is solution valid (Yes / No) | Yes |

Copy the printed packing list here:

Best Packing List
--------------------------------------
+ Water bottle
+ First aid kit
+ Sleeping bag
+ Torch
+ Energy bars (x6)
+ Rain jacket
+ Map & compass
+ Cooking stove
+ Rope (10 m)
+ Sunscreen
+ Power bank

---

Look at plots/experiment_1.png and describe what you see.

The value increases rapidly in the early generations, showing quick improvement. After some generations, the curve becomes flat, indicating convergence and minimal improvement.

---

## Experiment 2 — Effect of Mutation Rate

| mutation_rate | Final best value | Weight (kg) | Valid? | Shape of curve |
|--------------|-----------------|-------------|--------|----------------|
| 0.01 | 75 | 14.9 | Yes | Rapid rise then early plateau |
| 0.05 | 77 | 14.4 | Yes | Smooth rise then stable convergence |
| 0.30 | 78 | 14.1 | Yes | Fluctuating then sharp improvement |

---

Compare the three plots. What happens when mutation is too low? Too high?

When mutation is too low, the algorithm loses diversity and gets stuck early. When mutation is too high, the search becomes random and unstable. A moderate mutation rate provides a balance between exploration and exploitation.

---

Which mutation_rate gave the best result? Why do you think that is?

The mutation_rate 0.30 gave the best result because it increased exploration and helped escape local optima.

---

## Summary

| Experiment | Key setting | Final value | Main finding in one sentence |
|------------|-------------|-------------|------------------------------|
| 1 — Baseline | mutation_rate = 0.05 | 77 | The algorithm converges quickly and stabilizes |
| 2 — Mutation rate | mutation_rate = 0.30 | 78 | Higher mutation improves exploration and finds better solutions |

---

## Reflection

Mutation rate is an important parameter in Genetic Algorithms. Low mutation reduces diversity and causes early convergence. Moderate mutation gives stable performance. High mutation increases exploration but may reduce stability.

---

## Submission Checklist

- [x] Student name and ID filled
- [x] Q1, Q2, Q3 answered
- [x] Experiment 1 completed
- [x] Experiment 2 completed
- [x] Summary completed
- [x] plots/ contains all required images