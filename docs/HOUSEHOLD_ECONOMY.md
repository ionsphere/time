# TIME — Everyday-Life Economy and Agent Simulation
## Design v0.3 · households and exchange are the core

> **Core premise:** Simulate an economically complete, modern small town populated by autonomous people who **earn transferable credits for accepted work and spend them on other people's goods and services**. Their choices change production, demand, household formation, caregiving, housing, research, and the future labor requirements of society. Recovered leisure is a consequence of these mechanisms—not an award granted by the game.

**No bargaining defines the number of credits due for a fish.** Certified reference exchange cost is mechanically computed from feasible production recipes; accepting a purchase affects *whether* a transfer happens, not how many credits the fish is worth. The social decision to guarantee basic access is separately governed. See [Foundational Cost](FOUNDATIONAL_COST.md).

This document supersedes the earlier bridge-first *scope*, not the provenance/credit principles in [ECONOMIC_MODEL.md](ECONOMIC_MODEL.md). Assume that time provenance, reference production effort, quality checks, and settlement accounting can be calculated correctly. The simulation is designed to discover **what people do once this accounting exists**.

## Productivity incentive contradiction

**Earning credits for actual work and lowering production costs through efficiency can conflict.** A fisherman who fills an accepted 10-fish order in six minutes instead of 60 may get one-tenth the income under strict elapsed-time pay, even as consumers pay less for fish. A system dependent only on worked minutes can therefore penalize progress. The simulation **must not assume that a standard minute of cost equals a minute of personal entitlement**. Compare accepted-output commitments, baseline access, finite funded productivity dividends, and intrinsic motivations without changing the immutable physical time unit. See [Productivity Incentives](PRODUCTIVITY_INCENTIVES.md).

## A. Three non-interchangeable quantities

1. **Elapsed human hours:** 24 hours each day per person; travel, work, care, sleep, leisure.
2. **Credited productive work (TC):** transferable credits received when an accepted task/output/service is settled, denominated in a standardized reference minute. Productive contribution is not synonymous with burning minutes. There are no arbitrary wages inferred from a demand curve.
3. **Embodied cost (reference/actual history):** attributable time in a product or service, including recursively allocated upstream work. A product's historical certificate remains fixed, while the reference cost for newly made equivalents can decrease.

A time-saving machine releases calendar time. **It does not mint time credits.** Citizens may choose to work more, use fewer credits because consumer goods have become cheaper, care for family, or pursue art/education.

**Attention:** "automatic and correct accounting" is an explicit simulation assumption, not an escape hatch for allocation, insolvency, supply constraints, research uncertainty, or unequal abilities. Those remain in the simulation.

## B. The exact fish transaction

A fisherman catches **10 fish in 60 minutes** of accepted labor, using 30 standard minutes of attributable fishing-boat/tool/transport/support work for the batch. We take these as already measured, quality-confirmed and allocated exactly once.

| Item | Amount |
| --- | ---: |
| Direct fishing contribution | 60 standard minutes |
| Upstream allocated inputs and services | 30 standard minutes |
| Total reference production cost of batch | 90 standard minutes |
| Reference cost per fish (if no faster feasible equivalent method exists) | 9 time credits |
| Two fish purchased by a household | 18 time credits |

**Transaction timing and ledger:**
- Upstream providers previously supplied equipment and services with 30 certified allocated time-minutes for the batch. The fisherman has paid them already or owes them 30 TC against sales.
- A household with +120 TC buys two fish for 18 TC: household position becomes +102 TC; the seller's position increases by 18 TC. Physical inventory transfers two fish.
- Across all 10 fish sold at cost: the fisherman receives 90 TC gross, pays or has already paid 30 TC to upstream providers, and retains **60 TC for the 60 minutes of fishing contribution** (before shared institutional obligations).
- **No time is created:** the credits move from purchasers to contributors. The full ledger includes all accounts and offsets.
- If the fisherman works for a fishing co-op, the co-op can pay 60 TC for the accepted work before the fish sell, taking inventory risk through its own permitted debit/working-capital position. If self-employed, the fisherman carries that risk until customers buy.
- If the fish don't sell and spoil, the fishing work really happened, but the producer or co-op incurs a loss. **An unsold fish does not force a buyer into existence.**
- If the lake only replenishes 5 fish/day, a 10-fish catch is unsustainable even if its labor accounting is perfect. The ecosystem constrains the feasible catch, not a speculative fish price.

