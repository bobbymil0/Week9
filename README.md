# Week 9 Homework: The Case of the Missing Festival Lanterns

## Student Info

Name: Bobby Nepali  
Student number: 2412077  
GitHub username: bobbymil0  

---

## Summary

This program analyzes festival lantern records and returns a structured report about what happened in the log. The `analyze_lanterns` function takes a set of expected lantern names, a list of `(lantern_name, actual_section)` records, and a dictionary of correct sections. It identifies which lanterns were seen, which expected lanterns were missing, and which unexpected lanterns appeared. It also detects duplicate lantern names, counts all log records by section, and reports expected lanterns that were placed in the wrong section. The result is returned as one dictionary with six required keys.

---

## Approach

Your approach:

- First, I created sets and dictionaries to store seen lantern names, duplicates, section counts, and wrong-section details.
- During one loop over `lantern_log`, I updated seen names, detected duplicates with a `seen_once` set, counted records per section, and checked section correctness only for expected lanterns.
- For wrong sections, I stored only the first wrong section found for each expected lantern.
- After the loop, I used set subtraction to compute `missing_lanterns` and `unexpected_lanterns`.
- Finally, I returned one report dictionary with exactly the required six keys.

---

## How I Used Dictionaries and Sets

Your explanation:

```text
Sets were used for seen_lanterns, seen_once, duplicate_lanterns, missing_lanterns, and unexpected_lanterns.
Dictionaries were used for count_by_section and wrong_section_lanterns (including inner expected/actual fields).
Sets made membership checks and set difference fast and simple. Dictionaries made counting and key-based lookups straightforward.
Using only lists would require extra loops for membership checks and updates, which would be slower and less clean.
```

---

## Complexity

Your complexity explanation:

```text
Time complexity: O(n + m)
Space complexity: O(a + s)
Explanation: The function loops through lantern_log once (n records) with O(1)-average set/dict operations inside the loop, then does set subtraction over expected and seen lantern sets (m and a sizes). There are no nested loops over the log. Extra space is used for sets of unique lantern names (a) and dictionaries for section counts and wrong-section records (s and up to a).
```

---

## Edge-Case Checklist

Check the cases your solution handles.

- [x] empty `lantern_log`
- [x] empty `expected_lanterns`
- [x] no missing lanterns
- [x] no unexpected lanterns
- [x] duplicate lanterns
- [x] wrong-section lanterns
- [x] unexpected lanterns ignored for wrong-section checking

Add one more edge case you thought about:

```text
An expected lantern appears in multiple wrong sections; only the first wrong section should be recorded.
```

---

## Tests I Added

Describe the test you added:

```text
Test name: test_analyze_lanterns_records_first_wrong_section_only
What it checks: An expected lantern appears in two wrong sections and later once in the correct section; the report keeps only the first wrong section and still marks it as duplicate.
Why it matters: It verifies the assignment rule about recording the first wrong section only.
```

---

## How to Run the Tests

```bash
pytest -q
```

Paste your final test result here:

```text
Could not run in this environment: Python/pytest command not available in terminal session.
```

---

## Assistance and Sources

```text
AI used? Y/N: Y
What it helped with: Implementing analyze_lanterns, adding a meaningful test, and drafting README explanations.
Other sources used: Homework brief and starter files.
```

---

## Submission Self-Check

Before submitting, check:

- [x] I completed `analyze_lanterns` in `src/challenges.py`.
- [x] I added at least one meaningful test of my own.
- [ ] `pytest -q` passes.
- [x] I completed this README.
- [ ] I pushed my latest work to GitHub.