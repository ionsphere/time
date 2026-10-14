# TIME — The Hours We Give Back
## Game design document · v0.1

> **Pitch:** Build a living society whose success is measured by how much of life people reclaim. Every farm, house, road, artwork, machine, and invention has a traceable history of human effort. A non-speculative time-credit economy tracks accepted contributions; progress makes necessities cheaper rather than making money more expensive.

**Genre:** approachable isometric city builder + agent-based economic simulation + narrative thought experiment.  
**Audience:** players who enjoy city builders, production-chain puzzles, and systemic sandboxes; no economics background required.  
**Player fantasy:** not “become the richest mayor,” but “give a community its life back.”  
**Working title:** TIME: The Hours We Give Back.  
**Status:** game design, not an implemented prototype. Assumptions are deliberately falsifiable.

## The hook: the first bridge

A river separates 80 villagers from their fields. Each day, they take a long detour. The player can direct available productive effort to constructing a bridge, but doing so delays food storage and tool repairs.

- Project estimate: **300 standard-work-hours** of attributable construction, material, and equipment effort.
- Routing simulation: **25 person-hours saved per day**, conditional on who actually crosses.
- Simple payback: **12 days**, before repairs, disruptions, or opportunity costs.
- Actual payoff is made visible: villagers stop walking around the river and begin spending recovered time elsewhere.

The bridge does **not mint 25 credits per day**. It changes the underlying time diaries. Labor previously spent traveling becomes capacity to work, study, play, rest, or care for others. If villagers choose to work extra, the player sees more production; if they choose leisure, the player sees more living.

At the end of the tutorial: “You haven't earned 300 coins. You've returned 25 hours of life every day.”

## Design pillars

1. **Humans, not currency, are the protagonists.** Show daily routines, personal choices, and quality of life. Hours are finite time budgets, not health points or literal lifespan tokens.
2. **Everything has provenance.** Inspect any object and trace the attributable labor and physical inputs, through upstream tools and shared infrastructure.
3. **Productivity is visible progress.** A better technique reduces *new* production costs. Existing objects retain their historical creation records.
4. **Time saved isn't automatically earned.** Separately display historic effort, ongoing upkeep, counterfactual effort avoided, actual discretionary time, and transferable credit.
5. **Money is a settlement tool, not an investment game.** Time credits clear accepted contributions; hoarding, speculative resale, and compounding interest do not generate new productive output.
6. **No predetermined utopia.** Scarce land, finite materials, different abilities, risk, queues, bad projects, free-riding, and unfortunate inventions remain real.
7. **Player choices have moral texture, not preordained correct answers.** A faster city might be less pleasant; an efficiency victory might create fatigue or unequal access.
8. **Results must be reproducible.** Deterministic simulation seeds, event logs, counterfactual experiments, and a transparent metrics panel make the model auditable.

## The experience

The town starts small and grows across eras of capability, not literal historical periods. Workers have names, households, skills, preferences, needs, and individual daily schedules. Buildings, crops, workshops, infrastructure, public spaces, and machines occupy a traversable map. Residents route to jobs, shops, schools, clinics, exhibitions, friends, and recreation.

**Default presentation:** warm, legible, isometric miniature city; animated footpaths and work sites; understated technical overlays. Avoid grim “everyone wears wrist clocks” fiction. **Time is not lifespan.** It is what citizens can choose to do.

### Four primary views

| View | What player sees | Question answered |
| --- | --- | --- |
| **Living World** | Residents, walking routes, activity, construction, queues, downtime | What is happening to people? |
| **Time Atlas** | Travel-time isochrones, task duration, mandatory-work burden, local accessibility | Where does life go? |
| **Provenance Lens** | Selected object’s inputs, actual labor, allocated capital upkeep, original cost, current efficient reproduction cost | What did it take to create this? |
| **Commons Ledger** | Credit transfers, net positions, public-project obligations, unpaid work, defaults | Who owes what, and why? |

A persistent **Time Pulse** strip shows: population, average required work/day, average discretionary hours/day, household access to necessities, health/satisfaction, unpaid maintenance backlog, and civic credit position. Additional physical resource indicators warn about material depletion, energy constraints, and ecological damage.

