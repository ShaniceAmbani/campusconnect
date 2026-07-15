# Group Activity: SQL Subquery Patterns
### CampusConnect — a course enrollment system

**Format:** groups of 2–3 · **Time:** ~35–40 minutes · **Files needed:** `starter_code.py`

---

## The scenario

You're on the data team for **CampusConnect**, a small course-enrollment
platform. The admin team keeps asking questions your data can answer —
but every question needs a number or a list calculated *first*, before
you can answer the real question. That's exactly what a subquery is for.

Three tables are already built and seeded in `starter_code.py`:

| Table | Holds |
|---|---|
| `courses` | id, title, category |
| `students` | id, name |
| `enrollments` | id, student_id, course_id |

Don't peek at the data by printing the raw tables yet — for Task 1
especially, predicting first is the point.

---

## How this works

For each task:
1. **Think First** — answer the prediction question with your group,
   out loud, before writing any SQL. Write your guess down.
2. **Write the query** — fill in the matching `task_N_sql` variable in
   `starter_code.py`.
3. **Run it** — `python3 starter_code.py` — and check your prediction
   against the real result.
4. **Explain it** — one person in your group should be able to say, in
   plain English, what the inner query returns and how the outer query
   uses it.

---

## Task 1 — Scalar Subquery (returns ONE value)

> **Question:** Which courses have *more enrollments* than the average course?

**Think First:** Without running anything — do you expect most courses
to be above or below average, or roughly a 50/50 split? Why might it
NOT be 50/50?

**Hint:** You'll need two things from `enrollments`: a count of
enrollments *per course*, and the *average* of those counts. One of
those belongs in a subquery.

---

## Task 2 — IN Subquery (returns a LIST)

> **Question:** Which students are enrolled in Python Basics?

**Think First:** `courses` doesn't have a list of students, and
`students` doesn't have a list of courses. Which table actually
connects the two? What column in it identifies "Python Basics"?

**Hint:** First figure out Python Basics' `course_id` — you can find
it by inspection, but write the query so it doesn't rely on you
already knowing the number is `1`. That's what the subquery is for.

---

## Task 3 — NOT IN Subquery (finds what's MISSING)

> **Question:** Which students are not enrolled in any course?

**Think First:** How would you answer this by hand, looking at the
`enrollments` table? What are you actually checking the *absence* of?

**Hint:** Start from Task 2's structure. What changes when you're
looking for students *outside* a list instead of inside one?

---

For each query , group should be able to communicate : 

- what question it answers
- what the inner query hands back (a number, or a list)
- what the outer query does with that
s.