# Maintenance_Analytics
# Maintenance Analytics: What Do Unplanned Breakdowns Cost a Plant?

This is a personal project I built to practise SQL and Tableau on a realistic business problem.

**The scenario:** I'm a data analyst in a manufacturing plant. The plant manager says unplanned breakdowns are costing us production time, and wants to know the failure cost and what we can do about it.

## The data

I used the AI4I 2020 Predictive Maintenance dataset from the UCI Machine Learning Repository. It has 10,000 records. Each one has the product type, air and process temperature, rotational speed, torque, tool wear, whether the machine failed, and which of five failure modes happened (TWF, HDF, PWF, OSF, RNF).

Source: https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset

## Tools

- MySQL for the analysis
- Tableau for the dashboard

## The business problems

**Problem 1: How big is the failure problem?**
Out of everything we produce, how often do machines fail, and does the product quality type make a difference?

**Problem 2: Which failure type happens the most?**
This tells us where the maintenance budget should go first.

**Problem 3: Does tool wear drive breakdowns?**
Do machines with more tool wear develop faults more quickly?

**Problem 4: What operating conditions are risky?**
How do temperature, speed and torque compare for machines that failed and machines that did not?


## What I found

## What I found

- The overall failure rate is 3.39% (339 failures out of 10,000 records).
- Product type L (low quality) fails the most, at about 3.9%, compared with about 2.8% for M and about 2.1% for H.
- The most common failure mode is heat dissipation failure (HDF), which makes up 33.9% of failures, followed by overstrain (OSF) at 28.9% and power failure (PWF) at 28.0%.
- Failed machines had an average tool wear of X minutes, compared with X minutes for machines that did not fail.
- Failed machines ran at an average torque of X Nm, compared with X Nm for machines that did not fail.


## Recommendations

Based on what the data showed, this is what I would tell the plant manager:

1. **Replace tools before they wear out.** Failures rise sharply once tool wear reaches about 200 minutes, so tools should be changed at that point instead of waiting for them to break.
2. **Put the maintenance budget on heat dissipation failures (HDF) first.** It is the most common failure mode and accounts for 33.9% of all failures.
3. **Pay extra attention to product type L.** It has the highest failure rate (about 3.9%), so its machines should be inspected more often.
4. **Watch torque together with tool wear.** Overstrain failures happen when tool wear multiplied by torque goes past a set limit, so operators should get a warning when a worn tool is running at high torque.
5. **Start recording real costs.** The dataset has no cost data, so my cost estimate is based on assumptions. Tracking actual downtime and repair costs would make the estimate more accurate.
