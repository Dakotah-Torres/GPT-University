
# 📘 DS102 — SQL for Data Exploration  
## 🗓️ Day 1: What Makes an Analyst Powerful with SQL

---

### 🎯 Objectives
- Understand how analysts approach SQL differently from developers or DBAs  
- Revisit SQL building blocks through the lens of exploratory analysis  
- Set up your local SQL environment and create your first “analyst journal”

---

## 🧠 Concept 1: The Analyst’s Mindset

> "Analysts aren’t just writing queries — we’re interrogating reality."

Developers use SQL to build things. DBAs use SQL to maintain them.  
**Analysts?** We use SQL to answer questions, reveal insights, and guide decisions.

Analysts are:
- Hypothesis-driven
- Story-oriented
- Pattern-obsessed
- Outcome-focused

**Golden Rule:**  
> A powerful analyst spends more time shaping the *question* than the *query*.

---

## 🧠 Concept 2: SQL as a Thinking Tool

Let’s look at this familiar query:

```sql
SELECT product_id, COUNT(*)
FROM sales
GROUP BY product_id
ORDER BY COUNT(*) DESC;
```

At first glance, it's just product counts. But deeper down, you're asking:
- What are my best-selling products?
- Are purchases seasonal?
- Are sales growing or just spiking?

**Takeaway:** SQL evolves with your questions. It’s not just code — it’s a tool for layered thinking.

---

## ⚙️ Concept 3: Analytical Toolbox (Remixed)

| SQL Tool          | Use It When You Want To…                                  | Analyst Use Case                                        |
|------------------|------------------------------------------------------------|----------------------------------------------------------|
| `SELECT`, `WHERE`| Filter targeted records early                              | “Only users with >1 purchase”                            |
| `GROUP BY`, `HAVING` | Summarize and filter segments                        | “Which product categories underperform by region?”       |
| `CASE WHEN`       | Add classifications and flags                             | “Flag high-value vs low-value customers”                 |
| `ORDER BY`, `LIMIT` | Rank, filter top N results                            | “Top 10 reps by revenue in Q1”                           |
| `JOIN`            | Merge datasets and link behaviors                         | “Match users with campaign exposure and purchase data”   |

---

## 🛠️ Setup Tasks

### ✅ Step 1: Install a SQL Engine  
Choose one:
- PostgreSQL (recommended)
- SQLite (lightweight and simple)

### ✅ Step 2: Load a Practice Dataset  
Suggestions:
- [Chinook Music Store Dataset](https://github.com/lerocha/chinook-database)
- [Kaggle Datasets](https://www.kaggle.com/datasets)
- [Data.gov Datasets](https://www.data.gov/)

### ✅ Step 3: Create Your SQL Workspace  
Structure it like this:

```
SQL-Journal/
├── Day1/
│   ├── questions.md
│   └── queries.sql
├── Day2/
│   └── ...
```

---

## 📝 Homework – The Analyst’s Warmup

### Part 1: Write 5 Analyst-Style Questions
These should be in plain English. Example prompts:
- Which customers haven’t purchased in the last 30 days?
- What’s the average time between user logins?
- Which products are most frequently bought together?
- Who are the top 10 customers by revenue in the past 90 days?
- What percentage of customers churned this quarter?

### Part 2: Write 3 SQL Queries
Choose 3 questions and write queries to answer them using any dataset.

Include comments to explain your logic:

```sql
-- Top 10 customers by total revenue in the past 90 days

SELECT customer_id, SUM(total_amount) AS total_spent
FROM orders
WHERE order_date >= CURRENT_DATE - INTERVAL '90 days'
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;
```

---

## 🧰 Toolbox Reminder

You’ll use these throughout the course:
- PostgreSQL or SQLite for querying  
- Practice datasets from Kaggle, Data.gov, or GitHub  
- Markdown or Notion for your “SQL Journal”  
- ChatGPT or similar for code review and idea bouncing  

---

## 🎤 Closing Thought

> “The moment SQL becomes a tool for *thought*, not just *output*, is the moment you start seeing things others miss.”

---

🧭 Next Up: **Day 2 — Subqueries & Common Table Expressions (CTEs)**  
We’ll rewrite tangled subqueries into clean, readable logic flows — like turning spaghetti code into poetry.
