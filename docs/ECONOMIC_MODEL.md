# TIME — Economic Simulation Specification
## Verifiable model · v0.1

This document defines **game rules, not a claim that labor time is a discovered physical price of all things**. Explicitly separate what is measurable, what is conventional policy, and what remains a difficult economic allocation question. A simulation should expose these seams rather than suppress them.

## 1. The five different “times”

| Symbol | Concept | Unit | May change retroactively? | Is it currency? |
| --- | --- | --- | --- | --- |
| `H_actual` | Actual person-time consumed doing work or travel | person-hour | Logged events immutable; append corrections | No |
| `H_embodied` | Attributable historical human effort in producing a particular item | person-hour | Historical certificate immutable after finalization; append audits | No |
| `H_ref(x,t)` | Feasible efficient reference effort to deliver equivalent quality/output `x` using technology known at `t` | standard-work-hour | Recomputed for **new** production only | No |
| `H_avoided` | Time avoided versus a specified counterfactual by an innovation/site/service | person-hour per period | Estimate changes as comparison changes | No |
| `TC` | Transferable time credits; claims cleared against contributions and obligations | credit (defined at a fixed nominal standard-work-minute) | Ledger entries append-only | Yes |

`H_free` is **actual time available for self-directed activity** in agents' daily diaries; do not compute it by simply summing `H_avoided`.

### Unit constitution

**1 TC = 1 standard-work-minute of accepted task-equivalent productive contribution**, under the game's published reference-task protocol. This is a fixed definition of the nominal unit, **not** a promise that a TC can always purchase any actual person's minute or the same consumer basket. Some work requires specialized training; actual elapsed minutes and credited standard minutes differ.

The initial reference catalog has standard tasks (e.g., producing a specified food ration of verified quality) whose benchmarks are seeded explicitly for the toy world. In the full simulation, a versioned reference catalog is derived from demonstrated feasible production recipes, not exchange prices. Revisions change prices of newly made goods but never rename the nominal minute or rewrite a certified object's history.

An efficient specialist may complete many task-equivalent minutes of output in one real minute; a slow producer is not paid extra for unnecessary delay. Benchmarks are contestable and updated through demonstrated methods and transparent policy, **not automatically inferred from the last amount somebody bid**.

The choice of reference tasks, fair compensation for training, treatment of unequal abilities, and the reduction of heterogeneous inputs to a scalar are **governance assumptions, not facts of physics**. Represent disagreement explicitly in Laboratory mode.

## 2. Actors, physical world, and schedules

- **Agents:** age band, household, home, workplace/school, health, skills/training, current commitments, desired activity, personal policy preferences, credit account, physical inventory.
- **Physical goods:** unique identity, quantity, location, durability, condition, grade/quality, ownership/use rights, input lineage, historic certificate.
- **Service events:** teacher-hour, clinic visit, vehicle trip, performance, museum visit; event-specific output and quality, rather than persistent inventory.
- **Production recipes:** typed input quantities, equipment capacity and depreciation, skill preconditions, actual task time distributions, outputs and co-products, energy and environmental externalities.
- **Infrastructure:** roads, bridges, power, housing, schools, clinics, repair services, library/museum; capacity, queues, upkeep, failures, travel-network edges.
- **Resource stocks:** food, timber, ore, water, energy generation/storage, ecological burden; **physical scarcity is not reduced to time**.
- **Institutions:** households, producers, commons treasury, research fund, training program, shared service co-op.
- **Daily diaries:** sleep, care, essential work, optional paid work, travel, education, health, leisure, idle/waiting. All 24 hours must be accounted for without counting a minute twice.

### Daily update order

1. Apply exogenous state: weather, crop growth, wear, shocks, arrivals/births, resource regeneration.
2. Refresh agents' needs, task offers, skills, preferences, civic project votes.
3. Schedule agents and scarce equipment subject to capacity, consent, health, and physical inputs.
4. Execute journeys (route/queue time), work events, production, maintenance, consumption, and recreation.
5. Finalize output-quality checks and accepted transactions.
6. Apply double-entry credit postings, loan repayment/default handling, and institutional budget constraints.
7. Measure realized diary use, physical conditions, time cost, well-being, access, inequality.
8. Update **new** efficient recipes only when verified; compute scenario forecasts and save an event log/snapshot.

With a fixed random seed and the same player actions, this must yield the same state and metrics.

## 3. Provenance and time cost

A product has **two distinct price-like quantities**:

### A. Historical embodied effort (immutable certificate)

For a completed production batch `b`:

```text
H_embodied(b) =
    direct_verified_person_hours(b)
  + Σ allocated_embodied_input_hours(b)
  + Σ allocated_capital_use_hours(b)
  + verified_shared_service_hours(b)
```

