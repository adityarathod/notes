# Probabilistic Analysis and Randomized Algorithms
#lecture #cs4349 

## The Hiring Problem
You need to hire a new office assistant, so you hire an employment agency, which sends you one candidate per day (for a small fee). You must determine if you want to hire that person or not immediately after the interview. Note that it costs a lot to hire a candidate, since you must fire the existing person and hire the new one. You're willing to pay the price, but how much would the expected cost be?

Here is the code for an algorithm that hires the best assistant seen so far after interviewing the $n^{th}$ candidate:

```
HireAssistant(n)
best = 0 # a dummy candidate
for i = 1 to n
  interview candidate i
  if candidate i is better than best
    fire best
    best = i
    hire candidate i
```

## Probabilistic analysis
