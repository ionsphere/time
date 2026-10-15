# TIME — Foundational Cost, Not Agreed Compensation
## Pricing constitution draft · v0.4

> **Correction to earlier designs:** “Agreed compensation” cannot determine the monetary value of a fish. If the fisherman and buyer negotiate how many time credits a fish merits, negotiated exchange values have re-entered the system. We therefore separate (1) auditable physical cost, (2) mechanically computed standard transaction cost, (3) voluntary acceptance and scarcity allocation, and (4) rights/obligations governing access to shared production. Their rules are not the same.

This document is a **hypothesis to test**, not a proof of a uniquely derivable universal economic scalar. The underlying project is to make the exchange measure independent of bargaining, not to deny that real people choose whether to produce, consume, help others, or hold an object.

## 1. Foundational unit and calculation

**Fundamental clock:** one elapsed minute is the same physical duration regardless of who is working. No one can renegotiate a minute's length.

**Observed production:** for a specific verified batch of `n` equivalent acceptable outputs:

```
historical_direct_minutes_per_output = verified_direct_human_minutes / n

historical_total_minutes_per_output =
    (verified_direct_minutes + allocated_upstream_human_minutes) / n
```

A fisher who catches ten usable fish in 60 human minutes embodies **6 direct minutes per fish**. With 30 upstream embodied minutes attributable to the batch, the full historical cost is **9 minutes per fish**. If the fisher catches 100 usable fish in the same direct hour with otherwise unchanged tools/upstream allocations, direct effort is **0.6 minutes per fish**; total batch cost including those 30 upstream minutes becomes **0.9 minutes per fish**. In general, equipment/maintenance inputs may also vary and must be recorded—not assumed constant.

**No agreement makes the number six**. It is measured production history, with mathematically explicit allocation. This is an auditable *historical cost certificate*, not yet necessarily the transaction price.

**No invention or efficiency improvement rewrites the old batch:** the older fish were genuinely produced at the old cost.

## 2. Why use a reference cost for new exchanges?

If a fish automatically sells for its **actual** minutes consumed, deliberately taking ten times longer to catch one may command ten times the credits. Actual-time pricing gives a perversely rewarded inefficiency.

Candidate non-bargained transaction rule:

```
posted_cost(output_spec, date, accessible_conditions)
  = minimum verified attributable person-minutes
    among physically feasible, quality-equivalent production plans
    accessible under those conditions
```

This is **production-recipe optimization**, not an agreement between buyer and seller and not a derived CPI or currency exchange rate. Given the same quality specification, eligible technology, location/logistics constraints and available production capacity, the rule is deterministic and independently auditable. Faster verified production methods lower **new** output costs. Actual labor spent above the reproducible benchmark remains recorded but does not give the seller the right to charge more.

**Critical limitations to simulate:**
- A theoretical fastest technique is irrelevant if nobody can actually access it. Capacity constraints and equipment costs matter.
- The feasible minimum for the *first* fish may not scale to the thousandth fish; optimizing an entire demanded quantity can yield a quantity-dependent schedule and different marginal or averaged effort. Required quantity is a physical service requirement/consumer request, **not a willingness-to-pay price bid**.
- “Same fish” requires published quality/size/safety/freshness and delivery conditions. People may dispute product classification or whether an observed recipe is genuinely reproducible. Independent measurement does not remove standards governance.
- Co-products, capital depreciation, training, research allocation, ecology, and scarce mineral rights cannot all be uniquely mapped to a scalar minute from physical law alone. Any chosen allocation convention must be **public, versioned, constrained, and non-negotiable at point of sale**, while retaining the admission that it is a convention.
- Prices of past certified batches are historical facts; current reference costs for **new** output can rise if available inputs are depleted or infrastructure fails. “Stable unit” does not mean fixed price for every product forever.

A reliable implementation can start with auditable production graphs and batch cost certificates **before** claiming a perfect global reference-price oracle.

## 3. A transaction involves consent, but not price bargaining

Example under a verified 9-TC fish reference:
- The store has two physical, safe fish.
- The posted exchange cost is **2 × 9 = 18 TC**.
- The consumer decides whether to buy. They cannot demand a discount by arguing that fish are undesirable.
- The seller may offer or decline to produce; they cannot demand a markup by arguing that fish are fashionable.
- If a buyer purchases, **18 TC move from buyer to seller/settlement accounts** while two real fish move to the buyer.
- If nobody wants fish, no sale is forced; work was still spent, possibly wasted.

The parties choose **whether to participate and how much quantity is needed**. The production rule sets **the numerical accounting cost**.

