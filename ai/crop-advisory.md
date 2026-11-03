# Crop and irrigation advisory

**Track:** AI · **Level:** comfortable · **Domain:** agriculture

Recommend what to sow and when to water, grounded in the state agriculture department's own
advisories.

## The problem

A smallholder decides what to plant from habit and from whatever the shop owner recommends. Official
advisories exist, run to hundreds of pages, and are in the wrong language for the person who needs
them.

## Weeks 1 and 2: the model

**Predict:** which crop suits this soil and season, or what yield to expect.

**Data:** crop recommendation datasets (nitrogen, phosphorus, potassium, pH, rainfall, temperature,
humidity) are common on Kaggle and are a clean, small classification problem. `data.gov.in` carries
real area, production and rainfall series by district if you want something messier and more
interesting.

**Baseline (Week 1):** a decision tree. These datasets often give suspiciously high accuracy — if
you see 99 percent, something is leaking. Find out what before you celebrate; that investigation is
worth marks.

**Week 2:** a network on the same features, or a transfer-learned image model for leaf disease if
you would rather work with photographs.

## Weeks 3 and 4: the assistant

**Documents:** state agriculture department advisories, ICAR packages of practice, pest management
guidelines, scheme and subsidy documents.

**Questions it should answer:** "When should I sow groundnut in a rain-fed field?" "What do I do
about leaf curl on chilli?" "Which subsidy covers drip irrigation?" — with the clause cited.

**Week 4 agent, three tools:**

1. `recommend_crop(soil, season)` — your model
2. `search_advisory(question)` — your retrieval
3. `get_weather(district)` — a free weather API
4. Deliver one of them through **MCP**

## What will bite you

- **Advisories are regional and seasonal.** An answer correct for one district in one season is
  wrong elsewhere. Make the agent ask where the user is, and say so when it does not know.
- **Language.** If your users read Tamil or Hindi, an English-only answer is useless. Translating
  the output is a strong stretch goal; translating the *retrieval* is harder and more interesting.
- **Confident nonsense is dangerous here.** Someone could act on it and lose a season's income. Your
  limitations section should say plainly that this is not a substitute for an extension officer.

## Why this scores well

Real government documents are genuinely messy — scanned pages, tables, mixed languages — so your
chunking and retrieval decisions are real engineering, not a tutorial.
