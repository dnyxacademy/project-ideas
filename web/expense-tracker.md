# Shared expense tracker

**Track:** web · **Level:** comfortable · **Domain:** fintech, personal

Who paid for what in a hostel room or a trip, and who owes whom at the end.

## The problem

Four flatmates split groceries, electricity and the internet bill. One person pays, the others
promise to settle, and a month later nobody remembers.

## Who uses it

- **A member** adds an expense, says who paid and who shares it, and sees what they owe.
- **A group** wants one number each at the end of the month, not a spreadsheet argument.

## The minimum worth shipping

- Sign in, create a group, invite others by email.
- Add an expense: amount, description, date, category, who paid, who it is split between.
- Equal splits are enough. Unequal splits are a stretch goal.
- A balance per member: owes, is owed, net.
- **A settle-up action** that records a payment and resets the balance.
- Only group members see a group.

### Tables

`user`, `group`, `group_member`, `expense`, `expense_share`. Five tables, and a genuine join table —
good material for the schema diagram.

## Week by week

| Week | What exists at the end |
|---|---|
| 1 | Static dashboard and add-expense form, responsive |
| 2 | React and TypeScript: the form, a list, balances computed in the browser |
| 3 | Next.js on Vercel, Express API, Postgres. Real groups, expenses and shares |
| 4 | Sign-in, membership rules, balance tests, deployed |

## What will bite you

- **Never use floats for money.** Store paise as integers. `0.1 + 0.2` is not `0.3`, and a reviewer
  will check this one specifically.
- **Splitting 100 by 3** leaves a paisa. Decide who gets it (the payer, by convention) and test it.
- **Balance maths** is the hard part, not the UI. Write the balance function first, test it with
  invented numbers, then build screens around it.

## Why this scores well

Money maths is testable and unforgiving, so your eight tests are meaningful rather than decorative.
The balance calculation is also a good thing to be asked about in a review.

## Stretch

Unequal and percentage splits, recurring expenses, a monthly report, a chart by category, export to
CSV, settling through a payment link.