If ten fish exist and twenty households request them, fixed cost does **not** make the fish multiply. Allocation requires a separate public policy: priority, lottery, quota, reservation, or a share of common stocks. Scarcity may create queues, side payments or illicit resale. A no-bargaining rule has an enforcement and incentive problem; pretending otherwise makes the game invalid.

Do not call the purchase cost “agreed compensation”; call it **certified reference exchange cost**. Call the mutual-credit transfer **settlement**. Call a separately granted support entitlement a **constitutional access right**, not fish price.

## 4. The incentive impossibility: three wishes cannot all hold

Consider improving a method to make ten fish in six minutes instead of 60.

We might want simultaneously:
1. **New fish cost six direct minutes**, because that is all the verified current method needs.
2. **The fisherman personally receives the old 60 credits** for the ten fish, so he is not financially punished for improving efficiency.
3. **No third party pays the 54-credit difference** and no extra new monetary claims are issued.

Those three conditions cannot all be true in an ordinary closed transfer ledger: if purchasers transfer only six credits, the producer cannot receive 60 without another debit, liability, or explicit transfer. (Add upstream costs to both sides without changing the logic.)

**This is an accounting impossibility, not a choice between market and non-market pricing.** The game must let players see it directly.

If we insist on immutable production-based prices and no artificial token issuance, productivity incentives have to come from an **explicit second institution**, not from falsely increasing the exchange cost of the fish.

### Candidate institution: contribution requirements and essential access

Suppose the community guarantees an explicitly defined level of access to necessities **conditional on physical capacity and a transparent support framework**. Participants contribute toward required services through completed outcomes and take fewer obligatory tasks as technology improves. Finishing ten fish in six minutes rather than 60 yields **54 more minutes available for personally chosen activity**, *provided access to necessities is not mechanically reduced with the labor performed*.

This is **not** a claim that the producer earns 60 new currency units. The fish still costs six direct-minute-equivalents under the updated method. A separate common-provisioning rule decides how baseline food, housing and other essentials are made available, and who takes responsibility for necessary work. The rule's burden, rationing, limits and potential free-riding remain visible.

Optional incentives: an **explicitly financed** finite productivity reward; social recognition; priority to conduct research; self-directed creative time. None is an ingredient of fish's certified price. Innovation prizes are policy choices with a debited fund, not physical constants.

### Why “contribution obligations” aren't another bargaining price

The **number of minutes embodied in a fish** is computed, not bargained.
The **choice of who must do which work and who gets guaranteed baseline access** is a social allocation constitution, not an invariant physically measurable property. People can dispute and change these institutions; changes affect claims/access, not the length of a minute or a fish's historical production record.

A fully politics-free or governance-free economy cannot be derived just from the clock. That limitation must be a **visible simulation result**, never patched by an unmentioned negotiated wage.

## 5. Reproducible simulation tests

1. **Same verified physical inputs -> same historical time cost**, regardless of producer identity, consumer wealth or desire, or market price.
2. Producing 10 fish with 60 direct minutes yields 6 direct min/fish; 100 fish from 60 minutes yields 0.6 direct min/fish.
3. If verified upstream allocation is 30 minutes in both examples, total costs are 9 and 0.9 min/fish respectively, without duplicating upstream credits.
4. Artificially wasting 60 more minutes on an otherwise equivalent product does **not** increase the benchmark and cannot command a larger posted transfer.
5. Advancing available technology lowers reference cost for **future** identical products, not historical certificates.
6. Buyer/seller preference changes without physical process changes do **not** change reference cost or posted exchange cost.
7. Requested quantities beyond feasible supply cause transparent rationing/queues or producer planning, **not demand-based markups**.
8. Better fish with reduced quality/freshness, dangerous depletion or undeliverable equipment are **not** falsely treated as a valid equivalent recipe.
9. A worker who earns fewer credits after a productivity improvement may struggle to obtain necessities unless another explicit institution compensates through *access*, not a fabricated fish cost.
10. The “six paid / sixty received / nobody else pays” assertion is rejected by the settlement ledger as impossible.
11. Failed capital/R&D amortization conventions are reported as contested **cost-allocation assumptions**, not hidden discretionary wages.
12. A hypothetical no-bargaining policy must expose whether resale and side payments defeat its intended allocation.

## 6. Open foundational question

Even with a perfect omniscient production-recording system, **duration is a physical invariant, whereas reducing unlike labor, training, land, materials and social obligations to one transferable scalar is partly a constitutional choice**.

The project should therefore seek the *least arbitrary, most falsifiable and globally reproducible* method for deriving embodied and reference human time; test whether production-time pricing plus separate rights to essential provision can sustain a modern society. It should not quietly reintroduce markets by negotiating an hourly wage or a fixed premium on fish.
