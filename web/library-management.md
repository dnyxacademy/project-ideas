# Library management

**Track:** web · **Level:** comfortable · **Domain:** operations, campus

Issue and return books in a department library, with due dates that are actually tracked.

## The problem

A department library of a few thousand books runs on a register. Nobody knows what is out, who has
it, or what is three months overdue.

## Who uses it

- **A member** searches the catalogue, sees if a copy is free, and reserves it.
- **A librarian** issues and returns copies, and chases what is overdue.

## The minimum worth shipping

- Sign in. Members search and reserve; librarians issue, return and see overdue items.
- Catalogue search by title, author or ISBN, with availability shown.
- **A book has copies.** Three copies means three can be out at once, and the fourth request waits.
- Issue sets a due date; return clears it and frees the copy.
- An overdue list, with how many days late.

### Tables

`member`, `book` (title, author, isbn), `copy` (book, condition, status), `loan` (copy, member,
issued, due, returned). Four tables, and the book-versus-copy distinction is the interesting bit.

## Stage by stage

| Stage | What exists at the end |
|---|---|
| 1 | Static catalogue and book detail page, responsive |
| 2 | React and TypeScript: search, availability badges |
| 3 | Next.js on Vercel, Express API, Postgres. Real catalogue, real copies |
| 4 | Sign-in, librarian role, issue and return, overdue logic, tests, deployed |

## What will bite you

- **Book versus copy.** Modelling one row per book and a `count` column will fall apart the moment
  you want to know *which* copy someone has. Model copies properly on day one.
- **Date maths.** "Overdue" depends on today, so a test that hard-codes a date will pass in
  November and fail in December. Pass the current date into your function.
- **A copy cannot be issued twice.** Same constraint lesson as the clinic.

## Why this scores well

The schema is the most interesting of the six, which makes your stage 3 schema diagram worth looking
at, and the overdue calculation is easy to test.

## Stretch

Fines, renewals, a hold queue when every copy is out, import the catalogue from a CSV, a librarian
dashboard with counts, barcode scanning.
