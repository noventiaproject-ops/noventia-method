# Rules versions

Card rules are numbered, and each developer card records the rules version and the thresholds version it was made with.

Published at https://noventia.xyz/docs/rules-versions. Updated 2026-11-07.

Rules are pure functions: facts and thresholds in, card numbers and the warning level out. Same facts, same result. Rules do not read the network, the clock or the config themselves; time and thresholds arrive as input.

Every developer card records two numbers: the card rules version and the [thresholds](thresholds.md) version. An old card keeps the versions it was made with.

## Card rules version 2

In use since 17 October 2026. What changed from version 1:

* **Level 3.** High risk is at least one launch with a liquidity pull within N hours, or first day dumps in at least 2 launches. Version 1 also set level 3 for first day dumps in more than half of all launches; that clause is gone.
* **Not applicable.** A launch where the creator received no own allocation is "not applicable" for both day one facts. Its create transaction is kept as proof.
* **Later purchases.** Every sale by the creator in the first 24 hours counts against the own allocation, including tokens bought after launch.
* **Stamps.** The 3 most recent launches each get a stamp: "Liquidity pulled", "Alive" or "No swaps in 30 days". A wallet without launches gets "On Solana since {Month YYYY}". Fixed words only, months in UTC, proofs per stamp.
* **Exchanges.** While the list of exchange deposit addresses is empty, transfers to exchanges count as moved out.

## Card rules version 1

17 October 2026, earlier the same day. The differences are listed under version 2.
