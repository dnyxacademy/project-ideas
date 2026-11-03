# Student dropout early warning

**Track:** AI · **Level:** gentle · **Domain:** education

Predict which students are at risk of dropping out, then answer a teacher's questions about what
the institution's own policy says to do about it.

## The problem

By the time a student stops attending, the reasons have been visible for weeks — attendance,
assignment submissions, marks sliding. A class teacher with 60 students cannot watch all of it.

## Weeks 1 and 2: the model

**Predict:** will this student pass, fail or drop out this term?

**Data:** student performance datasets are among the easiest to find — attendance, internal marks,
previous grades, study hours, family background, extra tuition. Search Kaggle for student
performance or dropout data, or use your own institution's anonymised records with permission.

**Baseline (Week 1):** logistic regression on attendance and internal marks. Note the accuracy, and
then note the F1 for the at-risk class specifically — this is the metric that matters, and it is
usually much worse than the accuracy.

**Week 2:** a small network on the same features. Say honestly whether it beat the baseline. On
tabular data of a few thousand rows it often will not, and writing that down is worth more marks
than hiding it.

## Weeks 3 and 4: the assistant

**Documents:** the academic regulations, the attendance policy, the examination rules, the
scholarship and fee-concession criteria. Every institution publishes these as PDFs.

**Questions it should answer:** "What is the minimum attendance to sit the exam?" "What happens if a
student is detained?" "Which concessions apply to a first-generation learner?" — each with a
citation to the clause.

**Week 4 agent, three tools:**

1. `get_student_risk(student_id)` — your Week 2 model
2. `search_policy(question)` — your Week 3 retrieval
3. `draft_message(student_id, concern)` — writes the note a teacher would send home
4. Deliver one of them through **MCP**

## Where this gets ethically serious

Read this before you start, and write about it in your README.

- A label of "likely to drop out" attached to a real student can become self-fulfilling. The output
  is a prompt for a conversation, never a decision.
- If your data has caste, religion, gender or income in it, check whether your model is simply
  learning to predict disadvantage. Report the error rate per group, not just overall.
- Names must never leave your machine. Work with IDs.

## Why this scores well

The bias section is not an add-on here — it is the heart of the project, which makes your ethics
write-up genuine rather than dutiful.
