# Deadstock 2121

A browser game about finding, hoarding and trading rarities in a drowned, neon-lit port city. "Deadstock" is collector slang for old stock that never sold and sat in a warehouse for decades. In 2121 it is the only thing left worth owning.

This document is the vision and the plan. The playable prototype lives in `index.html` next to it.

## The pitch

You are a picker. You crawl through flooded malls, dead data centres and collapsed archives looking for things people made a century ago: vinyl pressings, boxed toys, sealed game cartridges, first-issue magazines, prototype hardware, numbered prints. None of it does anything useful any more. All of it is worth money to the right person.

Credits buy you access to better districts and better traders. Better districts give you rarer finds. Rarer finds let you trade up. The loop is slow and greedy, like real collecting: every deal feels like a small heist.

## The world: Estuary, 2121

The city is never fully named by its residents. They call it Estuary. The old waterfront drowned in the 2060s and the money moved upward into climate-controlled towers. Everything below the water line was left to pickers, divers and squatters.

Culture runs on nostalgia. The last physical media was manufactured around 2040. Everything after that is streamed, licensed and revocable. People with money pay enormous sums for the things that cannot be revoked: a record, a cartridge, a toy still in its box. The trade in these objects is half black market, half religion.

### Districts

Each district has its own loot mix, entry toll and risk. Higher districts are locked behind collector rank.

| District | What it was | What you find there | Toll | Unlocks at |
|---|---|---|---|---|
| The Stacks | The national media archive, forty floors, half open to the rain | Magazines, records, zines | free | start |
| The Submall | A three-level shopping centre under two metres of estuary water | Toys, games, some tech | low | start |
| Cold Racks | A decommissioned data centre still running its own cooling | Tech, dev kits, cartridges | medium | Picker |
| Pressing Plant | The last vinyl plant on the peninsula | Records, test pressings, lacquers | high | Dealer |
| Uptown Vault | Private storage towers whose owners stopped paying | A bit of everything, but the good versions | very high | Curator |

### Categories

Six categories, each with a base value and its own market index that drifts every day.

- **Records**: pressings, test pressings, promo white labels, misprints
- **Toys**: figure lines, chase variants, sealed boxes, convention exclusives
- **Games**: cartridges and discs for consoles that no longer exist, big box editions, demo discs
- **Magazines**: first issues, cover variants, issues with the poster still inside
- **Tech**: handhelds, pagers, decks, prototypes and dev units
- **Art**: zines, risographs, screen prints, holo-posters, numbered and signed

### Rarity and condition

Six rarity tiers with steep value multipliers. Mythic items are named grails with their own lore and appear once per game.

| Tier | Drop weight | Value multiplier |
|---|---|---|
| Common | 50 | 1x |
| Uncommon | 28 | 2.2x |
| Rare | 14 | 5x |
| Epic | 6 | 14x |
| Legendary | 1.2 | 45x |
| Mythic | 0.05 | 160x |

District rarity boosts and the Eye skill (capped at 30) multiply the weights upward tier by tier, so the top tiers only become realistic in the later districts.

Condition multiplies on top: Mint 1.6x, Near Mint 1.25x, Good 1x, Worn 0.7x, Damaged 0.4x.

