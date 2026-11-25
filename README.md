# Is ScraperAPI Worth It? $49 Buys 100,000 Requests or 1,333 — Credit Multipliers, Every Plan Price, and Measured Success Rates (Plus Who Should Skip It)

ScraperAPI starts at $49/month for 100,000 credits, and a credit is not a request. On a plain HTML page that's 100,000 pages. On Amazon with JavaScript rendering it's about 6,667. On a bot-protected site with ultra-premium proxies and rendering turned on, roughly 1,333. Whether it's worth the money comes down to two things you can check before paying: which domains you scrape, and whether those pages need rendering.

The rest of this article is the arithmetic behind those numbers, every plan on the pricing page, the October 2026 third-party benchmark, and the limits that only appear in the documentation. ScraperAPI was founded in 2018, runs a pool of 40M+ IPs across 50+ countries, advertises a 99.9% uptime SLA, and claims about 36 billion API requests a month for 10,000+ brands. None of that tells you whether your $49 is well spent. The credit table does.

> **Quick pick:** solo developers and small teams usually start on **Hobby ($49/mo, 100,000 credits, 20 threads)** and stay there while targets are ordinary HTML or light e-commerce. If Amazon, Google, or JS rendering is central to the job, **Startup ($149/mo, 1,000,000 credits, 50 threads)** is the first tier where the per-page cost stops being painful. Country-level geotargeting outside the US and EU starts at **Business ($299/mo)**; pay-as-you-go overflow starts at **Scaling ($475/mo)**.
> 👉 [Compare current ScraperAPI plans and start the 7-day trial](https://www.scraperapi.com/?fp_ref=coupons)

## Every ScraperAPI plan and what it costs

The pricing page has nine tiers, including free and education. Annual billing takes exactly 10% off every paid tier and is applied at checkout without a code. The monthly column below shows what you pay month to month; the second number is the effective monthly rate on annual billing.

| Plan | Price per month (annual) | Credits per month | Concurrent threads | What changes at this tier | Sign up |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | 1,000 | 5 | Full feature set, no card required | [Start free](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 ($44.10) | 100,000 | 20 | US and EU proxies only, 30-day analytics | [Get Hobby](https://www.scraperapi.com/?fp_ref=coupons) |
| Startup | $149 ($134.10) | 1,000,000 | 50 | Same geo limits, 10x the volume | [Get Startup](https://www.scraperapi.com/?fp_ref=coupons) |
| Business | $299 ($269.10) | 3,000,000 | 100 | Country-level geotargeting, unlimited analytics | [Get Business](https://www.scraperapi.com/?fp_ref=coupons) |
| Scaling | $475 ($427.50) | 5,000,000 | 200 | Pay-as-you-go overflow switches on | [Get Scaling](https://www.scraperapi.com/?fp_ref=coupons) |
| Professional | $975 ($877.50) | 10,500,000 | 300 | Priority support | [Get Professional](https://www.scraperapi.com/?fp_ref=coupons) |
| Advanced | $1,975 ($1,777.50) | 21,500,000 | 500 | Priority routing | [Get Advanced](https://www.scraperapi.com/?fp_ref=coupons) |
| Enterprise | Custom quote | 22,000,000+ | 500+ | Dedicated team, Slack support | [Request Enterprise pricing](https://www.scraperapi.com/?fp_ref=coupons) |
| Education | $10 one-time | 50,000 (valid 24 months) | 25 | Universities, NGOs, public bodies | [Apply for the Education plan](https://www.scraperapi.com/?fp_ref=coupons) |

Three details sit outside the table. New accounts get 5,000 credits for 7 days with no card, then drop to the free plan's 1,000 credits a month. Every plan carries a 7-day, no-questions-asked refund. Credits reset at renewal and unused ones are lost, so buying headroom "just in case" is a donation.

## What a credit actually costs: two multipliers, one of them automatic

ScraperAPI applies credits at two separate layers. The domain multiplier fires on its own the moment a request goes to a known site. Feature multipliers only apply when you add the parameter yourself.

**Domain multiplier (automatic, not optional):**

| Target | Credits per request |
| --- | --- |
| Standard HTML page | 1 |
| Amazon, Walmart, eBay | 5 |
| Google, Bing, including subdomains | 25 |
| LinkedIn | 30 |
| Any site behind Cloudflare, DataDome, PerimeterX/HUMAN or Akamai, when bypass kicks in | +10 |

**Feature parameters (you opt in):**

| Parameter | Extra credits |
| --- | --- |
| `render=true` (JS rendering) | +10 |
| `screenshot=true` | +10 |
| `premium=true` (premium proxies) | +10 |
| `ultra_premium=true` (paid plans only) | +30 |

The part that catches people is that premium proxies and rendering don't add up the way you'd expect. `premium=true` plus `render=true` costs **25 credits, not 20**. `ultra_premium=true` plus `render=true` costs **75 credits, not 40** — nearly double the naive sum. Both rules are documented, and both are buried deep enough that most buyers find them after the invoice.

There's a real case of the gap in the wild: a Reddit user reported being quoted 60 million credits at one credit per Amazon request, paying, and then discovering the 5x domain multiplier applied, which cut the purchased capacity by 80%. That's the same failure mode as assuming 100,000 credits means 100,000 pages.

## How many pages $49 really buys

Same 100,000-credit Hobby plan, six different jobs:

| What you're scraping | Credits per request | Real pages from 100,000 credits |
| --- | --- | --- |
| Plain HTML | 1 | 100,000 |
| Amazon, no rendering | 5 | 20,000 |
| Amazon with JS rendering | 15 | ~6,667 |
| Google SERP | 25 | 4,000 |
| LinkedIn with JS and premium proxies | ~55 | ~1,818 |
| Bot-protected site, ultra-premium plus rendering | 75 | ~1,333 |

Convert that into cost per 1,000 successful requests and the tier structure makes sense:

| Plan | Plain HTML | JS rendering | E-commerce | SERP | Ultra-premium + JS |
| --- | --- | --- | --- | --- | --- |
| Hobby $49 | $0.49 | $4.90 | $2.45 | $12.25 | $36.75 |
| Startup $149 | $0.15 | $1.49 | $0.75 | $3.73 | $11.18 |
| Business $299 | $0.10 | $1.00 | $0.50 | $2.49 | $7.48 |
| Scaling $475 | $0.10 | $0.95 | $0.48 | $2.38 | $7.13 |

Two conclusions follow. On plain HTML the Hobby plan is genuinely cheap at $0.49 per thousand and Business at $0.10 is competitive with almost anything. On protected sites with rendering, Hobby costs $36.75 per thousand, which is more than most fully managed scraping services charge for the same pages. If your project is heavy on JS rendering or anti-bot bypass, the entry plan is the wrong plan; the cost curve only flattens from Startup upward, and barely moves past Scaling.

One more cost decision worth doing explicitly: structured data endpoints. Amazon has 3 endpoints, Google 5, Walmart 4, eBay 2, Redfin 4, and they're available on every plan including free. They parse the page for you. Scraping 10,000 Amazon products through the SDE on Business consumes 50,000 credits, about $5 of plan value; a hand-built parser using plain requests consumes 10,000 credits but costs you development and maintenance time. At low volume the SDE is the better trade; at high volume the parser wins.

👉 [Run your own URLs against the 5,000-credit trial before choosing a tier](https://www.scraperapi.com/?fp_ref=coupons)

## Measured performance: 60.1% success across 11 targets

Scrapeway's benchmark covering 1 October to 1 November 2026 put ScraperAPI at a **60.1% overall success rate**, **10.6 seconds** average response, and **$5.81 per 1,000 requests** across 11 targets. That ranked fifth of six tested APIs. The same batch's industry averages were 72.3% success, 11.8 seconds, and $3.88 per thousand, so ScraperAPI was faster than average, less reliable than average, and more expensive than average on this mix.

Per-target results explain the average better than the headline does:

| Target | Success | Avg. response | Cost per 1,000 |
| --- | --- | --- | --- |
| Zillow | 100% | 5.9s | $0.49 |
| Etsy | 96% | 8.7s | $4.90 |
| Amazon | 94% | 5.0s | $2.45 |
| Walmart | 89% | 5.2s | $2.45 |
| LinkedIn | 89% | 19.0s | $14.70 |
| Booking.com | 47% | 37.1s | $18.58 |
| Indeed | 41% | 25.4s | $9.80 |
| StockX | 37% | 12.9s | $12.29 |
| Realtor.com | 37% | 3.7s | $0.49 |
| Twitter/X | 0% | — | — |
| Instagram | 0% | — | — |

The pattern is sharp. Mainstream e-commerce and real estate listings work well and cheaply. Job boards, travel, sneaker resale, and social platforms fall apart, and the failures are expensive because LinkedIn and Booking still bill at high multipliers.

An earlier Scrapeway run from April 2026 gave ScraperAPI 62–64% overall against an industry average of 58–60%, with response times of 5–7 seconds. That's a very different picture from the October numbers, and Booking.com scored 0% in April versus 47% in October. Benchmarks on a fixed target list drift with site changes and test conditions, so treat any single number as a prior rather than a verdict. The safe reading: ScraperAPI is stable on mainstream Western e-commerce and property sites, unreliable on social and several travel/job targets, and worth testing on your own domains before committing a month.

## Limits that only show up in the documentation

**Country-level geotargeting is gated at $299.** Hobby and Startup are restricted to US and EU proxies. If your project needs to appear as a Brazilian or Japanese visitor, Business is the floor.

**Pay-as-you-go starts at Scaling.** Exceed your credits on Hobby, Startup, or Business and scraping pauses until renewal, with the choice of upgrading or waiting. Only Scaling and above can overflow at a fixed per-credit rate up to a cap you set. Auto-upgrade exists as an opt-in on the lower tiers, which means an unexpected bill rather than a stopped job.

**No usage alerts.** There is no email or SMS when credits run low. You watch the dashboard or you find out mid-month.

**A forced 10-minute cache on hard targets.** When ScraperAPI decides a site is difficult, results are cached for up to 10 minutes. For price monitoring or stock checks, that's stale data by design.

**Login walls are off-limits.** The `session_number` parameter holds the same IP for about 15 minutes, which is useful for multi-step page flows. It doesn't extend to form filling, two-factor authentication, or scraping anything behind a login; the terms prohibit it.

**Concurrency limits reject rather than queue.** Go past your thread count and you get a 429. No extra charge, but no retry either.

**Analytics history is 30 days on Hobby and Startup**, unlimited from Business.

The dashboard's Domain Cost Estimator is the authoritative way to price a specific URL, and `max_cost` lets you cap what a single request is allowed to consume. Both are worth using before you size a plan.

## What users actually complain about

Aggregate ratings are decent: G2 4.4/5 across 16 reviews, Capterra 4.6/5 across 62, Trustpilot 4.5/5 across 43. Capterra's sub-scores show ease of use at 4.9/5, support at 4.6, features and value at 4.5 each.

Positive reviews cluster around integration speed (a URL parameter added to existing code, live in minutes), clear documentation, reliability on Amazon, Google and Zillow, responsive support, and billing only for successful requests. Negative reviews cluster almost entirely around the credit system rather than the proxy infrastructure. One Capterra reviewer wrote "Breakdown of credit costs can be confusing," which is the polite version. Others describe pricing surprises at scale and shakier results on heavy-duty targets. There's no proactive spend warning, so the first signal of trouble is usually a stopped job.

## When ScraperAPI is the wrong purchase

It's infrastructure, not a platform. There are no pre-built crawlers, no hosted code execution, no dataset storage, no scheduling engine in the base product, and no workflow automation. If you don't already have scraping code, you're buying an engine without a car.

A few situations where another tool fits better, with prices as published:

| Provider | Better fit when | Published entry point | Notable difference |
| --- | --- | --- | --- |
| Apify | You want ready-made scrapers, storage, and scheduling | $29/mo | 19,000+ pre-built Actors, full platform |
| Bright Data | Enterprise compliance, maximum success rates | ~$499+/mo | Flat rate regardless of JS rendering, fine proxy granularity |
| ScrapingBee | You want predictable cost per request | $49/mo | No non-linear multiplier stacking |
| Scrapfly | JS-heavy sites at volume | $49/mo | 95% success at $3.75/1k in the October benchmark, but 16.3s average |
| ZenRows | Protected sites with unified pricing | ~$300/mo equivalent | Flat pricing, higher entry cost |
| Firecrawl | Fast responses matter more than breadth | — | 81% success at 5.2s and $2.70/1k in the same test |

Social platforms are a hard no regardless of provider choice here: Instagram and Twitter/X returned 0% in October. Login-gated data is explicitly out of scope. And if you need country-level geotargeting on a $49 budget, the product simply doesn't sell that to you.

## FAQ

**Does ScraperAPI have a free trial?**
Yes. New accounts get 5,000 credits over 7 days with no credit card. After that you fall to the free plan: 1,000 credits and 5 concurrent threads per month. Both cover the full feature set, so a trial run on your real targets costs nothing but time.

**How many credits does one Amazon request use?**
5 for a standard product request. Add `render=true` and it becomes 15. Add `premium=true` and `render=true` together and it's 25, not 20, because those two stack non-linearly.

**Do unused credits roll over?**
No. They reset at each renewal date and are lost. Size the plan to your measured monthly volume rather than to a worst case.

**Can I scrape Instagram or Twitter/X with it?**
Both scored 0% in the October 2026 benchmark. It isn't a product limitation you can pay your way out of.

**Is $49/month enough to start?**
For plain HTML pages, comfortably: 100,000 requests at $0.49 per thousand. For Amazon with rendering, it's about 6,600 pages, and for ultra-premium protected pages about 1,300. If your targets land in the second or third bucket, budget for Startup.

## How to decide

Match the plan to the job rather than to the credit number:

- Plain HTML or light e-commerce under roughly 80,000 requests a month → **Hobby, $49**.
- Amazon, Google, or JS rendering as a core workload → **Startup, $149**. The per-page cost drops by two-thirds and the volume ceiling moves tenfold.
- You need to look like a visitor from outside the US or EU, or you need unlimited analytics → **Business, $299**. There's no cheaper path to country-level targeting.
- You can't afford to be hard-stopped mid-month → **Scaling, $475**, the first tier with pay-as-you-go overflow.

Two things to confirm before you pay. Run your five or six hardest URLs through the 5,000-credit trial and read the Domain Cost Estimator output for each one; that tells you the real credits per page instead of the advertised 100,000. Then check whether your geotargeting needs go beyond the US and EU, because that single requirement moves the floor from $49 to $299.

Everything else is refundable within 7 days, credits don't carry over, and annual billing takes 10% off whenever you're ready to commit.

👉 [Start the ScraperAPI free trial and price your own targets](https://www.scraperapi.com/?fp_ref=coupons)
