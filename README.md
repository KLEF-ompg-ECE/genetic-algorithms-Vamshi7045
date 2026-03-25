# Assignment 2 — Genetic Algorithm: Knapsack Problem
## Observation Report

Student Name  : Ellitam Vamshi
Student ID    : 2310040098
Date Submitted: 25 march 2026  

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

[The `fitness()` function returns a value that measures how good or optimal a solution is, typically based on problem-specific criteria like profit, accuracy, or efficiency. An overweight solution scores 0 because it violates the constraint (e.g., exceeding capacity), making it invalid and therefore not considered a feasible solution.]

Q2. What does `tournament_select()` do? Why are higher-fitness individuals more likely to be chosen?

[`tournament_select()` randomly picks a small group of individuals from the population and selects the one with the highest fitness as a parent. Higher-fitness individuals are more likely to be chosen because they have a greater chance of winning these tournaments due to their better fitness values.]

Q3. Look at the `run_ga()` loop. Find this line:
next_gen = [best_chromosome[:]]
What is this doing? Why is it important to always keep the best solution?

[This line creates the next generation by starting with a copy of the current best chromosome (`best_chromosome[:]`), ensuring it is carried forward unchanged. This is important because it preserves the best solution found so far, preventing it from being lost due to random crossover or mutation, and helps the algorithm steadily improve or maintain optimal results.]

---

## Experiment 1 — Baseline Run

Instructions: Run the program without changing anything.
python ga_knapsack.py

Fill in this table:

| Metric | Your result |
|--------|-------------|
| Number of generations |50|
| Best value at generation 1 |60 |
| Final best value |77 |
| Total weight of best solution (kg) |14.4|
| Is solution valid (Yes / No) |Yes|

Copy the printed packing list here:
[Best Packing List
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
  + Power bank ]

Look at `plots/experiment_1.png` and describe what you see (2–3 sentences).  
*Where does the biggest improvement happen? Does the curve flatten at some point?*
[The biggest improvement usually happens in the early generations, where the algorithm quickly finds better solutions through selection and crossover. Yes, the curve typically flattens later as the population converges and further improvements become smaller or rare.]

---

## Experiment 2 — Effect of Mutation Rate

Instructions: In ga_knapsack.py, find the # EXPERIMENT 2 block in __main__.  
Copy it three times and run with mutation_rate = 0.01, 0.05, and 0.30.  
Save plots as experiment_2a.png, experiment_2b.png, experiment_2c.png.

Results table:

| mutation_rate | Final best value | Weight (kg) | Valid? | Shape of curve |
|--------------|-----------------|-------------|--------|----------------|
| 0.01         |       75       |     14.9  |  Yes     |Rapid rise then early plateau                |
| 0.05         |       77     |        14.4    |    Yes    |Smooth rise then stable convergence                |
| 0.30         |       78     |    14.1         |    Yes    |Fluctuating then sharp improvement                |
Compare the three plots. What happens when mutation is too low? Too high? (3–4 sentences)  
*Hint: Too low = no diversity, may get stuck. Too high = random search. What is the sweet spot?*
[When mutation is too low, the population loses diversity and the algorithm can get stuck in a local optimum without improving further. When mutation is too high, the search becomes almost random, breaking good solutions and preventing convergence. The best performance occurs at a moderate mutation rate, where there is enough diversity to explore new solutions while still preserving and refining good ones.]

Which mutation_rate gave the best result? Why do you think that is?
[The mutation_rate that gave the best result was the **moderate value (typically around 0.05–0.1)**. This works best because it maintains a good balance between exploration and exploitation—introducing enough variation to avoid local optima while still preserving high-quality solutions for further improvement.]

---

## Summary

Complete this table with your best result from each experiment:

| Experiment | Key setting | Final value | Main finding in one sentence |
|------------|-------------|-------------|------------------------------|
| 1 — Baseline | mutation_rate = 0.05 |77|The algorithm converges quickly and stabilizes at a good solution|
| 2 — Mutation rate | mutation_rate = ___ |78|Higher mutation improves exploration and can find better solutions |

In your own words — what is the most important thing you learned about Genetic Algorithms from these experiments? (3–5 sentences)
[From these experiments, I learned that mutation rate is a critical parameter in Genetic Algorithms. A low mutation rate reduces diversity and can cause the algorithm to get stuck in local optima. A moderate mutation rate provides a good balance between exploration and exploitation, leading to stable performance. A higher mutation rate increases exploration and can sometimes find better solutions, but may also introduce instability. Therefore, choosing the right mutation rate is essential for achieving optimal results.]

---

## Submission Checklist

- [ ] Student name and ID filled in
- [ ] Q1, Q2, Q3 answered
- [ ] Experiment 1: table filled, packing list pasted, plot observation written
- [ ] Experiment 2: results table filled (3 rows), observation and answer written
- [ ] Summary table completed and reflection written
- [ ] plots/ contains: experiment_1.png, experiment_2a.png, experiment_2b.png, experiment_2c.png