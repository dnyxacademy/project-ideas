# Event RSVP and check-in

**Track:** web · **Level:** gentle · **Domain:** events, campus

The smallest project here. Pick it if you have never written code before and want to finish well
rather than finish barely.

## The problem

A club runs weekly sessions. Headcount comes from a Google Form, attendance from a paper sheet, and
nobody knows who actually turned up versus who said they would.

## Who uses it

- **An attendee** sees what is on, says they are coming, and can change their mind.
- **An organiser** creates an event with a capacity, and marks people present on the day.

## The minimum worth shipping

- Sign in. Organisers create and edit events; everyone else can only RSVP.
- An event has a title, description, date and time, venue and capacity.
- RSVP yes or no, and change it until the event starts.
- **Capacity is enforced.** When it is full, further RSVPs join a waiting list.
- An attendee list for organisers, with a present or absent tick.
- A dashboard: said yes, actually came, as numbers.

### Tables

`user`, `event`, `rsvp` (user, event, status), `attendance` (or a `checked_in_at` column on `rsvp`).
Three or four tables.

## Stage by stage

| Stage | What exists at the end |
|---|---|
| 1 | Static event list and detail page, responsive |
| 2 | React and TypeScript: list, filter by upcoming or past, an RSVP button with local state |
| 3 | Next.js on Vercel, Express API, Postgres. Real events and RSVPs |
| 4 | Sign-in, organiser role, capacity and waiting list, tests, deployed |

## Stretch

A QR code per RSVP for check-in, a calendar export, reminder emails, recurring events, a public
page needing no sign-in, a CSV export of the attendee list.

## What will bite you

- **Capacity under load** is the same race as the clinic's double-booking. Count in the database,
  not in JavaScript.
- **Past versus upcoming** needs a decision: does an event disappear at its start time, or its end?
  Write it down, then test it.
- **The waiting list promotion** — when someone cancels, who moves up? Pick a rule (earliest RSVP)
  and keep it.

## Why this scores well

It is small enough that you can finish the minimum by stage 3 and spend stage 4 on tests, polish and
a confident demo. That reads far better than an ambitious half-built thing.