**No top-line wealth score.** Victory is a balanced frontier of time autonomy, reliable necessities, social well-being, solvency, and environmental viability.

## The player role

The player is a **steward of the commons**, not the owner of everyone's labor. They can propose infrastructure, set transparent civic rules, fund research, plan roads and services, allocate limited shared supplies, and compare designs. Citizens have autonomy: they choose activities, accept or decline offered work, and can oppose or leave unfair arrangements. Story-mode town councils approve major interventions; sandbox mode can override consent for stress tests, with consequences shown.

This creates real gameplay: a project may have outstanding global time savings but benefit only one district or burden a small set of specialists.

## Core loop (each turn = one day; animated at accelerated real time)

1. **Observe** individual time diaries, unmet needs, queue lengths, physical inventory, and accessible services.
2. **Find friction**: repetitive manual tasks, transport detours, tool downtime, skill bottlenecks, housing maintenance, information gaps.
3. **Propose** a solution: tool, process redesign, bridge, housing, school, clinic, exhibition, research program, automation.
4. **Inspect its bill of time**: upstream production graph, direct labor, training, maintenance, risk, material inputs, estimated counterfactual saved time.
5. **Fund and schedule** it through accepted time-credit transfers, civic pooling, or constrained interest-free credit. Participation and physical input capacity matter.
6. **Run the world**. Observe behavior change, adoption, side effects, actual time use, reduced/new costs, and failures.
7. **Compare the forecast to reality**, update reference production recipes, then attempt the next improvement.

Surprise is essential: a new road may induce more trips, a shorter commute may increase social visits, a robot may shift labor to technicians, and a theater may attract visitors but increase congestion. The underlying arithmetic is transparent even when outcomes are emergent.

## Campaign structure: five acts

### Act I — The Detour (tutorial, ~20–30 minutes)
Build the bridge, maintain food supply, discover embodied hours vs hours saved, and open the Time Atlas. The player also learns why 25 hours saved daily is *not* 25 newly created credits.

### Act II — The Box and the Land
Expand housing. A house's **box** has labor/material provenance and a repair schedule; a **site** has accessibility profiles that change as amenities and transportation change. A seemingly “free” remote plot may impose recurring travel time. Land itself is not fabricated labor. Accessible plots require allocation rights, and congestion can make a dense center worse for some households.

### Act III — The Workshop and the Invention
Start with a slow manufacturing recipe. Offer training, automation, and research choices. A scientist works for weeks on uncertain outcomes. One invention halves the required labor per equivalent tool. New tools become cheaper; old tools' historical cost records remain unchanged. The scientist can receive wages, a fixed prize, and a **capped, finite share of verified avoided effort** collected from beneficiaries—never perpetual rent.

### Act IV — The Museum and the Commons
A painter spends 100 hours on a work nobody initially wants to acquire. That is historical effort, **not a guaranteed claim on anyone else's credits**. Later an exhibition uses curator time, space, security, maintenance, and visitor travel; ticket charges cover accepted service costs, with a bounded artist/creator payment if policy allows. Popularity affects attendance and queues, **not a retroactive rewrite of the painting's labor history**. Community events can improve well-being without saving hours.

### Act V — The Automation Dividend
Introduce increasingly capable AI and robots. Compare scenarios: reduce required human work, expand output, shorten a workweek, or concentrate benefits in a few households. A successful ending demonstrates both freedom from obligatory labor and credible institutions that maintain shared infrastructure. Bad endings include ecological collapse, skill atrophy, neglected care work, inaccessible essentials, or insolvent commons credit.

## Mission ideas: why the theory is interesting to play

