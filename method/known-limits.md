# Known limits

What the developer card and the airdrop report method do not catch, what they cannot see, and what is not confirmed yet.

Published at https://noventia.xyz/docs/known-limits. Updated 2026-11-07.

Every method has limits. These are the ones known today.

## What an airdrop report does not measure

* **Transfers to exchanges.** The list of exchange deposit addresses is empty, so these transfers count as moved out, and the metric Went to exchanges is not measured.
* **Groups of recipients funded from one source.** This needs the funding source of every recipient. The reports do not measure it yet.
* **Selling through a second wallet.** A transfer to another wallet counts as moved out.

## Where an airdrop report can be off

* **Sampling.** A report can measure a seeded random sample of the recipients instead of every one. It states the sample size, the seed and the margin of error at 95% confidence. The recipient count always covers every claim.
* **Holding.** Holding is the balance of the account that received the claim. A move to another account of the same wallet makes the later balance "not known", and the report leaves that recipient out of that metric and says how many were left out.

## What the developer card does not catch

* **Selling through a second wallet.** If the creator moves tokens to another wallet and sells there, the card shows a move out on day one. A move out does not count as a sale.
* **Sales on exchanges.** The list of known exchange deposit addresses is empty. A transfer to an exchange counts as moved out.
* **Funding.** The first SOL funding source needs an endpoint that the collector does not use yet, so the funding fact stays empty.

## What the developer card leaves out on purpose

* **Anything without a proof.** If a fact cannot be proven by a transaction, it is not on the card.
* **Token names and symbols.** Chain data is [hostile input](hostile-input.md); a card uses fixed words only.
* **Launches with no own allocation.** They are "not applicable" for the day one facts, and the card says so.

## Not confirmed on live data yet

The collector has been checked against one live wallet with no launches, trades or tokens. These parts of the data are not yet seen on a launching wallet:

* the instruction names of Pump.fun trades;
* how a mint initialization names the mint authority;
* which DEX programs Helius summarizes as a liquidity removal;
* how a new mint appears in token transfers.

Whether the data source returns incoming token transfers that a wallet did not sign is also not confirmed. For SOL it does.

## When the collector stops

If the collector cannot read a full history, it stops with an error instead of making a partial card. See [Data sources and adapters](data-sources.md).

## Heuristics

Report metrics such as farm clusters are heuristics and can be wrong. They are labeled as heuristics wherever they appear.
