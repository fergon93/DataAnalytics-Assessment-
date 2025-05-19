## Assessment SQL Query Explanations and Challenges

### ✅ Question 1: Customer Portfolio Summary (`Assessment_Q1.sql.sql`)
**Approach:**
- Retrieved each user's total number of savings accounts and investment plans.
- Calculated the total confirmed deposits using `COALESCE` to handle nulls.
- Used `LEFT JOIN` to include users without accounts or plans.

**Challenges:**
- Ensured accurate aggregation using `COUNT(DISTINCT ...)`.
- Prevented null values from affecting totals with `COALESCE`.

---

### ✅ Question 2: Transaction Frequency Categorization (`Assessment_Q2.sql.sql`)
**Approach:**
- Merged transaction data from savings and plans into a common monthly format.
- Calculated average monthly transaction count per user.
- Categorized users into High, Medium, and Low frequency based on thresholds.
- Ordered categories using `FIELD()` for custom sort.

**Challenges:**
- Standardized date formats (`%Y-%m`) across tables.
- Carefully managed grouping to avoid double counting.

---

### ✅ Question 3: Detect Inactive Users (`Assessment_Q3.sql.sql`)
**Approach:**
- Combined savings and plan transactions into one dataset with consistent column names.
- Used `ROW_NUMBER()` to isolate the most recent transaction per user.
- Calculated inactivity days and filtered users inactive for ≥ 365 days.

**Challenges:**
- Ensured accurate window function usage and filtering on `rn = 1`.
- Correctly calculated inactivity duration with `DATEDIFF`.

---

### ✅ Question 4: Customer Lifetime Value (CLV) (`Assessment_Q4.sql.sql`)
**Approach:**
- Aggregated transaction count and profit per user from both savings and plans.
- Calculated tenure in months using `TIMESTAMPDIFF`.
- Computed CLV with the formula:  
  \[
  CLV = \left(\frac{total\_transactions}{tenure\_months}\right) \times 12 \times \left(\frac{total\_profit}{total\_transactions}\right)
  \]
- Rounded CLV and sorted results in descending order.

**Challenges:**
- Handled edge cases where `tenure_months = 0` to avoid division errors.
- Verified all financial metrics used correct assumptions (e.g., `0.001 * amount` for profit).

---

This breakdown helps explain the logic and thought process behind each SQL script and highlights how issues were addressed.
