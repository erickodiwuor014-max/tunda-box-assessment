# Tunda Box – Junior Data Analyst Assessment

Candidate: Erick Odiwuor

Responses to the Power Learn Project Junior Data Analyst Assessment (fictional company, invented data).

## Contents
- solutions.ipynb: SQL and Python solutions for Parts 2 to 5, with outputs
- README.md: this file

## Full written responses
Google Doc with all answers (Parts 1 to 6): https://docs.google.com/document/d/1uXIQcK9ssdR-bMxwKwgP6j-i3fVkFhGRaR-AQovujb8/edit?usp=sharing

## How to run
Open solutions.ipynb in Google Colab (colab.research.google.com) and choose Runtime, then Run all. The notebook loads the sample tables into an in-memory SQLite database, so no other files are needed.

## Thought process
1. Audit before answering. The sample data has deliberate traps: a duplicate order (1006), inconsistent city spellings, a missing amount (1009), an extreme outlier (1013, KES 185,000), an orphan customer ID (999), and an order dated before its customer signed up (1003). Each one can change an answer, so I cleaned first and showed results with and without the outlier where it mattered.
2. State definitions. Revenue means completed orders only. A repeat buyer has 2 or more distinct completed orders. Assumptions are written next to every answer.
3. Be open about uncertainty. Where one suspicious record decides the answer, I report the cleaned result, flag the record, and say what changes if it is real.
4. Statistics: effect size and noise. The A/B test's 20% lift is 10 extra conversions (p = 0.33), so I recommend not shipping yet.
5. Business case: check the mix. Conversion rose in both channels. The blended fall comes from paid social growing from 20% to 44% of sessions, so I recommend not pausing it and judging it on cost per order and lifetime value.

## Key results
- S1 Orders by status (deduplicated): completed 16, refunded 2, cancelled 2
- S2 Top city by completed revenue: Nairobi, KES 20,650 (caveat: order 1013)
- S3 Customers who never ordered: 109 and 110
- S4 Repeat purchase rate: 50% (4 of 8 buyers)
- S5 Month-on-month revenue (1013 excluded): Jul -24.4%, Aug +2.9%, Sep +47.1%
- D3 Typical order value: median about KES 2,400
- T2 A/B test: 5.0% vs 6.0%, p = 0.33, do not ship yet
- Part 5: mix shift, not a site problem; do not pause paid social