The fish is **not** automatically "free," and equal access to fish is **not** determined merely by who lives closest to the water. A supermarket, reservation system, delivery route, or public provisioning network can all mediate access while the time-cost rule remains the same.

## C. What every autonomous person needs to decide

Each agent is a citizen with an age/development stage, home, family relationships, energy/health, training and skills, temperament, aspirations, promises, needs, daily schedule, household and personal credits, physical possessions, and attitudes toward policies. The simulation cannot assume that everybody wants to maximize work output or leisure.

Every agent repeatedly chooses:
- **What to consume:** buy groceries, order a meal, repair something, seek care, spend on a concert, or go without.
- **What to contribute:** accept a task, operate a business, volunteer, study, do unpaid household work, invent, make art, or rest.
- **What to make:** producers choose batch size from anticipated committed demand, observed unsold stock, spoilage, production capacity, and personal goals; they may stop producing unwanted outputs.
- **Who to cooperate with:** form a household, share care, join a co-op, hire a specialist, choose a job, move, or organize a civic project.
- **How to handle scarcity:** reserve scarce goods, queue, substitute, repair, wait, request public support, or choose a different location.

Decisions use **personal beliefs and limited information**; no single player controls them. Citizens respond to experiences and forecasts. Use a deterministic seeded bounded-rational decision policy for prototype; make choices inspectable ("why did Maya buy fish?"). Do not use LLM inference for economic truth.

## D. Household = the fundamental accounting and decision unit

A household pools some resources and allocates consumption, paid work, uncredited care, and longer-run investments among members. Not every household is two working adults. Include single parents, children, adults with disabilities, people between jobs, retirees, and multi-generational homes.

**Recurring needs**
- Food, drinking water, electricity, shelter, clothing, sanitation, communication.
- Health care, transport, education, childcare and eldercare.
- Replacement/maintenance, social participation, recreation, emergencies.

**Recurring decisions**
- Grocery basket and cooking at home versus buying prepared food.
- Paid work versus providing child/elder care versus outsourcing care.
- Renovate versus repair versus move.
- Pay now versus accept a principal-only loan for a house/tool.
- Save for expected future needs versus spend on quality of life.
- Train now to qualify for a better task later; accept or decline risky research work.
- Have a child if desired, knowing that care responsibilities and household needs change, with a public social-provisioning policy that can affect feasibility.
- Allocate recovered time to second job, school, friendship, family, creative work, or leisure.

**Representative monthly ledger (made-up numbers, in credited hours; not a normative standard):**

| Flow | Hours-equivalent TC |
| --- | ---: |
| Adult A: paid accepted contributions | +120 |
| Adult B: paid accepted contributions | +80 |
| Food and household consumables | −48 |
| Housing construction principal installment | −25 |
| Housing repairs and utilities | −18 |
| Care and education purchased from providers | −35 |
| Health/transport/connectivity | −12 |
| Commons assessments and public services | −22 |
| Creative/recreational goods and services | −8 |
| **Monthly net addition to household balance** | **+32** |

Every expenditure is another person's or institution's receipt (or repayment/assessment), not credits burned in an invisible shop. A household can instead save less, provide more care directly, or require public support.

**Care is an essential economic activity**, not a free output from a non-working parent. Record actual caregiving time and determine how it is recognized/funded under explicit alternative policies: household private time, paid community care, civic child credit, eldercare social insurance, cooperative sharing. When paid, compensation has a payer or treasury obligation. Model childbirth, parental leave, illness, dependency, education and retirement across years.

