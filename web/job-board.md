# Fresher job board

**Track:** web · **Level:** ambitious · **Domain:** hiring, campus

A board for roles that actually accept final-year students and freshers, with the filters the big
sites get wrong.

## The problem

General job sites bury fresher roles under "2+ years experience" listings. A student spends an hour
filtering and finds four relevant posts.

## Who uses it

- **A candidate** filters by role, location, remote or on-site, and applies.
- **An employer** posts a role and reads applications in one place.
- **An admin** approves employers, so the board does not fill with spam.

## The minimum worth shipping

- Three roles: candidate, employer, admin. Sign-in tells them apart.
- An employer posts a job: title, description, location, remote flag, salary range, deadline.
- Admin approves or rejects a posting before it appears.
- A candidate browses and filters, opens a job, and applies with a note and a link to their CV.
- An employer sees applications for their own postings only, and marks each reviewed or rejected.

### Tables

`user`, `employer` (company profile), `job`, `application` (job, candidate, status). Four tables
with real relations — comfortably over the bar.

## Stage by stage

| Stage | What exists at the end |
|---|---|
| 1 | Static job list and detail page, responsive |
| 2 | React and TypeScript: list, filters, a job detail route |
| 3 | Next.js on Vercel, Express API, Postgres. Real jobs, real filters in SQL |
| 4 | Three roles, the approval flow, applications, tests, deployed |

## Stretch

Saved jobs, email on a new match, an employer dashboard with counts, full-text search, a public
company page, an application status timeline.

## What will bite you

- **Three roles is three times the authorisation work.** Every endpoint needs to ask "who is
  asking, and do they own this?" Write that check once as middleware, not in fifteen handlers.
- **Filter combinations.** Four filters at once means dynamic SQL. Let Prisma build it, and test
  the awkward combinations.
- **Scope.** This is the biggest project in the list. If stage 3 slips, drop the admin role and say
  so in your README. A finished two-role board beats a broken three-role one.

## Why this scores well

Role-based access is exactly what stage 4 is about, and "an employer cannot see another employer's
applications" is the kind of test that impresses a reviewer.
