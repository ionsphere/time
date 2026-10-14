# TIME — Vertical Slice & Prototype Plan
## Build the first twenty minutes, not the entire world

This is a **proposal**, not an implementation. The first version should test whether **watching people reclaim their own time feels like winning**. It should also reveal at least one weakness of the time economy without punishing the player for discovering it.

## One-sentence first-play promise

*“I built a bridge that never earns a coin, and it still feels like the most valuable thing I've ever constructed in a city builder.”*

## First playable: the river settlement

**Map:** one small isometric valley with two neighborhoods, a river, fields, forest, workshop, storehouse, one bridge site, footpaths, and a commons square. Prefer a fixed hand-authored map with a seeded simulation over procedural world generation.

**Population:** 80 individually scheduled residents across households; 50 take a relevant daily one-way route in the introductory scenario. Their needs and choices vary. Keep visuals abstract enough to simulate accurately before high-detail animation.

**Production chains:**
- food: farming -> harvest -> household consumption
- timber/tool supply: gather timber -> workshop fabrication -> construction/repair
- civic infrastructure: materials + construction labor -> footbridge -> upkeep and route savings

**Core choices:**
- maintain food supply now vs commit labor and timber to the bridge
- shorten the route via a bridge vs improve the existing road (different costs/benefits)
- spend discretionary hours on additional output vs leisure/care after the bridge opens

**Not required for the first playable:** multiplayer, generalized AI citizens using LLMs, a world economy, currencies backed by physical assets, markets, all career types, political simulation, procedural research, 3D terrain, museums, or advanced research projects. Architecture should leave space for them, not implement them prematurely.

## Exact 15–25-minute player journey

| Minute | Player experience | System demonstrated |
| --- | --- | --- |
| 0–2 | Intro flyover follows one resident making an absurd river detour; Time Pulse shows life devoted to travel and work. | Human diary / routing |
| 2–5 | Click a resident; inspect 24-hour diary and “why they travel.” Preview travel-time isochrones. | Human-centered affordance |
| 5–8 | Hover bridge: 300 standard-work-hours embodied estimate; predicted 25 person-hours saved per day; materials and upkeep required. Compare a cheaper road upgrade. | Cost vs time returned |
| 8–12 | Commit to bridge; workshop/farm bottlenecks become obvious. Reassign only *available willing* workers, procure timber, defer non-critical work. | Scarce productive capacity |
| 12–15 | Bridge opens; residents change routes; Time Pulse shows less travel. Credits do **not** jump. | Realized benefit, not currency mint |
| 15–20 | Advance 12+ days; compare simple payback with the actual impact after maintenance/changed travel behavior. | Honest counterfactual |
| 20–25 | A citizen chooses leisure instead of extra work; another helps on the farm. Compare town health/food/time results. | Productivity is not automatically leisure |

This sequence should work before broader campaign chapters exist.

## Presentation: three must-have interactions

### A. Click any person

**Diary:** 24-hour radial or stacked timeline with sleep, care, work, travel, free-choice activities, and unmet commitments. Hover a segment to reveal the location, route, contributing task, and consequences.

**After the bridge:** show a same-person “before/after” diary and where the saved minutes actually went. If extra labor or new trips consumed the savings, say so.

### B. Click any product or building

**Time Receipt:**

```
Bridge #1 — verified historical inputs
Labor on site                    120 standard h
Timber and tools (allocated)    180 standard h
----------------------------------------------
Historical creation receipt     300 standard h

Predicted avoided travel         25 person-h/day
Expected upkeep                   1 standard h/day
Simple gross payback             12 days
No new time credits are issued by opening it.
```

The illustrative receipt must match the selected seeded scenario (or show actual computed values when the user changes the plan). Distinguish `person-h` of travel, `standard h` of compensated production, and `TC` of account credits even if the numbers align in a trivial example.

### C. Open the town's time atlas

Overlay footpaths with resident traffic, reachable areas by walking time, commute bottlenecks, and daily minutes per household. Let users scrub “before / after” with no camera movement.

An optional “what changed?” compare panel shows labor, travel, free time, quality/access, physical resources, and net account positions **with the same seed**.

## Minimal simulation architecture

**Recommended path:** browser-playable TypeScript prototype with a deterministic headless domain simulation, thin renderer (e.g., Canvas/PixiJS), and UI view-model adapters. The economy cannot depend on animation timing. Avoid storing game state in UI components.

```
/core
  clock, deterministic rng, event log, scenario loader
  agents, households, diaries, needs, skills
  world map, tile graph, pathfinding
  inventories, production recipes, equipment and wear
  provenance graph, reference recipe catalog
  accepted work, double-entry ledger and civic budget
  counterfactual evaluator, metric aggregation
/game
  steward commands, constraints, action previews, tutorial objectives
/ui
  town map, resident diary, time receipt, atlas, time pulse
/scenarios
  tutorial-river.json
/tests
  determinism, conservation, bridge, credit, recipe, diary, accessibility
```

