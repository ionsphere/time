# TIME — The Hours We Give Back

**A game about building a world where progress gives people more of their lives back.**

TIME is a proposed isometric city-building and economic simulation. Every manufactured object has a verifiable history of human work; technologies can reduce the effort needed to make new objects; infrastructure can free time previously wasted on transport or repetitive tasks. A time-credit system tracks accepted contributions without mining, speculative appreciation, or interest. Crucially, **saving time doesn't automatically mint currency**.

The player is a steward of a living settlement, making decisions about roads, homes, food, tools, research, art, public services, and eventual AI-driven automation. The win condition isn't a giant bank balance: it is a sustainable community with reliable necessities, real discretionary time, cultural life, and fair access to resources.

## Start here

- [Game Design](docs/GAME_DESIGN.md) — core experience, city-builder loop, acts, puzzles, player incentives, visible metrics, and experimental mode.
- [Economic Simulation](docs/ECONOMIC_MODEL.md) — time definitions, cost provenance, credits, invention rewards, land/access, counterfactuals, and auditable invariants.
- [Vertical Slice](docs/VERTICAL_SLICE.md) — first playable, the bridge scenario, interface, implementation boundaries, and acceptance criteria.

## The first level

A river forces villagers to spend precious time traveling around it. You decide whether to build a bridge, improve the path, or prioritize other needs. The bridge consumes productive hours and materials. If it succeeds, people spend less time walking and choose how to use their regained hours. **No coins spring out of the bridge.** The payoff is visible in people's lives.

## Important distinctions

- **Historical creation effort** is not an item's guaranteed resale price.
- **Reference production effort** changes when feasible technology improves; historical records do not.
- **Avoided work** is not automatically **actual leisure gained**.
- **A credit** is a transferable claim settled between parties, not a stored hour of someone's life.
- **Human-time accounting** does not resolve every scarcity, quality, fairness, or cultural-value question.

The game should explore the strengths *and* failure modes of such an economy, not predetermine that it always wins.

**Status:** design proposal. No gameplay implementation yet.
