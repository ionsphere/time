# TIME — First Playable: A Month in a Modern Neighborhood
## Vertical slice v0.2 — everyday exchange first, infrastructure later

**This supersedes the bridge-centered first playable.** The bridge remains an optional demonstration, but the game must first simulate households who earn, shop, cook, care for children, maintain housing, and face uncertainty. The accounting and settlement mechanics are described in [Household Economy](HOUSEHOLD_ECONOMY.md) and [Economic Model](ECONOMIC_MODEL.md).

> I work, buy fish another person caught, cook a meal, pay for care, save for housing, and choose how I respond when software automation changes available work. Every person and every time-credit transfer has an explainable origin.

**Setting:** modern neighborhood, with automatic verified accounting. Approximately **60 households, 160 citizens**, in varying life stages, with a deterministic simulated month plus long-horizon acceleration and years-long event snapshots.

## Required simulated economy

- Food: fishing co-op, upstream boat/tool suppliers, farm, grocery store and optional food preparation.
- Housing: home construction, repair, land/site-use allocation and interest-free principal obligations.
- Services: utilities and transport, care/school, clinic, software and repair work.
- Finance and commons: time-credit ledger, producer working-capital, household credit limits, public care support, defaults and assessments.
- People: employed and unemployed adults, children, a single parent, caregiver, retirees, ill people, and specialists.
- Choices: accept work, create products on anticipated demand, buy goods, seek services, share care, invest in skills, have children, save, move, borrow and refuse unwanted work.

Producers own actual inventory. Customers cannot buy fish not caught; producers do not get paid simply for spending time when nobody accepts what they made. Fixed production-cost pricing can lead to shortages/queues, unsold inventory, or changed production volumes.

## First-play session (25–35 minutes)

| Moment | Experience | System verified |
| --- | --- | --- |
| Meet household | Two adults and a child, current time diaries, skills, balances, health, house, food and care needs | Households create demand |
| Work | Accept a software/repair task and earn time credits when accepted | Productive work is compensated |
| Buy fish | Two fish cost 18 credits when the verified batch has 90 credited minutes for 10 fish | Goods and credits transfer |
| Follow the fish | See fisherman, lake, tools, upstream maintenance, co-op inventory and payment chain | Provenance + payment are auditable |
| Eat | Household consumes fish, health/food inventory changes; supplier updates next-day catch | Consumption shapes production |
| Care | Choose daycare versus household caregiving; observe consequences for earnings and time | Care cannot disappear |
| Housing | Pay repairs or principal; preview a different home and scarce-site allocation | Family planning and obligations |
| Automate | Apply verified process change; prices for newly produced equivalent work fall, accepted job availability may change | Progress can benefit and displace |
| Branch policy | Compare food-queue policies, credit default rules, public care support | Institutional choices matter |
| Time travel | Advance to month 12, year 5, year 20 and inspect child, parent and retiree outcomes | Families must remain viable |

The player guides one household, can inspect or switch to other citizens, and can run counterfactual civic-policy experiments. The town remains autonomous; no player compels everyone to work.

## Fish receipt and settlement

**Batch:** 60 accepted fishing minutes + 30 upstream allocated minutes -> 10 fish = 90 credited minutes. Two fish cost **18 TC**. A household with +120 TC spends 18 and ends at +102. The seller receives the 18, and physically delivers two fish. Across full batch sales the fisher receives 90 gross, covers 30 of previously purchased or owed upstream inputs, and retains 60 for the direct fishing contribution.

A co-op may pay the fisher before all fish sell using a permitted working-capital debit, then bear inventory/spoilage losses. Self-employed fishers may be paid when their catch sells. **No additional credits are created by recording embodied time or by a fish swimming into a net.** Closed-world ledger entries reconcile.

If the lake is exhausted, the inventory cannot be refilled. If 20 households want 10 available fish, a visible ration/lottery/priority/queue policy determines access, and agents seek substitutes or new suppliers. The posted reference time cost does not automatically rise with demand.

## Primary interface

1. **Living Neighborhood:** contemporary map, homes, workplaces, shopping, deliveries, school, clinic and citizen routines.
2. **Person/Household Diary:** 24-hour activities, real work/care/travel/leisure, income, consumption, food inventory, monthly budget, loan principal and health.
3. **Time Receipt:** verified production provenance, historic effort vs reference production cost, physical stock and quality.
4. **Who Paid Whom:** follow exact time-credit postings from the buyer to sellers, salaries, upstream providers, taxes/assessments and principal-only repayments.
5. **Society Lens:** distributions of food access, care, housing, work, shortages, credits, insolvency and quality of life, including children and elderly.
6. **What-If Timeline:** identical seed and inputs under alternate policies or technologies.

## Engine and initial milestones

**Architecture:** headless, deterministic agent-based simulator; event-sourced ledger; physical inventory and production graph; bounded-rational agent policies; household/lifecycle dynamics; thin visual renderer; seeded replay and measurable counterfactuals.

**M0 — fish exchange:** two households, fish co-op, upstream input provider, accepted work, stocks, spoilage, settlement, authorized working capital, double entry.

**M1 — everyday economy:** dozens of households and food, housing, care, health, infrastructure and service sectors, autonomous producer and consumer decisions.

**M2 — life stages:** childhood, education, family formation, caregiving, illness, retirement, housing loans, support policies and default.

**M3 — UI and narrative:** daily life, purchases, receipts, transaction tracing, household dashboard and agent decision explanations.

**M4 — automation and research:** add **The Better Fisher** incentive dilemma: if labor per ten fish falls from 60 to six minutes, does a fisher adopt the method when hourly pay drops? Compare accepted-output obligations, stable essential access, finite funded innovation dividends, and intrinsic motivations. Also test jobs lost/new tasks, training and scientific uncertainty. See [Productivity Incentives](PRODUCTIVITY_INCENTIVES.md).

**M5 — economic laboratory:** compare time cost, conventional money/interest and hybrid rule sets in matching worlds.

**M6 — city infrastructure / art:** bridges, land accessibility, museums, public projects; now embedded in a working economy.

## Acceptance tests (before visual polish)

1. Fish batch, inventory, accepted work and money trail reconcile exactly; two fish transfer and cost 18 TC in the example seed; no double-counting upstream efforts.
2. No demand leads to unsold fish/spoilage; excessive demand leads to transparent queue/allocation, not hidden price escalation.
3. Person-hours in a day never exceed 24; care, transport, work and leisure cannot overlap.
4. Accepted work earns credits through actual transfers or bounded obligations; wasted time alone does not mint them.
5. A household can buy food and services, service house principal, support dependents, save, and make discretionary decisions.
6. Children, temporarily ill adults, single parents and retirees have realistically different support and access under chosen policies. Unmet needs are observable.
7. All closed-world time-credit postings sum to zero; loan loss and public debt are explicit.
8. Automation makes new equivalent outputs cheaper while leaving historical production certificates fixed; no balance increases just because time is saved.
9. At least one specialist shortage, fish shortage, and household-credit default produces an uncomfortable policy trade-off.
10. The same seed plus the same actions produces identical diaries, stocks, credit transfers and outcomes.

**Exit criterion:** select any piece of fish, person, or credit and trace where it came from, who produced it, who paid whom, who consumed it and what each person did next. Without everyday cross-household exchange, the game cannot evaluate the time economy.