| Dilemma | Visible consequence | Principle tested |
| --- | --- | --- |
| Build a bridge or repair irrigation? | Travel time vs food reliability | Projects compete for limited present effort |
| Mass-produce a phone, or build a repair service? | Upstream embodied time vs maintenance | Lifecycle cost matters |
| Make a factory 10× faster | Lower reproduction cost, fewer routine jobs | Freed time does not have to mean lost livelihoods |
| Grant a research prize or fund many uncertain studies? | Breakthroughs, failures, public knowledge | Discovery needs ex-ante support |
| Put a clinic downtown or in remote neighborhoods? | Waits, journey lengths, unequal access | Land benefit depends on use and accessibility |
| Exhibit an artwork | Visitor delight, curator costs, queues | Creation cost ≠ experienced value |
| Run 24-hour subscriptions or offer one-time software? | Hosting/support labor vs release/maintenance labor | Service pricing follows work actually performed |
| Issue too much civic credit | Claims exceed feasible future contribution | Credit is not magically stored human time |
| Let robots do everything | Abundance of reproducible goods, scarce land and attention | Time cost is not a complete theory of allocation |

## Winning and losing

There is **no single victory number**. Every campaign chapter defines minimum viable conditions (food, shelter, health, ecological constraints, credit solvency) and asks the player to improve the **time-autonomy frontier** while satisfying them. The player can finish with a high-work, high-output town or a low-work, lower-output town; both have visible trade-offs.

Primary indicators:
- **Necessary effort:** average hours per resident/day needed to supply an agreed basket of essentials, with demographic and household breakdowns.
- **Discretionary time:** actual free-choice hours after sleep, care, travel, and obligations, not a sum of saved-time estimates.
- **Access and quality:** share of residents reliably receiving necessary goods/services at acceptable quality.
- **Equity:** bottom-decile discretionary time and access, alongside averages.
- **Sustainability:** maintenance backlog, resource inventories, pollution, ecological limits, defaults.
- **Human experience:** relationships, well-being, culture, education, health, and participation.

A spectacular productivity number that hides an exhausted minority or failing clinic is not a win.

## Two modes

**Campaign** introduces the concepts as stories in a small coherent town. Players use the time economy from the outset and see why its rules exist.

**Economic Laboratory** uses the **same world, agents, resources, preferences, and random seed** to compare rulesets: time-based contribution clearing, a conventional price/interest economy (stylized, not a straw man), and optional hybrids. The game can show when a conventional market allocates a scarce resource better, when a fixed cost benchmark causes a queue, or when a time-credit scheme cannot handle a rare specialist. Every comparison must disclose policy and modeling assumptions.

## What the game must *not* imply

- A person-hour has an objectively equal economic output across tasks or workers.
- Historical embodied time is a guaranteed minimum resale price or a floor anyone is obliged to pay.
- Every useful experience saves time (art, medical advances, and relationships often do not).
- Increasing efficiency produces currency, rather than reducing labor requirements.
- Time is physically conserved across people or bankable like electricity.
- Scarce land, mineral stocks, attention, skill, and ecological capacity can be valued solely by labor time.
- A “better” economy removes disagreement over public priorities.

The point is not to prove the theory correct. It is to let players **discover its surprising strengths and stress its weaknesses**.

## Accessibility and feel

- Moment-to-moment choice should be comprehensible from an object's *time receipt*, not from a spreadsheet.
- Optional advanced panels reveal full input-output graphs, benchmark recipes, counterfactual calculations, and ledger equations.
- Play/pause and 1×/4×/16× simulation speed; replay and rewind by saved deterministic snapshots.
- Color-blind-safe annotations (numbers and patterns, not color alone); keyboard and touch-readable UI.
- Gentle failure recovery through policy rollback, migration, and new proposals; no catastrophic unwarned currency wipeouts.
- Soundscape shifts from machinery/commutes toward everyday community life as obligations shrink—not because work is bad, but because choice increases.

## Open questions to test in prototype

1. Can standardized accepted output be priced in task-equivalent minutes without rewarding slowness or undervaluing specialists?
2. Does a civic clearing ledger remain solvent under default, sickness, migration, and emergencies without interest?
3. How does the game allocate oversubscribed unique housing sites at non-auction prices?
4. Can we estimate counterfactual saved time without double-counting overlapping inventions or induced demand?
5. What rewards basic science and cultural work when outcomes are uncertain or not time-saving?
6. What prevents hoarding, rationing, or waiting-list favoritism from becoming new forms of wealth/power?
7. Is enough of the economy visible at household scale to make the simulation legible and fun?

See [Economic Simulation Specification](ECONOMIC_MODEL.md) and [Vertical Slice](VERTICAL_SLICE.md).
