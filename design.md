# GPU Brief

Design for `ewVisible/gpu-brief`.

Issue #1 asks for a GPU news product that is different and can make money. The difference is the product: a decision, not another headline feed.

## What it is

GPU Brief tells a buyer what to do with money this week.

Each item is one card:

- **Action:** buy, wait, sell, or rent.
- **Number:** the price, the stock, or the cost that changed.
- **Why:** one sentence. A launch, a shortage, or a used-market move is context for the number, not a separate article.
- **Do this:** one link, or "do nothing".

A card that has no number and no action is not published.

## Who pays

Three people already spend money on this decision. A general reader does not.

| Reader | Decision they pay to get right | What they use the brief for |
| --- | --- | --- |
| Small AI team | Rent H100/H200/B200 this week, or wait | Cost per million tokens versus last week |
| Used-market trader | Buy or sell 4090, 5090, A100, L40S | Street price and how many units are actually listed |
| Local inference user | Buy a used card for a homelab, or keep the one they have | Price versus the workload they already run |

VideoCardz, Wccftech, and Tom's Hardware already cover the launch rumor. This brief does not compete with them on speed or on volume. It competes on the action those articles never make.

## How it is different

- One card, not forty articles. If nothing actionable changed, the brief says so and stops.
- The unit is a GPU SKU and a market, not a press release.
- News is allowed only as the reason under a number.
- No score, no "top 10", no rewritten press release.
- A card names its source and its time. A number without a source is not published.

## What a card looks like

```text
WAIT  H100 SXM 80GB  US on-demand rent
$2.49 / GPU-hour, down $0.31 in 7 days. Three clouds in stock.
Do this: do not sign a 30-day reservation this week.
Source: listed prices at 2026-11-13 09:00 UTC.
```

The first version is a markdown file in `briefs/`, one file per day. A site comes after ten briefs exist and someone other than the author has asked for the next one.

## How it makes money

Money follows the decision, in this order. Do not sell ads against a feed that does not exist.

1. **Paid brief.** A weekly card list for the three readers above. Free sample is one card. The paid issue is the full list plus the "do nothing" calls, which are the part a headline site will not write.
2. **Referral on the action.** When a card says buy or rent, the link can be an affiliate or a partner cloud. The card still states the price and the alternative. A card is not written to fit the link.
3. **Later, a price feed.** Normalized rent and street prices for the SKUs the brief already tracks, sold to small clouds that do not want to scrape. Not in the first version.

The first dollar is a paid weekly brief, not a pageview. Ten free briefs are the proof. Then a price.

## What the first version will not do

- No accounts, no paywall, no app.
- No automatic scraping until the card format has been written by hand at least ten times. The sources and the fields get decided by writing cards, not by building a crawler first.
- No coverage of every GPU. Start with the SKUs the three readers actually trade: H100, H200, 4090, 5090, A100, L40S.
- No rumor without a price or a stock change.

## Repository after this initialization

```text
README.md          what this is
design.md          this spec
briefs/TEMPLATE.md the card format
briefs/             one markdown file per brief, added as they are written
```

`main` is the default branch. It did not exist until this commit: the repository had no commits, so GitHub had no branch to serve and no CI to read.

## Next step

Write the first real brief in `briefs/` from public prices, using `briefs/TEMPLATE.md`. Do not add a scraper in that step.