Each upstream batch or piece of equipment has a unique ID and its inherited embodied hours are allocated once through production events, preventing multiplication of the same labor along branches. Tools/machines pass through a fraction of their embodied labor as capacity is consumed; track remaining embodied allocation. Multi-output recipes must assign fractions summing to 1, flagging arbitrary shared-cost assignments. Reused/recycled inputs carry remaining allocations explicitly. Repair labor is added as a distinct event rather than changing the original certificate.

**Important:** Historical hours can be *wasted* and do not create an enforceable buyer or resale floor. A seller may ask to recover 100 hours; buyers may decline. If goods deteriorate, their provenance stays true while current usefulness and expected repair requirements change.

### B. Current efficient reproduction cost (versioned)

`H_ref(output_spec, technology_version, conditions)` = minimum currently **demonstrated feasible** attributable human effort for an equivalent quality-checked output, given available recipes, physical constraints, and amortized supporting infrastructure. It is not the absolute theoretical global minimum, which may be unknowable. Record candidate recipes and assumptions, and prefer **achievable** to magically optimal recipes.

When technological progress halves assembly time, the reference cost for new phones falls. The historic record of an old phone stays as it was. An actual new factory with bad yield might spend more than reference cost, but may not charge extra simply because it wasted effort; it must improve its process or find a willing donor.

**No arbitrage from waste:** verified labor is *logged* whether successful or not; credits are not minted simply by putting in hours or deliberately choosing an inefficient path.

## 4. Time savings and counterfactual attribution

For the same output quantity, required quality, location context, and safety standard:

```text
H_avoided(event) =
    estimated_person_hours(best_valid_alternative_to_event)
  - actual_person_hours(chosen_method)
```

A credible counterfactual is declared, shown in UI, and versioned. Separate:
- **Potential savings:** modelled capacity over expected lifetime.
- **Verified process savings:** comparison for events that actually occurred.
- **Realized time freed:** change in agents' diaries available for self-directed activities after behavior and demand adapt.

If demand expands, extra output is not disguised as time freed. If a new tool requires maintenance, data labeling, rare material extraction, training, or displaced care work, count that work in the appropriate affected agents and input chains.

**No double counting:** inventions share a baseline chain; allocate marginal improvements against the *best previously usable* alternative at adoption time. Combined interactions must be evaluated with a same-world counterfactual replay, and residual/shared effects flagged rather than assigning 100% to each inventor.

### Example: bridge

Given 50 daily travelers each avoiding 30 minutes of travel **one-way**, the daily gross reduction is 25 person-hours. A bridge requiring 300 attributable hours has a 12-day *simple* payback. If maintenance uses 1 hour/day, net recurring saving is 24 hours/day and payback is 12.5 days (ignoring construction disruption). If more trips occur afterward, actual discretionary hours may grow by less than 24. Never issue 24 TC/day solely because the bridge exists.

## 5. Land, housing, and access

**Building = manufactured stock**, with embodied history, current replacement/reference cost, condition, remaining life, and expected maintenance.

**Land = a bounded location/right, not manufactured labor.** Avoid assigning land an imaginary production history. Evaluate its service through accessibility:

```text
site_daily_access_savings(household, site, baseline_site) =
  Σ over required/desired trips [frequency(trip) *
    (travel_time(baseline_site, destination) - travel_time(site, destination))]
```

The baseline and trip basket are explicit. New clinics, relocated employers, congestion, family changes, public transit, and accessibility needs alter the site's *current* time advantage. They do not alter historic building cost. A site may have social/environmental advantages not represented by travel time.

**Scarcity allocation remains a game decision:** queue/lottery/priority/shared ownership/rotation, with fairness and strategic behavior modeled. An auction is optional **only in a comparison regime**. Low labor-cost creation does not grant infinite desirable land.

## 6. Credits and interest-free clearing

A time credit is a **transferable accounting claim**, not a certificate that time has been stored.

- Issue/extend balances only when an accepted output/service is supplied to a consenting recipient, or a transparently approved civic obligation funds it.
- Every posting is double-entry: `Σ balances = 0` across the closed simulation (including institutional accounts and credit liabilities).
- Positive account positions have counterparties with obligations. Enforce credit limits, repayment schedules, default resolution, consent, fraud/quality controls.
- **No automatic balance appreciation, interest, or yield.** A 100 TC principal obligation is 100 TC principal; actual real purchasing possibilities may still change as technology and scarcity change.
- Civic projects can pay workers through a funded commons account or an approved credit line; beneficiaries can later contribute and retire obligations.
- A contribution becomes payable because someone has agreed to accept the output, **not because the producer consumed an impressive number of hours**.
- Public services and universal entitlements require explicit collective funding/contribution rules. An unfunded public debit is a liability, not free money.

