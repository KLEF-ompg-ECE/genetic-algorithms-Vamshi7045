# Assignment 2 — Genetic Algorithm: Knapsack Problem
## Observation Report

Student Name  : Ellitam Vamshi
Student ID    : 2310040098
Date Submitted: 25 March 2026  

---

## How to Submit

1. Run each experiment following the instructions below
2. Fill in every answer box — do not leave placeholders
3. Make sure the plots/ folder contains all required images
4. Commit this README and the plots/ folder to your GitHub repo

---

## Before You Begin — Read the Code

Open ga_knapsack.py and read through it. Then answer these questions.

Q1. What does the `fitness()` function return? Why does an overweight solution score 0?

The fitness() function returns the total value of selected items. If the total weight exceeds MAX_WEIGHT, it returns 0 to penalize invalid solutions.

Q2. What does `tournament_select()` do? Why are higher-fitness individuals more likely to be chosen?

tournament_select() selects the best individual from a random group. Higher-fitness individuals are more likely to be chosen because they perform better.

Q3. Look at the `run_ga()` loop. Find this line:
next_gen = [best_chromosome[:]]
What is this doing? Why is it important to always keep the best solution?

This line copies the best chromosome into the next generation. It ensures the best solution is preserved.

---

## Experiment 1 — Baseline Run

Instructions: Run the program without changing anything.
python ga_knapsack.py

Fill in this table:

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

Look at `plots/experiment_1.png` and describe what you see (2–3 sentences).

The value increases rapidly in early generations. Later, the curve flattens showing convergence.

---

## Experiment 2 — Effect of Mutation Rate

Instructions: In ga_knapsack.py, find the # EXPERIMENT 2 block in __main__.  
Copy it three times and run with mutation_rate = 0.01, 0.05, and 0.30.  
Save plots as experiment_2a.png, experiment_2b.png, experiment_2c.png.

Results table:

| mutation_rate | Final best value | Weight (kg) | Valid? | Shape of curve |
|--------------|-----------------|-------------|--------|----------------|
| 0.01 | 75 | 14.9 | Yes | Rapid rise then early plateau |
| 0.05 | 77 | 14.4 | Yes | Smooth rise then stable convergence |
| 0.30 | 78 | 14.1 | Yes | Fluctuating then sharp improvement |

Compare the three plots. What happens when mutation is too low? Too high? (3–4 sentences)

When mutation is too low, the algorithm loses diversity and gets stuck. When mutation is too high, the search becomes random. A moderate mutation rate balances both.

Which mutation_rate gave the best result? Why do you think that is?

The mutation_rate 0.30 gave the best result because it increases exploration and avoids local optima.

---

## Summary

Complete this table with your best result from each experiment:

| Experiment | Key setting | Final value | Main finding in one sentence |
|------------|-------------|-------------|------------------------------|
| 1 — Baseline | mutation_rate = 0.05 | 77 | The algorithm converges quickly |
| 2 — Mutation rate | mutation_rate = 0.30 | 78 | Higher mutation improves exploration |

In your own words — what is the most important thing you learned about Genetic Algorithms from these experiments? (3–5 sentences)

Mutation rate is important in Genetic Algorithms. Low mutation causes early convergence. Moderate mutation gives stable results. High mutation increases exploration.

---

## Submission Checklist

- [x] Student name and ID filled in
- [x] Q1, Q2, Q3 answered
- [x] Experiment 1 completed
- [x] Experiment 2 completed
- [x] Summary completed
- [x] plots/ contains all required images
## Section C

Mutation rate is important in Genetic Algorithms. Low mutation causes early convergence. Moderate mutation gives stable results. High mutation increases exploration.