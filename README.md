# ScraperAPI Coupon Code: Which Codes Still Work, How Much They Really Save, and Why 100,000 Credits Isn't 100,000 Requests (Full Plan Comparison)

The realistic ceiling on a ScraperAPI coupon code is **10% off your first month**. That's what the company's own promo documentation has said since 2021, what SimplyCodes has tracked as the 90-day discount ceiling, and what the codes still circulating on coupon sites and GitHub guides all resolve to once you get to the checkout field.

There's a second 10% that requires no code at all. Switch the billing toggle to annual and every standard plan drops by 10%, which takes Hobby from $49/month to **$44.10/month**. That discount repeats on every renewal for the life of the subscription, while a first-month code touches exactly one invoice.

Below is the full plan table with annual pricing, the credit multiplier table that decides whether a $49 plan covers 100,000 pages or 3,333, the codes worth typing at checkout, and the cases where ScraperAPI is the wrong purchase regardless of the discount.

> **Most readers should land on Hobby** — $49/month, or $44.10/month billed annually, for 100,000 credits and 20 concurrent threads. Run the 7-day trial (5,000 credits, no credit card) against your real target URLs before paying, then flip the annual toggle.
> 👉 [Compare ScraperAPI plans and start the 5,000-credit trial](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Every ScraperAPI plan and what the annual toggle does to it

ScraperAPI's pricing page currently lists eight tiers, from a permanent free plan to custom Enterprise. The monthly and annual columns below come from that pricing page; the Hobby figures are independently confirmed by SimplyCodes' tracking.

| Plan | Monthly | Annual (per month) | Credits/month | Threads | Get it |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | [ Start on the free plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [ Get Hobby](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [ Get Startup](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [ Get Business](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [ Get Scaling](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [ Get Professional](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [ Get Advanced](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22M+ | 500+ | [ Request Enterprise pricing](https://www.scraperapi.com/?fp_ref=coupons) |

Three limits sit in the fine print and change which tier makes sense:

- **Credits never roll over.** Whatever is left at renewal is wiped, so buying a bigger plan than you need is a straight loss.
- **Pay-as-you-go overage starts at Scaling.** On Free, Hobby, Startup and Business, running out means 429 responses and waiting for renewal (or opting into auto-upgrade); only Scaling and above let you keep scraping past the limit at a fixed per-credit rate up to a cap you set.
- **Country-level geotargeting starts at Business.** Hobby and Startup get US and EU proxies only. If your project needs Brazil, Japan or India at the country level, the entry tiers can't do it. Analytics history splits the same way: 30 days on Hobby and Startup, unlimited from Business up.

## Why 100,000 credits isn't 100,000 requests

This is the part almost no coupon page explains, and it's the difference between a plan that fits and one that bills you twice in a month.

A standard HTML page costs 1 credit. Everything else scales from there:

| Request type | Credits per request |
| --- | --- |
| Standard page | 1 |
| Amazon / Walmart / eBay | 5 |
| Google / Bing SERP | 25 |
| LinkedIn | 30 |
| Bot-protection bypass (Cloudflare, DataDome, PerimeterX, Akamai) | +10 |
| `render=true` (JS rendering) | 10 |
| `premium=true` (premium proxies) | 10 |
| `screenshot=true` | 10 |
| `premium=true` + `render=true` | **25** |
| `ultra_premium=true` | 30 |
| `ultra_premium=true` + `render=true` | **75** |

The stacking isn't additive, which is where budgets break. Premium proxies plus rendering costs 25 credits, not the 20 you'd get by adding the two line items, and ultra premium plus rendering costs 75 rather than 40. ScraperAPI does expose the cost before you spend it: every response carries a `sa-credit-cost` header, the dashboard has a Domain Cost Estimator, and you can set `max_cost` per scrape to cap a single request.

Run the arithmetic on a real job. Scraping Amazon product pages with premium proxies and rendering costs 5 (Amazon) + 25 (premium + render) = **30 credits per request**, so Hobby's 100,000 credits covers roughly **3,333 product pages**, not 100,000. Push everything through JS rendering on ordinary sites and Hobby gives you 10,000 renders. A workload that needs ultra premium plus rendering burns 75 credits a request, which puts Hobby at about 1,333 requests.

That math also tells you when the multiplier is worth paying. Amazon's structured data endpoint returns 18+ fields including price, reviews, BSR and images at a 98% success rate, Zillow 100%, Etsy 99%, Walmart 93%. Five credits for a parsed record beats one credit for raw HTML you then have to parse and maintain yourself.

## Which ScraperAPI coupon codes are worth typing at checkout

Start with the official one. ScraperAPI's own site documents **START10** for 10% off the first month, usable at signup or from the dashboard, and that page has been live since May 2021 without a change in terms.

The codes posted across coupon aggregators and GitHub guides are variations on the same 10%:

- **START10** — first month, new users.
- **DATALOVER** — reported working across subscription plans, not only the first month.
- **FSCRAP1** — pricing plans, but requires a new account created through the partner link, or it won't activate.
- ANWAR10, TART10, TENERE10, BOOM10 and similar — first-month codes with different names. Forums advertise BOOM10 at up to 30%; reports land at 10%.

Bigger numbers are where these lists go stale. One aggregator page, updated October 23, 2026, still listed a 70%-off code alongside headlines for 60% off geotargeting, 50% off headless rendering and 45% off e-commerce scraping. Every expiry date on that page fell between October 24 and October 29, 2026. They're all in the past now, and the page rates its own inventory "moderate chance of a working code."

SimplyCodes updates daily and, on November 9, 2026, tracked two verified codes, both at 10%, with three separate users reporting that codes failed the same day. Even a genuine 10% code can bounce, which is why the practical move is to paste two or three into the field and keep the one that changes the total.

The checkout sequence that works:

1. Create the account through the promotional link first. Codes like FSCRAP1 only activate on a fresh account.
2. Pick your plan on the pricing page.
3. Decide monthly or annual. The annual toggle applies its 10% automatically and needs no code.
4. Open the checkout and find the field labeled **Promo Code** or **Discount Code**.
5. Paste the code and hit Apply.
6. Confirm the total actually dropped before you submit payment. Ineligible codes are rejected silently, and the only symptom is an unchanged price.

👉 [Lock in the annual 10% on Hobby or any other tier](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Annual billing or a first-month code: which one actually saves more

Annual billing is the only discount with no conditions attached. Over twelve months it takes $59 off Hobby ($588 versus $529.20), $179 off Startup, $359 off Business, $570 off Scaling, $1,170 off Professional and $2,370 off Advanced. No code, no expiry, no new-account requirement.

A first-month code cuts one invoice by 10% and then disappears. On Hobby that's about $4.90 once.

Some guides claim the two stack, with Hobby landing near **$39.69/month for the first year** ($44.10 minus another 10%, roughly $476 for twelve months instead of $529.20). Treat that as an estimate rather than a rule. SimplyCodes notes that both discounts sit in the same 10% band and suggests testing at checkout to see which path produces the lower total, and codes are commonly rejected when the billing cycle or plan doesn't match what the code expects. The test takes ten seconds: apply the code, watch the total.

## Where ScraperAPI stops working

Success rate matters more than discount here, because a 10% saving on a tool that returns nothing is a 100% loss.

Independent benchmarks put **Instagram, Twitter/X and Booking.com at a 0% success rate** with ScraperAPI. Sites behind a login are explicitly off-limits under the terms of service; the API can't handle form logins or two-factor authentication. Difficult targets also get a **10-minute forced cache**, so live pricing, stock levels and auction data can lag by up to ten minutes, which rules it out for real-time repricing.

Plan restrictions catch people too. Hobby and Startup lack country-level geotargeting outside the US and EU. Business and below have no pay-as-you-go, so a traffic spike means an upgrade or a wait.

If your workload is mostly JS-heavy rendering across many different domains, the credit multiplier makes ScraperAPI expensive per rendered page compared with ScrapingBee, which starts around $49/month with no comparable multiplier system and more predictable costs. Bright Data, from roughly $499/month, is the option for teams where success rate on hard targets outweighs price. Scrape.do undercuts the entry price at about $29/month for simple unprotected scraping. ScraperAPI's advantage concentrates on structured endpoints for Amazon, Google and Zillow at volume, where the parsed output justifies the credit cost.

## Questions that come up at checkout

**My code was rejected. Why?**
Three usual reasons: the account has subscribed before (most codes are first-time only), the code can't combine with the annual toggle, or it expired since the aggregator last checked. Try a different code before assuming the discount doesn't exist.

**Does the free trial need a credit card?**
No. The 7-day trial includes 5,000 credits and up to 5 concurrent connections with no payment method. At 1 credit per standard page that's 5,000 pages; on Amazon's 5-credit multiplier it's about 1,000; on Google SERPs at 25 credits it's 200. Size your test accordingly.

**What happens when credits run out?**
Scraping pauses until renewal, and requests beyond your concurrency limit get a 429 with no extra charge. Auto-upgrade, which moves you to the next tier automatically, is opt-in and available from Hobby through Professional. Pay-as-you-go is available from Scaling upward.

**Is there a free plan I can stay on?**
Yes. 1,000 credits per month with 5 concurrent threads, permanently, no card. Projects that stay under 1,000 credits a month never need to pay.

**Can I use a code after I've already subscribed?**
Most of them, no. Annual billing is the discount that stays available to existing accounts, applied from the billing page.

## How to pick a plan in one pass

Match the plan to the work, not to the discount:

- Scraping plain HTML from unprotected sites at low volume: free plan first, Hobby when you outgrow it.
- Amazon, Walmart or Google SERPs: multiply your monthly page count by 5 or 25 before choosing between Hobby and Startup. The sticker credit number is misleading on these targets.
- Country-level geotargeting outside the US and EU: Business is the floor, at $299/month or $269.10 annually.
- Volume that swings with client work or seasonality: Scaling, where pay-as-you-go absorbs the peaks without a permanent upgrade.
- Needing Instagram, Twitter/X, Booking.com or logged-in pages: none of these plans will do it.

Before you pay, confirm two things on the checkout screen: the billing cycle is the one you intended, and the total on the final page reflects the discount you applied. Then apply your code.

👉 [Check current ScraperAPI pricing and apply your code at checkout](https://www.scraperapi.com/pricing/?fp_ref=coupons)
