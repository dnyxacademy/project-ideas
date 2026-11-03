# Project ideas

Eleven project briefs for people learning **full-stack web development** or **AI** — each one small
enough to actually finish, starting from close to zero.

Most project lists you find online describe platforms built over months by people who already know
the stack. These are deliberately smaller, and each one says plainly what the minimum is.

Every brief gives you:

- the problem, and who actually has it
- **a minimum worth shipping** — strict, and achievable
- a table sketch (web) or a dataset-and-documents shape (AI)
- a four-stage build order — stages, not a schedule, so take as long as each needs
- **the specific things that will trip you up**, which is the part most lists leave out
- stretch goals for when you are ahead

Free to use, adapt and teach from, with credit — CC BY 4.0.

## Web development

| Idea | Level | What makes it interesting |
|---|---|---|
| [Event RSVP and check-in](web/event-rsvp.md) | gentle | The smallest. Finish well instead of barely |
| [Clinic appointment booking](web/clinic-appointment-booking.md) | comfortable | One rule — never double-book — that tests beautifully |
| [Student marketplace](web/student-marketplace.md) | comfortable | Image upload and ownership rules |
| [Shared expense tracker](web/expense-tracker.md) | comfortable | Money maths, and five tables with a real join |
| [Library management](web/library-management.md) | comfortable | The best schema here: books versus copies |
| [Fresher job board](web/job-board.md) | ambitious | Three roles, so authorisation everywhere |

More detail, and the shared four-stage arc: [web/README.md](web/README.md)

## AI

Read [ai/README.md](ai/README.md) first — every AI project needs **a dataset and a document set**,
and finding only one of the two is how the retrieval work goes wrong later.

| Idea | Level | What makes it interesting |
|---|---|---|
| [Student dropout early warning](ai/student-dropout-early-warning.md) | gentle | Bias is the heart of it, not an appendix |
| [Crop and irrigation advisory](ai/crop-advisory.md) | comfortable | Real government PDFs: messy, regional, multilingual |
| [Insurance claim triage](ai/insurance-claim-triage.md) | comfortable | Unbalanced data, and clause-numbered documents |
| [Retail demand and returns](ai/retail-demand-and-returns.md) | comfortable | A naive baseline that is genuinely hard to beat |
| [Health information assistant](ai/health-information-assistant.md) | ambitious | Judged on how well it refuses |

## How to choose

1. **Will you still care about it three stages in?** That is the only question that really matters.
   Stage 3 is the heaviest, and interest is what gets you through it.
2. **Be honest about your level.** "Gentle" is not a lesser choice. A finished small project is
   worth far more than an ambitious half-built one, and anyone reviewing your work has seen plenty
   of both.
3. **Check you can get the data** before you commit, if you are on the AI track.
4. **Do not pick what your friend picked** just to compare notes. You will both learn less, and
   two identical repositories raise questions neither of you wants to answer.

### Levels

| Level | Means |
|---|---|
| gentle | You have not written code before. The minimum is reachable by stage 3, leaving room to polish |
| comfortable | You can give all four stages proper time. Most people should be here |
| ambitious | You have built something before. There is real difficulty in it, and it can be cut back if it slips |

## Scope, honestly

The minimum on each page is genuinely minimal, and the stretch goals are there for when you are
ahead — not a checklist. **Shipping the minimum, tested and deployed, with an honest README, counts
for more than a sprawling unfinished platform.** That is true whether someone is marking it or you
are showing it to an employer.

Each brief is roughly four stages of work. How long a stage takes is up to you: a week each if you
are on a taught course, longer if you are fitting it around a job or a degree. What does not work is
stopping after stage 2 — a front end with no data behind it is the most common abandoned project
there is.

## Bring your own idea

Very welcome, and often the best projects. [propose-your-own.md](propose-your-own.md) is a one-page
template that forces the useful questions early — and if you have someone mentoring you, it is the
thing to get reviewed before you start building.

