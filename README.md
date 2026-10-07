# Task 1 — Inconsistencies and duplicates

- **Name:** Daniel Ehab
- **ID:** 58-3825
- **Major and lab:** MET-02

## What I did

I cleaned a copy of club_signups.csv in task1.ipynb: 39 rows, every column stored as text. Faculty, club and city had 13, 13 and 9 spellings, one with a trailing space, so I stripped spaces, lower-cased, mapped the rest with explicit dictionaries (Media Engineering and Technology to MET, Soccer to Football) and asserted that only canonical values remain. Names got single spaces and title case, and emails were trimmed and lower-cased, giving each student one spelling. A dictionary turned the 9 spellings of yes and no in fee_paid into booleans. signed_up_at mixed YYYY-MM-DD and DD/MM/YYYY; the first number of the slashed dates runs from 13 to 18, so it is the day, and I parsed each format explicitly. Removing exact duplicates dropped 3 rows (39 to 36), and keeping one row per student_id and club dropped 4 more, leaving 32. I kept the latest submission by parsed time, because in all 4 resubmitted pairs the later one marks the fee as paid; keeping the first would list paid students as unpaid. The order of steps matters: deduplicating before fixing the club spellings still finds the 3 exact copies but only 2 of the 4 resubmissions, because Music/music and Debate/debate club look like different clubs, leaving 34 rows. Two different students are called Mohamed Adel and even share an email, so I identified people only by student_id; a name key would have merged them and deleted 2 real sign-ups, leaving 30.
