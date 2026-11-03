# Student marketplace

**Track:** web · **Level:** comfortable · **Domain:** marketplace, campus

Buy and sell textbooks, cycles, calculators and hostel furniture inside one college.

## The problem

Every term, seniors leave with things juniors need, and the trade happens in chaotic WhatsApp
groups where listings scroll away in an hour and nobody can search last week's messages.

## Who uses it

- **A seller** lists an item in under a minute, with a photo and a price.
- **A buyer** searches by category and price, then contacts the seller.

## The minimum, by 28 November

- Sign in with a college email.
- Create, edit and delete your own listing: title, description, price, category, one photo.
- Browse everything, filter by category, search by title, sort by price or newest.
- Mark as sold — sold items stay visible but clearly marked.
- A listing shows how to reach the seller. **Only the owner can edit their own listing.**

### Tables

`user`, `listing` (seller, title, price, category, status), `category`, and `message` or `interest`
if you add contact in-app. Three tables minimum, four if you add messaging.

## Week by week

| Week | What exists at the end |
|---|---|
| 1 | Static listing grid and a detail page, responsive, with placeholder items |
| 2 | React and TypeScript: the grid, filters and search over mock data |
| 3 | Next.js on Vercel, Express API, Postgres. Real listings, real categories |
| 4 | Sign-in, ownership rules, image upload, tests, deployed |

## Stretch

In-app messages, saved searches, a report button, price-drop alerts, infinite scroll, a map of
hostel blocks.

## What will bite you

- **Image upload** is the trap. Files do not belong in Postgres. Use a free object store or a
  hosted image service, keep the URL in the row, and limit the file size. Budget a full day.
- **Ownership checks** must be on the server. Hiding the edit button is not security — someone will
  call your API directly, and a mentor will.
- **Search** starts as `WHERE title ILIKE '%term%'`. That is fine. Say in your README that it does
  not scale, and you have made an honest limitations section.

## Why this scores well

Ownership rules give you clean tests ("a user cannot edit someone else's listing"), and the grid
with filters makes a good two-minute demo.