## More ideas, and places to go deeper

Other people's lists, worth browsing — especially if none of the briefs above appeals. They are not
ours, we do not control them, and most are pitched at a far bigger scope than these. Read them for
the idea, then cut it down to the minimum you can actually ship.

### Idea catalogues

| Where | What you get |
|---|---|
| [NamasteDev project ideas](https://namastedev.com/project-ideas) | Product-style briefs with a difficulty and a stack, mostly platform-sized |
| [roadmap.sh projects](https://roadmap.sh/projects) | Ideas graded beginner to advanced, with requirements per project |
| [Frontend Mentor challenges](https://www.frontendmentor.io/challenges) | Real designs to build to. Excellent early practice |
| [Project-based learning](https://github.com/practical-tutorials/project-based-learning) | "Build X from scratch" tutorials, by language |
| [The Odin Project](https://www.theodinproject.com/paths) | A full project-first curriculum. These briefs borrow its SQL-before-NoSQL order |

### Data and documents, for the AI track

| Where | What you get |
|---|---|
| [Kaggle datasets](https://www.kaggle.com/datasets) | The widest choice, with notebooks showing what others did |
| [Hugging Face datasets](https://huggingface.co/datasets) | Text and multimodal sets, easy to load in a notebook |
| [UCI repository](https://archive.ics.uci.edu/datasets) | Small, clean, well-documented teaching sets |
| [data.gov.in](https://data.gov.in) | Indian government open data, by ministry and district |
| [Public APIs](https://github.com/public-apis/public-apis) | Free APIs — useful as a tool for an agent |

### Learning and reference

| Where | What for |
|---|---|
| [MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development) | The reference for HTML, CSS and JavaScript. Trust it over a blog post |
| [Hugging Face agents course](https://huggingface.co/learn/agents-course/unit0/introduction) | Free course on agents |
| [Model Context Protocol docs](https://modelcontextprotocol.io) | MCP itself |

**Two cautions.** A tutorial you can follow line by line teaches you very little — read it, close
it, then build. And whatever you borrow from an idea list, the project has to be your own work:
your commits, your decisions, and your answers when someone asks why.

---

## If you are on the Dnyx Academy programme

Everything above applies. These are the parts specific to the November 2026 batch:

- **Pick in Week 1, and get it approved by Tuesday.** Then do not change it — restarting in Week 3
  is the most reliable way to not finish.
- **Your minimum is due by noon on Saturday 28 November.** Each idea page lists its own minimum; on
  top of that your track has a bar the final project is marked against, in your starter repository
  at `docs/week-plan.md`:
  - **Web:** sign-in, three related PostgreSQL tables, a Next.js front end in TypeScript,
    validation, eight automated tests including one end-to-end flow, deployed front end and API, a
    README, a two-minute video, and a "How I used AI" note.
  - **AI:** your Weeks 1 to 3 work still visible, an agent with three tools (one through MCP),
    logged traces, ten test cases with results and an honest failure analysis, a deployed demo, a
    README with limitations, a video, and a "How I used AI" note.
- **Your own idea** needs a mentor's approval by Tuesday of Week 1. Post the filled-in template in
  your batch chat or your lesson Q&A.
- A mentor will help you decide what to cut. Ask in Week 1, not Week 3.

**Where to go next**

- Your starter template: [web-starter](https://github.com/dnyxacademy/web-starter) ·
  [ai-starter](https://github.com/dnyxacademy/ai-starter)
- The day's brief: [MERN-Assignments](https://github.com/dnyxacademy/MERN-Assignments) ·
  [AI-Assignments](https://github.com/dnyxacademy/AI-Assignments)
- Your tickets, due dates and submissions: [Dnyx Learn](https://learn.dnyxacademy.com)

---

CC BY 4.0 — use these ideas anywhere, with credit. Maintained by
[Dnyx Academy](https://dnyxacademy.com).