An item's value is `category base × rarity × condition × today's market index for that category`.

## The characters

Traders are bots with personalities. Each one wants some categories and pays more for them, is cold on others, has a cash reserve that refills daily, a patience limit for haggling and a reputation with you that improves with fair deals.

- **Kessandra Vôo** runs a sound system at the night market. Pays over the odds for records. Does not care about toys.
- **Old Dinis** keeps a toy stall in the dry part of the Submall. Toys and magazines. Thinks tech is junk.
- **Nullpoint** is a vending kiosk with an attitude and a wallet. Tech and games. No patience for haggling.
- **Mags Ferraz** archives zines in the Stacks. Magazines and art. Pays little for anything else.
- **Tio Rafa** runs the dock pawn shop. Buys anything at a bad price. Always has cash. Your floor when you are desperate.
- **Baron Ozu** is an uptown fixer. Only deals in epic and above. Pays a fortune. Opens once you are a Dealer.

Later, player characters take these seats and the bots become the long tail of the market.

## The loop

Each day you get six action points.

1. **Scavenge** a district (2 points plus the toll). Roll for loot by the district's category mix and rarity boost. Your Eye skill grows with every find and nudges the odds toward rarer tiers. Sometimes you find nothing. Sometimes something goes wrong: a drone sweep, a collapsed floor, a toll collector who wants more.
2. **Trade** at the night market (free). Sell to the trader who wants that category. Buy what another trader undervalues. Swap an item for an item and settle the difference in credits. Haggle: every trader has a hidden reservation price, and you have a few rounds to find it before they lose interest.
3. **Take assignments** from the job board (free to accept). Fetch a specific category and rarity, deliver a bulk lot, run a courier job across town for 2 points, or appraise an item blind and get paid if your guess lands within 20%.
4. **End the day.** Markets drift, news hits a category, traders restock and refill their cash, new jobs post, action points reset.

## Progression

Reputation comes from completed assignments, fair trades and rare finds.

| Rank | Reputation | What it opens |
|---|---|---|
| Scrapper | 0 | The Stacks, the Submall, four traders |
| Picker | 50 | Cold Racks |
| Dealer | 150 | Pressing Plant, Baron Ozu |
| Curator | 400 | Uptown Vault |
| Archivist | 1000 | The Register |

Credits are a sink as well as a score: tolls, storage locker upgrades, and eventually buying grails from Ozu.

The soft ending: reach Archivist with a Mythic grail in your vault and your name goes on the Register, the list of collectors whose collections are recorded for the city. The game keeps going after that.

## Design rules

- **Every item is text.** No art pipeline. Names are generated from category tables with years, pressings, variants and lore notes. This keeps the game cheap to extend and gives every find a line worth reading.
- **Trading beats grinding.** Scavenging is capped by action points. Trading is free. The best players make money by moving items between traders, not by digging more.
- **Bots must be beatable but not exploitable.** Each trader's want multiplier is public. Their reservation price is not. Rep narrows the gap but never removes it.
- **One screen, phone first.** Everything happens in tabs over a persistent feed. No page loads.

## Roadmap

### Done in the prototype (`index.html`)
- Character creation with four backgrounds
- Five districts, scavenging with loot tables, Eye skill, mishaps and on-the-spot sale offers
- Six categories, six rarities, five conditions, named Mythic grails
- Six bot traders with wants, cash, patience and reputation
- Haggling in both directions, item-for-item swaps with credit top-ups
- Four assignment types with expiry
- Daily market drift with news events and sparklines
- Rank progression, district unlocks, storage upgrades, the Register ending
- Local save, export and import as text

### Next
1. **Trader dialogue and memory.** Traders remember your last three deals and comment on them. Lowball them repeatedly and their opening offers get worse.
2. **Provenance.** Items carry a history: who owned them, which district they came from. Provenance adds value and makes forgeries possible (a new risk on buys).
3. **Sets and collections.** Completing a set (all issues of Pixel Weekly year one, the full Astro Rangers line) multiplies the set's value and unlocks a display case.
4. **Auction nights.** Weekly event where traders and the player bid on a lot in real time against bots.
5. **Multiplayer.** Replace bot traders with other players on the same market. The server owns the market indexes and item registry; items are unique and cannot be duplicated. Trades go through an escrow screen. Bots remain as liquidity at the bottom of the market.
6. **A map.** Replace the district list with a scrolling pixel map of Estuary and travel costs that depend on distance.

## Technical notes

- Single HTML file, no build step, no dependencies. Vanilla JS with a plain state object rendered through template strings.
- State is saved to `localStorage` after every change. Export and import move saves between browsers.
- For multiplayer the same state shape splits into a server-owned world (market, registry, jobs) and client-owned player state (vault, credits, rep).
