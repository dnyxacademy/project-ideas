# Insurance claim triage

**Track:** AI · **Level:** comfortable · **Domain:** finance, insurance

Score a claim for risk, then answer "is this even covered?" from the policy wording itself.

## The problem

A claims team reads every claim in the order it arrived. Simple ones wait behind complicated ones,
and the question that decides most cases — what does the policy actually cover — means searching a
sixty-page document under time pressure.

## Weeks 1 and 2: the model

**Predict:** is this claim likely to be straightforward, or does it need a human review?

**Data:** insurance claim and fraud-detection datasets are widely available on Kaggle (claim
amount, policy age, incident type, vehicle or property details). Credit default and loan approval
datasets work just as well if you prefer lending to insurance.

**Baseline (Week 1):** logistic regression. These datasets are **badly unbalanced** — perhaps two
percent of claims are flagged — so a model that says "fine" to everything scores 98 percent
accuracy and is worthless. Showing that you noticed, and switching to precision, recall and the
confusion matrix, is half the value of the first week's work.

**Week 2:** a network, plus a word on class weighting or resampling and whether it helped.

## Weeks 3 and 4: the assistant

**Documents:** policy wordings, IRDAI circulars, exclusion lists, claim procedure manuals. Insurers
publish policy documents openly, and they are exactly the dense, clause-numbered text that
retrieval is good at.

**Questions it should answer:** "Is damage from a flood covered under this policy?" "What is the
waiting period for a pre-existing condition?" "What documents does a claim need?" — with the clause
number cited, because without one the answer is useless to a claims officer.

**Week 4 agent, three tools:**

1. `score_claim(claim)` — your model
2. `search_policy(question)` — your retrieval
3. `check_documents(claim_type)` — lists what is still missing
4. Deliver one of them through **MCP**

## What will bite you

- **An unbalanced dataset will flatter you.** Report the confusion matrix every single time.
- **A wrong "not covered" is worse than a wrong "covered".** Say which error your model makes more
  often, and which one you would rather make.
- **Never present this as a decision.** It ranks and it quotes; a person decides. Put that in the
  README and say it in the demo.

## Why this scores well

Clause-numbered documents make citation quality easy to judge — either the clause it quoted says
what it claims, or it does not — so your fifteen test questions in Week 3 have crisp right answers.
