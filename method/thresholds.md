# Thresholds

Every number the card rules and the report metrics use, from one config file, confirmed on 18 October 2026.

Published at https://noventia.xyz/docs/thresholds. Updated 2026-11-10.

All thresholds live in one file in the engine: `src/config/thresholds.ts`. Rules receive them as input and do not read the file themselves, so the same facts and the same thresholds always give the same result.

**Thresholds version: 2.** The version goes up on every change and is recorded next to every result.

**Confirmed 18 October 2026.** The owner confirmed every value below on that date.

## Card facts

These apply to the developer card, under card rules version 2.

| Threshold | Value | Used by |
|---|---|---|
| Alive: swap window | 30 days | `tokensAlive` |
| N: liquidity pull window | 72 hours | `liquidityPulls` |
| First day window | 24 hours | `firstDayDumps`, `movedOutFirstDay` |
| X: share of own allocation | 50% | `firstDayDumps`, `movedOutFirstDay` |
| Sold it all: below this share of the peak balance | 1% | `longestHoldMonths` |
| Days per month | 30.44 | `longestHoldMonths` |

## Warning levels

| Threshold | Value |
|---|---|
| High risk: launches with a liquidity pull | at least 1 |
| High risk: launches with a first day dump | at least 2 |
| Little history: wallet age | under 90 days |
| Little history: launches | fewer than 3 |

## Report metrics

These apply to the public airdrop reports. Each recipient is measured from its own first claim.

| Threshold | Value | Metric |
|---|---|---|
| Sold early: window | 24 hours | Sold or moved out in 24 hours |
| X: share sold or moved out | 50% | Sold or moved out in 24 hours, each counted apart and together |
| Holding checkpoints | 30 and 90 days | Still holding |
| Y: share still held | 50% | Still holding |

Went to exchanges has no threshold of its own and is not measured, because the list of exchange deposit addresses below is empty. Linked wallets are not measured in a report, because the signals need the funding source and the history of every recipient.

## Linked wallets

A project's list check and the passport freeze use one rule: two or more independent signals that link wallets of at least 3 owners. The thresholds of each signal are not published. See [Linked wallets](branches.md#linked-wallets).

## Exchange deposit addresses

None yet. An address enters the list only with its exchange and a public source for the attribution. Until the list has entries, transfers to exchanges count as moved out, and the report metric Went to exchanges is not measured. See [Known limits](known-limits.md).
