# Clinic appointment booking

**Track:** web · **Level:** comfortable · **Domain:** healthcare, scheduling

The safest choice in the list. The rules are obvious, so you spend your four weeks learning the
stack rather than arguing about requirements.

## The problem

A two-doctor clinic takes appointments by phone. The receptionist keeps a paper diary, double-books
when it gets busy, and cannot tell a caller what is free next Tuesday without flipping pages.

## Who uses it

- **A patient** wants the first free slot with a particular doctor, without calling.
- **The receptionist** wants today's list, and to block a slot when a doctor is away.

## The minimum worth shipping

- Sign in. A patient sees only their own appointments; staff see everyone's.
- Pick a doctor, see free slots for the next 14 days, book one, get it confirmed on screen.
- Cancel up to a set time before. A cancelled slot becomes free again.
- Staff: today's list, and a way to block time off.
- **Two slots can never be booked twice.** This is the whole project.

### Tables

`doctor`, `patient` (one per user), `appointment` (doctor, patient, start, end, status), and
`availability` or `time_off`. Four tables, which clears the three-table bar.

## Week by week

| Week | What exists at the end |
|---|---|
| 1 | Static pages: the clinic, the doctors, a booking form that does nothing yet |
| 2 | React and TypeScript: a slot picker driven by hard-coded data |
| 3 | Next.js on Vercel, Express API, Postgres. Slots come from real rows |
| 4 | Sign-in, patient vs staff, tests for the double-booking rule, deployed |

## Stretch

Email confirmation, a waiting list for a freed slot, recurring availability, an iCal export, a
reschedule flow (harder than it looks), an SMS reminder.

## What will bite you

- **Time zones and clock maths.** Store UTC, render local. Decide early whether a slot is 15 or 30
  minutes and keep it fixed; variable durations are a Week 5 problem.
- **The race.** Two patients tap the last 10:00 slot at once. One must fail cleanly. A unique
  constraint on `(doctor_id, start)` in the database is the real fix — not a check in your code.
- **Do not store real patient data.** Seed it with invented names. Health records are not a thing
  to practise on.

## Why this scores well

The double-booking rule gives you something precise to test, so the eight tests in Week 4 write
themselves, and your end-to-end flow — book, see it, cancel, see it freed — is obvious.