## E. Goods, jobs and businesses are endogenous

No "buy fish" button may conjure fish from nothing.

Each producer has people, skills, physical inputs, equipment capacity, output quality, maintenance requirements, location, budget/credit, planned recipes, unsold inventory, cash/credit obligations, and expectations of future orders.

**Simple cycle:**
1. Households forecast needs and send **interest/reservation/orders**, not money bids.
2. Producers decide whether enough potential users justify effort and equipment commitment.
3. Workers voluntarily accept scoped tasks; supply inputs move in physical inventories.
4. Output passes quality/acceptance; time receipts assign direct and upstream contributions exactly once.
5. Goods are offered at **algorithmically certified reference production cost** under baseline policy, not at a wage, markup, maximum willingness to pay, or agreed compensatory price. Consumers choose whether to transact, not the unit cost.
6. Consumers with sufficient balances/limits accept purchases; payment transfers TC and delivery moves stock.
7. Providers recoup work, fund inputs, and decide whether to continue, expand, retrain, or abandon production.

**Oversubscription:** when 20 households want 10 fish, fixed-cost prices do not manufacture extra fish. Run a transparent distribution rule: reservation timestamp, need-based priority, lottery, per-household quota, or trade permission. Display shortages and waiting time. Allow citizens to respond by fishing more if resources permit, substituting beans, eating something else, or moving. Explicitly test queues, black markets/side payments, and allocation favoritism. No price hikes in the baseline time economy.

**Undersubscription:** when nobody wants a 100-hour painting, the painting retains an historical record but generates no obligated payment. The artist may seek patronage, exhibit it, keep it, donate it, or try another project.

**Upstream allocation:** when a tool contributed 6 minutes to a fish, that isn't a *newly spent* 6 minutes on sale; it recovers previous embodied effort through stock/capital accounts. The simulation must never credit the same original hour twice.

**Skill differences:** a specialist may require years of training and have scarce capacity. Reference task standards and training cost allocation can yield insufficient participation even without financial bidding. Present this as a failure condition to solve with training support, priority access, finite task rewards, or an explicit policy change, not an automatic “physically correct” wage.

## F. Where the first transferable credits come from

Unlike minted mining tokens, TC is a **mutual-credit settlement unit**, not a reward for running the clock.

A closed ledger may start from existing positive claims matched by institutional/household negative obligations. Or it may start at zero and issue reciprocal debit/credit balances only on an authorized transaction.

**Illustrative bootstrap** (assuming limited unsecured credit is institutionally accepted):
- Household needs 9 TC worth of food but has 0 TC.
- Food co-op accepts household's −9 TC obligation up to a published limit; co-op receives +9 TC.
- Household later supplies 9 TC of accepted repair work for others; the received credit repays its negative position.
- All postings balance across accounts. The community has **not physically stored nine historical minutes**. It has organized a credible future contribution and taken the risk that it won't materialize.

**Risk:** someone can be ill or unable to repay, or the food may spoil. Set eligibility and credit limits, provision reserves, social aid, forgiveness rules, and shared loss allocation. Without this, families can starve despite a mathematically balanced ledger.

**Producer working capital:** a co-op can issue authorized liabilities to workers/suppliers against forecast sales; if demand collapses, losses must be allocated. Do not require a fish seller to finance all required upstream labor personally before any sale.

**Savings:** a positive TC balance is a claim against a network's future goods/services, **not a guarantee of 1:1 specific future labor delivery or a compounding bond**. Credits earn no default yield. The game measures ability to spend them and the solvency/acceptance of the network.

## G. Housing and family over a lifetime

**House building:** the box has a provenance certificate (example 4,000 credited hours); land is a site-use right distributed by the chosen allocation policy; location advantage is measured in current commute/amenity access, not fabricated historic labor.

