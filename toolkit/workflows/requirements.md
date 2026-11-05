# Requirement Discovery Playbook

Use after reading the project README, relevant source files and the *actual* data.

## Ask questions that change the implementation
A useful stakeholder question has (a) a concrete ambiguity, (b) possible answers, and (c) a clear effect on business logic, the UI or a test.

| Dimension | Questions to investigate |
|---|---|
| Goal / actor | Who uses the result? What operational decision follows from it? |
| Units / definition | How are "success", "demand", "covered", "active" or "late" defined? |
| Input & identity | Which files are authoritative? How do IDs join? What are valid units and dates? |
| Duplicates & history | Latest event wins, earliest event wins, or preserve full event history? |
| Missing / error states | Exclude, infer, keep unknown, block operation, or warn? |
| Boundaries / exceptions | Inclusive vs exclusive thresholds, timezones, holidays, overrides, illegal transitions? |
| Constraints | Global vs per-location budgets, minimums/maximums, forbidden locations, fairness/privacy? |
| Trade-offs | False positive vs false negative costs, speed vs accuracy, cost vs quality? |
| Acceptance | Which inputs and outcomes would a stakeholder use to approve the result? |

**Avoid:** "Please tell me every hidden requirement."
**Prefer:** "For orders already dispatched, should cancellation be rejected, queued for manual approval or permitted? Which behavior is the expected acceptance test?"

## Procedure
1. Profile the real data; record schema, 5–10 representative rows and suspicious records.
2. Write a table with columns: Question / Evidence of ambiguity / Why it matters / What changes if answer A vs B / Priority.
3. Ask only the top 3–5 questions first; batch related ones when efficient.
4. Record the stakeholder answers verbatim or faithfully paraphrased with source.
5. Turn each answer into a testable rule (example input, expected output).
6. Reopen questions while implementing when new edge cases appear.
7. Stop asking once additional answers have low impact relative to build/test time.

## Hand-off to implementation
Produce a compact brief with:
- Goal and intended users
- Confirmed input/output contracts
- Business rules with source
- Open assumptions (clearly tagged)
- Acceptance checks
- Priority order for the next working slice

Do not turn exploratory patterns into normative business rules without stakeholder confirmation or a justified, disclosed assumption.
