# Scraper API Pricing: What Each Plan Really Costs, How Credits Burn, and Which Tier Fits Your Workload

ScraperAPI pricing runs from $49/month (Hobby) up to $1,975/month (Advanced), with a custom-priced Enterprise tier above that, a 7-day free trial with 5,000 credits, and 10% off everything on annual billing. But the number on the pricing page is only half the story — what you actually pay per request depends on credit multipliers for JavaScript rendering, premium proxies, and hard-to-scrape domains. This guide breaks down all seven plans, the real per-page costs, and the limits that only show up in the fine print.

## Quick pick

Most developers and small teams land on one of three tiers: **Hobby ($49/mo)** for solo projects, **Startup ($149/mo)** for regular monitoring jobs, or **Business ($299/mo)** if you need country-level geotargeting outside the US and EU. Annual billing cuts every plan by 10%, and the 7-day trial (5,000 credits, no credit card) lets you test your actual target URLs before paying anything.

> **Fastest route:** if you already know your monthly request volume, 👉 [check current plan prices and start the free trial](https://www.scraperapi.com/signup?fp_ref=coupons) — 5,000 credits, no credit card required, and you can switch tiers before the trial ends.

## The full plan table

Here are all seven paid plans as currently listed on the official pricing page, with the annual figures reflecting the 10% discount:

| Plan | Monthly | Annual (per mo) | API Credits | Threads | Sign Up |
| --- | --- | --- | --- | --- | --- |
| Hobby | $49 | $44.10 | 100,000 | 20 | [Start Hobby](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [Start Startup](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [Start Business](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Scaling (Most Popular) | $475 | $427.50 | 5,000,000 | 200 | [Start Scaling](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [Start Professional](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [Start Advanced](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22M+ | 500+ | [Contact Sales](https://www.scraperapi.com/contact-sales/?fp_ref=coupons) |

Every plan — including Hobby — includes JavaScript rendering, premium residential and mobile IPs, rotating proxy pools, CAPTCHA and anti-bot bypassing, JSON auto-parsing, custom headers and sessions, automatic retries, unlimited bandwidth, and a 99.9% uptime guarantee. You're choosing between volume, concurrency, and geotargeting reach, not between feature tiers.

There are also two free options: a 7-day trial with 5,000 API credits (up to 5 concurrent connections, no credit card), and a permanent free plan with 1,000 credits. The free plan is fine for experiments; it won't survive a production workload.

## What a "credit" actually buys

ScraperAPI doesn't bill per request. It bills per credit, and one request can cost anywhere from 1 to 25 credits depending on the target site and the parameters you send. This is where most pricing comparisons fall apart, because the headline credit number and your real page count are usually very different.

The baseline costs:

| Request Type | Credits Per Request |
| --- | --- |
| Standard HTML page | 1 |
| JavaScript rendering (`render=true`) | 10 |
| Premium residential proxies | 10 |
| Ultra-premium proxies | 25 |
| Cloudflare / Datadome / PerimeterX bypass | +10 on top |

Hard domains have their own fixed pricing: Amazon costs 5 credits per page, Google and Bing cost 25 (including subdomains), LinkedIn costs 30. If your target site sits behind bot protection, add 10 credits per request on top of everything else. The full domain cost list is in ScraperAPI's docs, and the dashboard's Domain Cost Estimator shows the exact credit cost for any URL before you scrape it.

Without any add-ons, Hobby's 100,000 credits translate to 100,000 standard pages, 20,000 Amazon product pages at 5 credits each, or 4,000 Google searches at 25 credits each. The multiplier stack is what shrinks those numbers: turn on JavaScript rendering and each request burns 10 credits, so the same balance covers about 10,000 rendered pages. Stack rendering and premium proxies together and a single request can consume 10–25 credits — enough to run through Hobby's entire allocation in far fewer sessions than the headline suggests.

One more safeguard worth knowing: the `max_cost` parameter caps how many credits a single request can consume, so a misconfigured loop can't silently drain your monthly pool. And failed requests don't cost credits — you only pay for successful responses.

## The limits that don't make the headline

Three restrictions materially affect which plan you should pick, and they're easy to miss when comparing plans side by side.

**Geotargeting.** Hobby and Startup only support US and EU locations. If you need to scrape from Asia-Pacific, LATAM, or any other specific country, Business ($299/mo) is the minimum tier — it unlocks country-level targeting across 50+ countries.

**Analytics history.** Hobby and Startup keep your dashboard analytics for 30 days only. Business and above give you unlimited history, which matters if you audit usage trends or need to reconcile credit burn across months.

**Overage behavior.** When credits run out, scraping pauses by default until renewal. What happens next depends on your tier:

- **Hobby, Startup, Business, Scaling, Professional** can enable auto-upgrade: when credits hit zero, your account moves to the next plan automatically.
- **Scaling, Professional, Advanced, Enterprise** can use pay-as-you-go instead: keep scraping at a fixed per-credit rate, up to a monthly spending cap you set yourself.

Concurrency works differently. Exceeding your thread limit returns a 429 response and the request is simply turned away — no extra charge, no queueing. Hobby's 20 threads get slow fast on batch jobs, which is one reason the plan fits solo projects better than time-sensitive monitoring.

Annual plans have one more trick: you can renew early to grab a fresh batch of credits instead of waiting for the billing cycle.

## Which plan for which job

The tiers map cleanly onto workload types:

1. **Testing or a low-volume side project** — start with the free trial, then Hobby at $49 if it fits. Fine for single-target daily scraping.
2. **Small team, regular monitoring** — Startup at $149. Ten times Hobby's credits and 2.5x the concurrency for 3x the price.
3. **Production workflow needing global geotargeting** — Business at $299 is the entry point. 3M credits comfortably covers around 30K requests/day for standard pages.
4. **Variable volume that spikes unpredictably** — Scaling at $475. It's the plan ScraperAPI itself labels most popular, and the pay-as-you-go overage alone justifies the jump from Business.
5. **High-volume infrastructure** — Professional ($975) or Advanced ($1,975), which adds priority routing so your requests jump the queue.
6. **22M+ requests/month** — talk to sales for custom Enterprise pricing.

👉 [Start a free trial and test your real targets](https://www.scraperapi.com/signup?fp_ref=coupons) before committing — 5,000 credits is enough to run the Domain Cost Estimator across your target list and see the true per-page price.

## How it compares on entry price

The credit-multiplier logic isn't unique to ScraperAPI; every major competitor uses some version of it. The entry tiers, for reference:

- **ScrapingBee** starts at $49/month with 150,000 credits, plus a 1,000-credit free trial. It's generally considered strong for rendering and screenshot jobs.
- **ZenRows** starts at $69/month with 250,000 credits, plus a 1,000-credit free trial.
- **Bright Data** sits at the enterprise end with entry plans around $499/month — out of reach for small teams.
- **Apify** bills by compute units and is structurally a workflow platform rather than a pure scraping API.

Two practical notes that apply across all of these: free trials throttle concurrency to 1–5 requests, so burst-testing on a trial understates production capability; and geo-targeted requests outside default US/EU regions cost extra credits on every major vendor, with some geos multiplying per-request cost several times over.

Where ScraperAPI separates itself is predictability and the free trial. Its 5,000-credit trial is five times what ZenRows or ScrapingBee give you — enough to actually measure your own credit burn instead of guessing from someone else's benchmarks.

## FAQ

**Does ScraperAPI have a free plan?**
Yes. A permanent free plan gives 1,000 API credits with up to 5 concurrent connections, and you can request more testing credits from support. Separately, every new account gets a 7-day trial with 5,000 credits and no credit card required.

**Do failed requests cost credits?**
No. Credits are only consumed for successful responses, which takes some of the risk out of scraping volatile targets.

**Is the annual discount worth it?**
Annual billing takes 10% off every plan — Hobby drops from $49 to $44.10/month and Business from $299 to $269.10/month. That works out to roughly $59 and $360 saved over a year respectively. If you're committed for more than a couple of months, annual wins, and you can renew early to reset your credit pool ahead of the normal cycle.

**How do I know my real cost per page before subscribing?**
Sign up for the trial, run your actual target URLs through the Domain Cost Estimator in the dashboard, and check whether they trigger the +10-credit anti-bot surcharge. That single check converts the pricing table into a real monthly estimate for your workload.

**What happens if I go over my plan?**
Concurrency overages return a 429 and cost nothing. Credit overages pause scraping unless you've enabled auto-upgrade (Hobby through Professional) or pay-as-you-go with a self-set monthly cap (Scaling and above).

## Before you commit

Three things to verify with your own numbers, in this order:

- **Run your top five target URLs through the trial first.** If two of them turn out to be 25-credit Google or 30-credit LinkedIn targets, your Hobby plan estimate just shrank accordingly — and the fix might be as simple as choosing structured data endpoints instead of raw scraping.
- **Check where your targets are located.** If any of them need non-US/EU geos, start your comparison at Business ($299) — Hobby and Startup can't serve those requests at any volume.
- **Set a `max_cost` on every request from day one.** It's the cheapest insurance against a runaway loop burning your monthly credits in an afternoon.

The decision itself is short: under ~100K standard pages a month on US/EU targets, Hobby at $49 does the job; regular commercial scraping goes to Startup; anything global or production-grade starts at Business and scales up through the pay-as-you-go tiers. 👉 [Compare all plans and start your 5,000-credit free trial](https://www.scraperapi.com/pricing/?fp_ref=coupons) — the trial costs nothing, and it's the only benchmark that matters for your specific target list.
