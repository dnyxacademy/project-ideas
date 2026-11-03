# Retail demand and returns assistant

**Track:** AI · **Level:** comfortable · **Domain:** retail, e-commerce

Forecast what will sell, and answer customer-policy questions from the shop's own terms.

## The problem

A small online shop over-orders what does not move and runs out of what does. Separately, the
support inbox fills with the same twenty questions about returns, shipping and refunds.

## Stages 1 and 2: the model

**Predict:** units sold next week per product, or whether an order will be returned.

**Data:** online retail and e-commerce transaction datasets are plentiful — the UCI online retail
set, and sales or returns data on Kaggle. Rows are orders, so you get quantity, price, category,
date and customer, and you engineer features from them.

**Baseline (stage 1):** last week's sales as the prediction. That is a serious baseline, not a joke.
It is hard to beat, and beating it is the point. Then linear regression with day-of-week, month and
category features.

**Stage 2:** a network, and an honest table of the error against that naive baseline.

## Stages 3 and 4: the assistant

**Documents:** the return and refund policy, shipping terms, warranty terms, the FAQ, and the
consumer protection rules the shop operates under.

**Questions it should answer:** "Can I return an opened item after 20 days?" "Who pays return
shipping?" "What is covered under warranty?" — with the clause quoted, so support staff can paste
the answer with confidence.

**Stage 4 agent, three tools:**

1. `forecast_demand(product, week)` — your model
2. `search_policy(question)` — your retrieval
3. `check_order_status(order_id)` — against a small invented orders table
4. Deliver one of them through **MCP**

## What will bite you

- **Never split time-series data randomly.** Training on next month and testing on last month leaks
  the future and gives a beautiful, meaningless score. Split by date. Reviewers look for this one.
- **Seasonality.** A festival week is not a normal week. Say what your model cannot see.
- **Policy answers have consequences.** If it tells a customer they can return something they
  cannot, the shop is on the hook. The agent should quote, and point to a human.

## Why this scores well

The naive baseline makes your comparison table honest and easy to read, and the time-series split
is a mistake most beginners make — avoiding it deliberately, and explaining why in your README,
reads as real understanding.
