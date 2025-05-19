Assessment SQL Query Explanations and Challenges

✅ Question 1: Customer Portfolio Summary (`Assessment_Q1.sql.sql`)
Approach:
- Retrieved each user's total number of savings accounts and investment plans.
- Calculated the total confirmed deposits using `COALESCE` to handle nulls.
- Used `LEFT JOIN` to include users without accounts or plans.

**Challenges:**
- Ensured accurate aggregation using `COUNT(DISTINCT ...)`.
- Prevented null values from affecting totals with `COALESCE`.
