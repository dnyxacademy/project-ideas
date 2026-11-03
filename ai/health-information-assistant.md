# Health information assistant

**Track:** AI · **Level:** ambitious · **Domain:** healthcare

Answer health questions from published clinical guidance, with citations — and refuse, clearly,
when it should.

**Read this first.** This is the hardest project here, and not because of the code. A health tool
that sounds confident and is wrong can hurt someone. If you pick it, your project is judged partly
on how well it refuses. If that does not appeal, pick another domain — there is no penalty for it.

## The problem

Someone with a symptom searches the web and gets a mix of reliable guidance, advertising and
nonsense, with no way to tell which is which.

## Stages 1 and 2: the model

**Predict:** a risk or outcome from tabular clinical features — diabetes, heart disease, a liver
condition. These teaching datasets (Pima, the UCI heart disease set, and similar) are small, clean
and well documented.

**Baseline (stage 1):** logistic regression, and a careful look at the confusion matrix. In health,
a false negative — telling someone they are fine when they are not — is the error that matters.
Optimise recall, and say why.

**Stage 2:** a network, or a transfer-learned image model on a public chest X-ray or skin-lesion set
if you want the computer-vision path.

## Stages 3 and 4: the assistant

**Documents:** public clinical guidance — WHO fact sheets, national health-ministry guidelines,
public CDC or NICE pages, ICMR documents. Use only published, citable guidance. Never scrape a
forum.

**Questions it should answer:** "What are the warning signs of dengue?" "What is the recommended
vaccination schedule for an infant?" — always with the source, and always with "see a doctor" where
the guidance says so.

**Stage 4 agent, three tools:**

1. `assess_risk(features)` — your model, framed as a screening score and never a diagnosis
2. `search_guidance(question)` — your retrieval
3. `find_nearest_facility(pin_code)` — a lookup, so the answer ends with somewhere to go
4. Deliver one of them through **MCP**

## The refusal is the feature

Build and test these explicitly, and demo them:

- **Emergency symptoms** — chest pain, breathing difficulty, heavy bleeding — short-circuit
  everything and return emergency instructions. Test this before anything else works.
- **No prescribing.** Never a drug name with a dose. Test that it refuses when asked.
- **No diagnosis.** "Guidance associates these symptoms with X; a doctor can confirm", never
  "you have X".
- **Out of scope** — pregnancy, children's dosing, a mental health crisis — gets its own careful
  answer with a helpline, not a guess.

Of your fifteen test questions in stage 3, make at least five things it **should refuse**. A model
that answers all fifteen has failed.

## What will bite you

- **No real patient data. Ever.** Public teaching datasets only.
- **Citations must be real.** A fabricated source is the worst possible failure here. Show the
  retrieved text next to the answer so a reader can check it.
- **Your limitations section is the most important page you will write.**

## Why this scores well

Safety behaviour is demanding, testable engineering: guardrails, routing, and an evaluation set
with refusals in it. Done honestly, it is the most impressive project on this list. Done carelessly,
it is the worst.