A scenario data file should define map, inventories, agents, schedules, technology, baselines, and expected outcomes; no hard-coded special behavior for the bridge. Placeholders are acceptable if data and rules are explicit.

**Update discipline:** fixed simulation ticks with a daily aggregation pass; deterministic route choice with stable tie-breaks, deterministic event order, auditable transaction posting, seeded stochastic deviations.

**Save/replay:** initial scenario + seed + timestamped player commands should reproduce outcomes. Snapshots accelerate rewind but do not replace the event history.

## MVP model decisions

- The bridge reduces route lengths and changes **actual agent time diaries**. Do not directly increment “freedom” as a collectible.
- No resource appears because a person works: production recipes consume physical inputs and actual labor capacity.
- No one is forced to work; if insufficient participants volunteer, projects pause.
- Historic allocated creation work may differ from efficient benchmark work; log both.
- Time credits change on accepted work/service settlement, not from idle time or gross “hours saved.”
- No claims of guaranteed resale value for historical certificates.
- No interest: loans have principal and default risk; optional credit lines require a funding institution.
- Needs must be physically satisfied: no fake abundance from positive ledger balance.
- One person cannot simultaneously travel, work, or provide childcare.
- An atlas highlight states its comparison baseline (e.g., same home/field and same residents without bridge).

## Acceptance criteria

1. A completely fresh user can identify what the bridge costs, what it saves, and why the savings are valuable **without opening the ledger**.
2. For the seeded introduction: the pre-bridge routing measurement is consistent with 50 commuters × 30 minutes each = 25 person-hours/day one-way, **when the scenario actually satisfies these numbers**.
3. Completing construction reduces observed travel time. A same-seed no-bridge counterfactual demonstrates the difference.
4. Daily person diaries total 1,440 minutes, without overlaps; travel path lengths/time reconcile with world geometry.
5. `Σ TC balances = 0` in the closed test world; no credits are generated by travel savings, non-consensual work, failed products, or unused projections.
6. Food, timber, equipment use, and completed construction reconcile with physical inventory and event logs.
7. A road-upgrade alternative has meaningfully different costs/benefits from the bridge; at least one plausible choice has a downside.
8. Altering the scenario seed or policies changes outcomes while identical replays match byte-for-byte canonical event summaries.
9. A player can inspect raw origin of every number on the bridge receipt and a resident's before/after diary.
10. Automated tests intentionally demonstrate **one limitation** of labor-time valuation (e.g., two equally costly site parcels attract unequal applicants and require an allocation rule).

## Milestones (scope gates, not promises of elapsed delivery time)

**M0 — Headless economics.** Build and test deterministic diaries, routing, production recipes, physical stock conservation, provenance, and closed double-entry TC accounts.

**M1 — Visible village.** Map, paths, animated agents, speed controls, needs and jobs, basic Time Pulse.

**M2 — The bridge.** Project previews, proposal/approval, constrained construction, before/after, counterfactual replay.

**M3 — Player comprehension.** Time Receipt, diary, Time Atlas, annotated tutorial, accessibility and playtesting.

**M4 — One uncomfortable trade-off.** Road vs bridge or food vs build; no perfect dominant strategy.

**M5 — Laboratory scaffold.** Deterministic scenario comparisons, policy toggles, metrics export. Only then prototype invention rewards, museums, land allocations, and AI.

## Future candidate expansions (not MVP promises)

- **The Box and the Land:** urban accessibility, property condition and depreciation, clinic location, congestion, equitable site allocation.
- **Workshop and Invention:** research fund, training, failed experiments, discovery prizes, finite verified productivity royalties.
- **Museum:** art production provenance vs events and services, capacity, delight without measurable labor savings.
- **AI transition:** automation, maintenance and data costs, distribution of productivity gains, skill bottlenecks, political pressure over free time.
- **Economic Laboratory:** same-world counterfactuals under conventional pricing/interest, time-based clearing, and hybrids; no rigged baselines.

## Evaluation and stop/go tests

Run blind first-time play sessions and ask:
- What did you gain from the bridge? (Desired answer: citizens’ travel time and optional use of that time.)
- Did the bridge issue new currency? (Desired answer: no.)
- Is a painting necessarily worth its creation hours to a buyer? (Desired answer: no.)
- If faster machinery eliminates human labor, what else might become scarce? (Expected: natural resources, sites, expertise, access, care, attention.)
- What trade-off did you regret, and why?

**Stop/go:** if players only watch gauges and cannot connect the economy to individual lived experiences, rework the presentation before adding deeper monetary mechanics. If every simulation “proves” the theory, add counterexamples before expanding.

See [Game Design](GAME_DESIGN.md) and [Economic Model](ECONOMIC_MODEL.md).
