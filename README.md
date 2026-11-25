# ScraperAPI Free Trial: How Far Do 5,000 Credits Get You, What Do the Limits Cost You Later, and Which Plan Do You Actually Need? (Full Pricing Table)

ScraperAPI's free trial runs 7 days, comes with 5,000 API credits, and asks for no credit card. Those 5,000 credits are not 5,000 requests to any site you point them at: a Google or Bing query costs 25 credits, so the trial covers 200 searches. A plain blog page costs 1 credit, which stretches the same allowance to 5,000 pages.

The gap between those two numbers is the thing most trial write-ups skip. Below you'll find the per-domain math, the three limits that quietly drain a trial balance, the full seven-tier price list, and a rule for each common workload so you can pick a paid plan without guessing.

> **Quick answer.** Testing whether ScraperAPI gets through your target sites? Open the trial first, pay nothing, and run your real URLs through it. Already know you're buying and scraping ordinary pages? Hobby at $49/month for 100,000 credits is the entry point. Country-level geotargeting outside the US and EU starts at Business ($299/month); pay-as-you-go overage starts at Scaling ($475/month).
>
> 👉 [Start the ScraperAPI free trial with 5,000 credits](https://www.scraperapi.com/signup?fp_ref=coupons)

## Every ScraperAPI plan on one table

ScraperAPI lists a free plan alongside seven paid tiers. Credits and concurrency are what separate them; the feature set is largely shared across the board, including JS rendering, premium residential and mobile IPs, anti-bot bypass and JSON autoparse.

| Plan | Monthly (USD) | Annual, effective monthly (billed annually) | Credits per month | Concurrent threads | Sign up |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | [ Create a free account](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [ Hobby at $49/mo](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [ Startup at $149/mo](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [ Business at $299/mo](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [ Scaling at $475/mo](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [ Professional at $975/mo](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [ Advanced at $1,975/mo](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [ Request an Enterprise quote](https://www.scraperapi.com/signup?fp_ref=coupons) |

Three parameters don't fit in that grid without making it unreadable on a phone, so they get their own table:

| Plan | Geotargeting | Analytics history | Pay as you go |
| --- | --- | --- | --- |
| Free | — | — | No |
| Hobby | US & EU only | Up to 30 days | No |
| Startup | US & EU only | Up to 30 days | No |
| Business | Country-level, global | Unlimited | No |
| Scaling | Country-level, global | Unlimited | Yes |
| Professional | Country-level, global | Unlimited | Yes |
| Advanced | Country-level, global | Unlimited | Yes |
| Enterprise | Country-level, global | Unlimited | Yes |

Annual billing is exactly 10% off the monthly rate, which is why the second column shows prices like $44.10 rather than a round number. Plans can be upgraded or downgraded at any time from the billing dashboard.

## What 5,000 trial credits actually buy

ScraperAPI bills per request, and the per-request cost depends on the domain. Standard pages cost 1 credit, Amazon and all Amazon domains cost 5, Google and Bing including subdomains cost 25, and LinkedIn costs 30. On top of that, pages protected by Cloudflare, DataDome or PerimeterX add 10 credits whenever ScraperAPI activates bypass logic. That surcharge is applied automatically; you don't request it.

Run the trial allowance through those multipliers:

| Target | Credits per request | Requests covered by 5,000 credits |
| --- | --- | --- |
| Standard page | 1 | 5,000 |
| Amazon product page | 5 | 1,000 |
| Google or Bing results page | 25 | 200 |
| LinkedIn page | 30 | ~166 |
| Standard page behind Cloudflare/DataDome/PerimeterX | 11 (1 + 10) | ~454 |

The same multipliers apply to paid plans, and they scale linearly. Hobby's 100,000 credits buy 20,000 Amazon product pages a month; Scaling's 5,000,000 credits buy 1,000,000 of them. Two tools keep this from becoming guesswork: the Domain Cost Estimator in the dashboard returns the exact credit cost for any URL before you commit, and the `max_cost` parameter caps what a single request is allowed to spend.

If your trial plan is "point it at a few hundred product URLs and see what works," the estimator is the first thing to open. It tells you within a minute whether 5,000 credits is a comfortable test or a single afternoon.

## Three limits that eat a trial balance faster than expected

**The anti-bot surcharge can multiply a request's cost.** A protected page at 11 credits is eleven times the price of the same page unprotected. Work out partway through a crawl that half your targets sit behind Cloudflare and the trial allowance disappears roughly twice as fast as planned. Check a sample of URLs for protection status before you queue thousands of them.

**Trial credits are perishable.** All 5,000 credits have to be used inside the 7-day window. Monthly paid plans work the same way: unused credits are lost at each renewal date and don't carry forward. A generous allowance on paper is worth nothing if your scraper isn't ready to run during the window, so build the request first and sign up second.

**Concurrency is a hard ceiling, and it doesn't queue.** Send more simultaneous requests than your plan's thread limit and the excess come back as 429 responses. They are turned away rather than held, and there's no extra charge for hitting the limit. The free plan allows 5 concurrent connections; Hobby allows 20, Startup 50, Business 100, Scaling 200, and the top tiers 300 to 500+. A crawler built to fire 50 parallel workers will look broken on Hobby until you dial the pool down.

## Picking a paid plan after the trial

The trial's real job is to tell you two things: your true credit cost per target and your realistic monthly volume. Multiply the first by the second and the tier usually picks itself.

| Plan | Credits per month | Price per 1,000 credits |
| --- | --- | --- |
| Hobby | 100,000 | $0.49 |
| Startup | 1,000,000 | $0.149 |
| Business | 3,000,000 | ~$0.0997 |
| Scaling | 5,000,000 | $0.095 |
| Professional | 10,500,000 | ~$0.0929 |
| Advanced | 21,500,000 | ~$0.0919 |

- **Under about 1,000 plain pages a month:** the free plan's 1,000 credits and 5 concurrent connections cover it at no cost.
- **Amazon or other 5-credit domains at modest volume:** Hobby. 100,000 credits ÷ 5 = 20,000 Amazon pages a month, which is more headroom than most side projects need.
- **You need geotargeting outside the US and EU:** Business is the floor. Hobby and Startup are restricted to US and EU locations and there's no workaround at those tiers.
- **You need scraping to keep running after credits run out:** Scaling at $475/month. Pay-as-you-go, billed per credit against a monthly spending cap you set, is only available on Scaling, Professional, Advanced and Enterprise.
- **Your volume is between 1M and 3M credits:** Hobby to Startup is the steepest efficiency jump on the list, three times the price for ten times the credits. Past Business, the unit price flattens out and you're paying for volume rather than a discount.

One thing worth knowing before you scale: on Hobby, Startup and Business, credits running out means requests get a 429, not an automatic overage charge. You can switch on auto-upgrade to move to the next tier when the allowance is exhausted; without it, scraping pauses until the next renewal.

👉 [Compare the plan tiers and start with the one you need](https://www.scraperapi.com/pricing?fp_ref=coupons)

## Is annual billing worth committing to?

The discount is exactly 10%, applied to the same credit allowance. Over twelve months the difference is real money but not transformative:

| Plan | Monthly billing, 12 months | Annual billing, 12 months | Saved |
| --- | --- | --- | --- |
| Hobby | $588.00 | $529.20 | $58.80 |
| Startup | $1,788.00 | $1,609.20 | $178.80 |
| Business | $3,588.00 | $3,229.20 | $358.80 |
| Scaling | $5,700.00 | $5,130.00 | $570.00 |
| Professional | $11,700.00 | $10,530.00 | $1,170.00 |
| Advanced | $23,700.00 | $21,330.00 | $2,370.00 |

Annual plans handle credits differently from monthly ones. You get the full year's allowance upfront and can spend it on any timeline, and if you burn through it before the billing period ends you can renew the same annual plan early for a fresh allocation. A monthly plan, by contrast, resets on each renewal date with nothing carried over. If your scraping is seasonal or front-loaded, the annual structure fits better than the 10% suggests.

The backstop on either option is a 7-day no-questions-asked refund, available if the service doesn't work out for any reason. Cancelling is free and can be done from the dashboard at any time. The trial window and the refund window are both seven days, which gives you one free evaluation before you pay and a second exit after.

👉 [See current pricing before you choose monthly or annual](https://www.scraperapi.com/pricing?fp_ref=coupons)

## FAQ

**Does the free trial require a credit card?**
No. ScraperAPI's trial is 7 days with 5,000 API credits and no card requirement at signup.

**Do the 5,000 trial credits stack on top of the free plan's 1,000?**
ScraperAPI's documentation only states that the first 7 days after signup come with 5,000 credits, and separately that the free plan includes 1,000 credits per month. Nothing official describes the two combining, so treat 5,000 as the trial figure and ask support if the exact account balance matters to your plan.

**What happens when the 7-day window closes?**
The documentation covers the trial period and the free plan but doesn't spell out the transition between them. Since no card is required to start, confirm the account state with support if you need certainty before signing up.

**Will I be charged automatically if I exceed my credits?**
Not on Hobby, Startup or Business. Requests beyond the allowance return a 429 and no overage is billed. Those tiers can enable auto-upgrade, which moves you to the next plan when credits run out; without it, scraping pauses until renewal. On Scaling and above, pay-as-you-go continues at a fixed per-credit rate up to a spending cap you set in the dashboard. That cap is a limit, not an amount charged in advance.

**Do annual credits reset every month?**
No. Annual plans deliver the full year's credits upfront for you to use on any schedule. Monthly plans reset at each renewal date, and unused credits are lost.

**Can I cancel or downgrade later?**
Yes. Plans can be changed from the billing dashboard at any time, and cancelling carries no charge.

## Two checks before you pay

Run a handful of your real target URLs through the Domain Cost Estimator during the trial. The trial tells you whether ScraperAPI gets through; the estimator tells you what each success actually costs, and those are different questions. A site that works at 11 credits per page changes your monthly bill by an order of magnitude compared with one that works at 1.

Then settle the geotargeting question. If your work needs locations outside the US and EU, the decision is made for you at Business, and no amount of credit math on Hobby will substitute for it. If US and EU coverage is enough, Hobby at $49 for 100,000 credits handles a surprising amount of Amazon and standard-page volume.

👉 [Open the ScraperAPI free trial and test your own targets](https://www.scraperapi.com/signup?fp_ref=coupons)
