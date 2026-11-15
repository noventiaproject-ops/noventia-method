# Card facts

The exact definition of every fact on the developer card, and the stamps rule.

Published at https://noventia.xyz/docs/card-facts. Updated 2026-11-07.

These are the definitions the fact collector and card rules version 2 use for the developer card. N, X and Y are set in [Thresholds](thresholds.md). Every fact on a card comes with the transactions that prove it; see [Facts and proofs](facts-and-proofs.md).

## Definitions

| Fact | Definition |
|---|---|
| `onSolanaSince` | Timestamp of the wallet's earliest transaction |
| `tokensLaunched` | Pump.fun: tokens where this wallet is the creator in the create instruction. Other tokens: this wallet is the initial mint authority in the mint initialization. The fee payer alone does not count |
| `tokensAlive` | Launched tokens with at least one swap in the last 30 days. Proof: the latest swap transaction. Liquidity is pool state and has no transaction, so it is not part of the definition |
| `liquidityPulls` | Liquidity removed by the creator within N hours of launch. The card counts each launch with a pull once |
| `firstDayDumps` | Launches where the creator sold at least X% of their own allocation within 24 hours. Own allocation: tokens the creator received in the launch transaction (the dev buy on Pump.fun) plus any mint to the creator in the first 24 hours. Sold: swaps, and transfers to known exchange deposit addresses. Every sale by the creator in the first 24 hours counts, including tokens bought after launch, measured against the own allocation. With no own allocation the fact is "not applicable" for that launch. The exchange list is empty, so such transfers show up as `movedOutFirstDay` |
| `movedOutFirstDay` | Launches where the creator transferred at least X% of their own allocation to other wallets within 24 hours. Shown as a separate fact. It does not count as a sale. Known limit: selling through a second wallet is not caught |
| `longestHoldMonths` | Longest time the creator held their own token without selling it all ("all" means below 1% of their peak balance) |
| `fundingNote` | First SOL funding source, and how many other deployers it also funded (heuristic, labeled as such). Needs an endpoint that the collector does not use yet, so it is left empty |

## How the card words them

| On the card | Fact |
|---|---|
| On Solana since | `onSolanaSince` |
| Tokens launched | `tokensLaunched` and `tokensAlive`, for example "5, 1 alive" |
| Liquidity pulled | `liquidityPulls` |
| Sold on day one | `firstDayDumps`, for example "2 of 5 launches" |
| Moved out on day one | `movedOutFirstDay` |
| Longest hold | `longestHoldMonths` |

A launch without an own allocation is left out of both day one facts, and the card says so: "No dev buy in 1 launch, so day one facts leave it out."

## Stamps

One stamp per launched token, for the 3 most recent launches. Label: "Launch, {Month YYYY}". Value: "Liquidity pulled" if the launch has a pull, otherwise "Alive" or "No swaps in 30 days". A wallet with no launches gets one stamp: "On Solana since {Month YYYY}".

Token names and symbols do not appear on a card. Chain data is [hostile input](hostile-input.md).

## Not on the developer card

No branch level, no count of linked wallets, no Noventia ID for unclaimed wallets, no attestation hash. Attestation on Solana is planned for stage 1, Passport. See [Attestation](https://noventia.xyz/docs/attestation).