This can become insolvent. Simulate bad loans, departure, inability to repay, and the governance consequences of debt relief or shared loss. An immutable unit **does not** solve solvency.

## 7. Invention and artistic contributions

**Research support:** hours spent on authorized research are compensated by a funded research institution, even when an experiment fails. No false guarantee of breakthrough.

**Prizes:** fixed, ex ante challenge reward on verified quality/outcome.

**Productivity dividend:** a policy-selected, **finite and non-transferable** creator reward. For qualifying adopted improvements:

```text
reward_TC = min(
    reward_rate * verified_incremental_saved_standard_minutes,
    remaining_cap_TC
)
```

Debit willing beneficiary/institutional fund, credit inventor/team. No reward is issued from thin air. A reward expires after a fixed number of years and stops when the improvement is superseded or fails quality verification. Rewards for multi-author work are split by agreed attribution; imperfect attribution is disclosed.

Example: 10→1 labor-hours/task across 100,000 equivalent uses = 900,000 gross hours avoided. At 1% with no cap reached: 9,000 hours-equivalent TC reward, financed from actual participating users; research funding of 2,000 hours is separate. These are **example policy parameters**, not natural constants.

**Cultural/medical benefits:** art, companionship, health, education, and experiences can improve human life without saving labor. Let citizens choose participation. Provide public funding, voluntary patronage, prizes, and quality-of-life effects; never invent counterfactual saved hours just to pay them.

**Museum:** production certificate for the artwork remains unchanged. An exhibition has new service costs (staff, security, restoration, venue upkeep) and finite capacity; visitors pay or receive collectively subsidized access. A billion-dollar “valuation” isn't printed because many people saw the art.

## 8. Scarcity and edge cases the game must surface

| Stress | Expected behavior |
| --- | --- |
| No one wants a 100-hour painting | Historical effort recorded; no required sale/credit issuance |
| Inefficient worker spends 10× more time | Actual time logged; output benchmark and compensation not multiplied |
| New automated recipe almost eliminates labor | New reproduction labor cost falls; resource and access constraints persist |
| Mineral deposit is finite but easy to extract | Production labor low; stock depletion, ecological impacts and rationing remain |
| Rare land has many applicants | Transparent allocation policy; potential queues/favoritism |
| Surgeon requires a decade of training | Training opportunity costs and capacity limits appear; skill shortage is real |
| Research consumes resources but fails | Costs borne by chosen public/private funding pool |
| AI halves a task then work expands | Process efficiency rises; discretionary time may stay flat |
| Public treasury grants everyone credits | Liabilities/counterparty accounting must reconcile; no unbacked hidden mint |
| Product breaks | Original creation certificate unchanged; repair/new replacement efforts logged |
| Co-products and recycling | Input allocation totals 100%; no double-crediting |
| Missing care-work measurement | Diaries expose omitted care burdens and skewed outcomes |

## 9. Instrumentation, invariants, and testing

**Hard simulation assertions**
1. For every agent/day: allocated diary minutes = 1,440; no overlap.
2. For every posting: total debits = total credits; net account sum = 0 (closed economy).
3. Each unique upstream cost allocation ≤ the amount available; co-product allocations total 100%.
4. No event issues credits solely for wasted effort or predicted future saved time.
5. Certified historical records never mutate; corrections are append-only audit events.
6. New techniques do not change past certificates.
7. Resource conservation/stock flows and non-negative reserves hold except explicitly modelled borrowing/storage.
8. Matching counterfactuals demand equivalent quantity, quality, safety, and contextual assumptions.
9. No hidden interest accrual in baseline regime.
10. Player-visible cards identify assumptions: verified fact, estimate, or policy.

**Metrics and exports**: seed, full event log, time diaries by cohort, input-output graph, physical stock changes, resource depletion, credit ledgers, reference recipes and their version history, counterfactual audit notes, benchmark fairness complaints, unmet demand/queues. Every chart should be explainable by replaying events.

## 10. What is deliberately *not* solved by the physics of time

- A unique mathematical conversion between unlike kinds of labor, material scarcity, discomfort, and cultural enjoyment.
- Whether a person *should* prefer one hour of leisure to a medical outcome or a painting.
- Who receives one unique house when fifty households apply.
- Fair allocation of credit risk, deep research budgets, infrastructure obligations, and discovery rewards.
- One infinitely redeemable “hour token”; future access requires future production and functioning institutions.

These questions are the **game**, not flaws to paper over. See [Game Design](GAME_DESIGN.md) and [Vertical Slice](VERTICAL_SLICE.md).
