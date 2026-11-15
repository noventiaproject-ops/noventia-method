# Facts and proofs

A fact is something that happened, with the transactions that prove it. No proof, no fact.

Published at https://noventia.xyz/docs/facts-and-proofs. Updated 2026-11-07.

A fact is something that happened, recorded with its source and its proofs. On Solana a proof is a transaction signature: anyone can open it in an explorer such as Solscan and see the same thing.

If a fact cannot be proven by a transaction, it is not on a passport or a card. This is the first of the [rules Noventia holds](rules-we-hold.md): "Facts only with a transaction behind them."

## What a fact holds

| Field | Meaning |
|---|---|
| `factId` | Its id: kind, transaction signature and part |
| `subjectId` | Who or what it is about, for example `wallet:solana:<address>` |
| `kind` | What happened, for example `solana.tokenCreated` |
| `value` | The details, for example the mint and the time |
| `source` | The adapter that read it |
| `observedAt` | When it was read |
| `proofs` | The transaction signatures it comes from |

## Card facts the Solana adapter emits

| Kind | Proof |
|---|---|
| `solana.firstTransaction` | The wallet's earliest transaction |
| `solana.tokenCreated` | The create or mint initialization transaction |
| `solana.tokenMovement` | Each swap, transfer, mint or burn of a launched token |
| `solana.liquidityRemoved` | The removal transaction that pays the token to the creator |
| `solana.latestSwap` | The newest swap of a launched token |

## From facts to numbers

The adapter does not compute a card number or EP. It emits one fact per thing that happened. [Rules](rules-versions.md) count and combine facts. The proofs of a card number are the proofs of the facts it used, so every number on a card comes with the transactions behind it. On the passport, the EP of each branch also comes from facts. See [Branches](branches.md).

Where the facts come from is described in [Data sources and adapters](data-sources.md).
