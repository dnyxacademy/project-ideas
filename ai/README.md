# AI project ideas

Every AI project here runs the same four stages, so what you choose is a **domain**, not a
different shape of work:

| Stage | Layer |
|---|---|
| 1 | One tabular dataset, cleaned and explored, and a baseline model with a score |
| 2 | A neural network on the same problem, compared honestly against that baseline |
| 3 | An assistant that answers from your documents, with citations |
| 4 | An agent with at least three tools, one through MCP, deployed |

**These are stages, not a schedule.** Take as long as each one needs.

So your domain needs **two things**, and this is the single most common way a project goes wrong at
stage 3:

1. **A dataset with rows** — numbers and categories to predict something from, for stages 1 and 2.
2. **A set of documents** — guidelines, rules, manuals, FAQs, reports — for the retrieval work in
   stages 3 and 4.

Pick your domain first and find both before you write any code. "I will find documents later" is
how people end up rebuilding everything at stage 3.

## Finding data

Look on Kaggle, Hugging Face Datasets, `data.gov.in`, UCI, and the open-data portal of whatever
ministry or body owns your domain. For documents, public PDFs from a government department, a
standards body or an NGO work well.

**Check the licence before you use it,** and put it in your README. "I found it on the internet" is
not a licence. Never use a dataset with real people's names, phone numbers or health records in it —
if the only version you can find has them, anonymise before anything is committed, and say what you
removed.

## The five below are starting points

Each one names a prediction task, the kind of documents to pair with it, and three tools for the
agent. Change the country, the crop, the subject or the scale freely — a project you care about is
one you will still be working on at 11pm at stage 3.

Your own idea is welcome. Use [propose-your-own.md](../propose-your-own.md).