A newly forming household without 4,000 TC upfront can obtain an authorized principal-only 4,000 TC construction obligation. Builders and upstream suppliers receive credited payments for actual work, and the household repays principal over (say) 20 years: **200 TC/year**, plus maintenance/utility/civic charges. No compound interest; **defaults and resource rationing still exist**. The structure ages and needs repairs; moving requires settling ownership and claims under explicit rules.

A child contributes no required economic output, but consumes food, shelter, education, medicine, and care. An old or sick citizen can also need care without equivalent current credited work. Simulate at least three policy choices:
1. Private household provisioning only (stress test: can be harsh and exclusionary).
2. Household + community services financed by explicit assessments.
3. Universal essential-access guarantee with transparently funded commons obligations and capped claim creation.

Measure fertility/family formation, intergenerational transfers, education access, dependency, debt, and whether citizens face poverty or high obligatory work even if mean productivity soars. No assertion that free credits create physical output.

## H. What AI does to the *entire flow*

When a technology reduces required human work per equivalent unit, the baseline reference production cost of **new** units falls after adoption and quality verification. The old product's provenance is unaffected.

This creates a genuine macroeconomic experiment:
- Prices of automatable goods fall in TC as required production labor falls.
- Workers may produce more, shift occupations, train, offer services, provide care, or work fewer hours.
- Personal credit earnings may also decline if fewer accepted human contributions are needed. That is not automatically compensated by time savings.
- Some goods remain scarce because of land, resources, quality, attention, and constrained specialist time.
- If almost all reproducible necessities need zero human work, the baseline unit-cost rule drives their *labor* price toward zero, but logistics, scarcity, and access still need allocation. The system may need shared provisioning and collective rights over automated productive capacity.
- The economy may fail for households with no way to earn TC while they still need scarce goods. **This must remain a visible possible outcome.**

A strong test asks: after automation, are the same households **better able to acquire what they need** or merely unable to find paid work? Distinguish less necessary work from less *available* work.

## I. Agent cognition (not scripted villagers)

A tractable agent model combines:
- **Needs:** daily physical minimums and longer-run well-being, health, family needs.
- **Beliefs:** expected demand, labor/transport effort, supply reliability, household stability.
- **Preferences:** leisure, children, creative pursuits, social life, status/recognition, security, vocation.
- **Constraints:** balances/credit, available hours, qualifications, geography, stocks, queues, permissions.
- **Decision policy:** choose a feasible package of activities and purchases using bounded lookahead, learned expectations, and randomized preference heterogeneity.

Example policy sketches:
```text
buy(food):
  if hungry and offered_stock > 0 and
     (balance + unused_credit_limit >= posted_reference_cost):
      purchase(); transfer_TC(); transfer_inventory()
  else:
      seek_substitute_or_support_or_wait()

accept_task(task):
  if skills_sufficient and required_inputs_reserved
     and acceptable_terms and time_available and
     expected_household_benefit > opportunity_cost:
      perform_then_settle_if_accepted()

have_child():
  evaluate_desire_for_family, predicted support, care arrangements,
           household resources, age/health, space, future confidence
  choice_is_probabilistic_and_not_optimized_only_for_currency
```

Agents must have explicitly inspectable *reasons* (needs/beliefs/constraints) for decisions. The player can follow a fish from lake -> co-op -> store -> household meal, and follow the 9 TC back to accepted work.

## J. Player perspective: life simulator + economic laboratory

The **default player** follows one contemporary household through jobs, shopping, family, housing, and civic decisions. The town around them is alive, autonomous, and open to inspection. The player may directly choose the focal household's actions (life-simulator mode) but can't force everyone else's choices. At any time they can move to the **Society Lens** to propose a policy and branch/replay the same seed as an experiment.

