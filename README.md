# SQL-Progress-Journal-day-14

# 📊 CS50 SQL Moneyball – Day 14: Pattern Matching with `LIKE` and Deep JOINs

## 🔄 Focus
- Relational JOINs across `players`, `performances`, and `teams`
- Mastered the SQL `LIKE` operator for flexible string filtering
- Debugged a case sensitivity issue in SQLite and solved it with precision

---

## 🧠 What I Learned Today

Today was a full-day SQL session. I:

- Reinforced how JOINs link tables using primary and foreign keys
- Practiced tracing which teams specific players played for (Task 5-style)
- Learned how `LIKE` works and why it didn’t return results at first
- Discovered SQLite’s case sensitivity and learned to use `LOWER()` with `LIKE` for flexible searches

---

## ✅ Key Commands Used

```sql
-- Trace player team history
SELECT DISTINCT teams.name
FROM players
JOIN performances ON players.id = performances.player_id
JOIN teams ON performances.team_id = teams.id
WHERE players.first_name = 'Rickey'
  AND players.last_name = 'Henderson'
ORDER BY teams.name DESC;

-- Debugging pattern matching
SELECT first_name, last_name
FROM players
WHERE first_name LIKE 'Rick%';  -- This failed

-- Corrected with case-awareness
SELECT first_name, last_name
FROM players
WHERE LOWER(first_name) LIKE 'rick%';  -- This works

🌱 Progress Snapshot
📅 Day 14

🕖 Studied SQL from 7am

🧩 Gained full clarity on JOIN structure + filtering

🔎 Learned to use SQL pattern matching tools (LIKE, %, LOWER())

🧠 Reflection
Even a small tool like LIKE opens up powerful searching capabilities in SQL. This was a great reminder that debugging leads to real learning — and now pattern matching feels intuitive.