**Early player moments**
1. Earn TC from a meaningful accepted job.
2. Choose groceries at a store; see supply, reference time cost, and producer provenance.
3. Choose cooking vs prepared food vs no purchase.
4. See fisherman decide whether to catch more fish next morning after sales/unsold stock.
5. Need to repair something; pay another citizen, barter skills through credit, or do it yourself.
6. Work less after an automation update; see prices fall **and** task availability change.
7. Arrange child care to take a job; observe care costs and family time.
8. Apply for a home, inspect box construction principal and land accessibility/allocation.
9. Research a new technique or patronize creative work; experience uncertainty and spillovers.
10. Reach retirement with a credible position or experience a claim/supply crisis.

**Economic Laboratory** can compare the same agent seed under time-based fixed production costs and interest-free credit, a simplified conventional market regime, and hybrids. All regimes need identical physical technology, agent preferences, resource stocks, and availability of public services except explicitly selected policy differences.

## K. What the game must be able to disprove

- Production-cost pricing may produce persistent queues for scarce items.
- Specialists may refuse work under a flat reference-hour rule.
- Research funding may be too small without uncertain future upside.
- Co-op losses can socialize costs even when ledger invariants remain intact.
- A zero-interest house loan still reserves scarce builders, land, and future repayments.
- AI may reduce consumer prices *and* reduce opportunities to earn credits, leaving some households worse off.
- Households with care responsibilities may be excluded unless contribution/funding rules account for care.
- A creation cost can be historically objective while economic acceptance of the product remains optional.

The game's objective is to find policies that survive these tests, not to hide them.

## L. Prototype engine boundary and acceptance checks

**Core simulation modules**
```
world: people, households, households relationships, health/age, physical stocks
economy: credit ledger, obligations, working capital, public treasury, defaults
production: output specifications, recipes, jobs, co-ops, inventories, quality,
            upstream provenance, reference costs, equipment depreciation
exchange: orders, cost-quoted offers, reservations, delivery, queue allocation
lifecycle: child, adult, aging, illness, education, training, care, family formation
behavior: agent goals, needs, preferences, beliefs, bounded choice, adaptation
policy: land-use allocation, school/care/clinic funds, social support, credit rules
metrics: nutritional sufficiency, affordability, wellbeing, work, care, leisure,
         shortages, unmet demand, household solvency, inequality
replay: fixed seeds, transparent event history, scenario branches
```

**Testable invariants**
1. Buyer credit decreases by precisely what seller/institutions receive; all ledger positions reconcile.
2. Sale moves actual fish stock, no fish magically created; a fish can be eaten only once.
3. A producer's net income from batch sales equals value transferred for direct contribution after recouping correctly allocated upstream inputs and commitments; unsold stock may generate a loss.
4. Paying for an accepted job creates a counterpart obligation or transfers existing balance. A person cannot create credits simply by marking a task complete.
5. No double spending and no duplicated upstream time allocations.
6. No agent spends more than 24 hours in a day; care/travel/work are mutually exclusive time slices.
7. A child/retiree can consume if supported by household, public provision, or credit policy; if not supported, the system visibly records unmet need.
8. A housing loan funds a real house with actual materials/work and an enforceable principal obligation; loans cannot conjure construction inputs.
9. New automation reduces new labor costs but does not automatically add currency to any individual's balance.
10. Fixed-cost scarcity triggers a visible allocation rule rather than an unnoticed price increase.
11. Same seed and actions -> same outcomes; differences among policies can be traced to explicit rule changes.
12. Producer cannot force acceptance of unwanted outputs; no retroactive historical cost mutation.

**First playable target**: a present-day neighborhood of ~60 households / ~160 agents, with a store, food co-op/fishing supplier, tool repairer, small builder, healthcare/care worker, public commons fund, and a few family/age profiles. Simulate a month with groceries, jobs, consumption, working capital, rent/use-right or loan installments, child care, illness, and one productivity improvement. *The bridge is an optional later demonstrator, not the tutorial's only economy.*

**Exit criterion:** selecting any citizen, any piece of fish, or any time credit provides a complete, auditable causal chain across production, payment, consumption, and changed human behavior. A simulation without actual life-cycle and cross-household transactions does not yet test the economy.
