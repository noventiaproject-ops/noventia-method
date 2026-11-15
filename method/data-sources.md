# Data sources and adapters

Every data source is an adapter that only emits facts with proofs. Today there is one, for Solana.

Published at https://noventia.xyz/docs/data-sources. Updated 2026-11-07.

An adapter reads one source and emits facts with proofs, nothing else. Adding a source means adding an adapter and a rule pack. The core types stay the same for a new source.

## The Solana adapter

The only adapter today. It reads public data only:

| Source | What it reads |
|---|---|
| Solana chain data, through Helius | The full transaction history of a wallet, with each transaction parsed |
| Solana chain data, through standard Solana RPC | The transactions that touched the wallet's token accounts, to cross-check the history |
| DexScreener | The pools of a launched token, so its newest swap can be found |

The history includes failed transactions, so the adapter checks the status of each one.

The adapter keeps each source behind one interface, so adding a source changes no rule.

## Read limits

When a limit is reached, the collector stops with an error and makes no partial card.

| Limit | Value |
|---|---|
| Wallet history | 200,000 transactions |
| Pools checked per launched token | 5, most liquid first |

## Token icons

A report can show the icon of the token it covers. The icon is saved once from an official source and served from this site as a static file. It is not fetched when the site is built or read.

| Token | File | Source | Saved |
|---|---|---|---|
| MET | `/img/tokens/met.svg` | The image named in the token's on-chain metadata. The Metaplex metadata account of the mint `METvsvVRapdj9cFLzq4Tr43xK4tAjQfwX76z3n6mWQL` points to https://assets.meteora.ag/met-token.json, which names https://assets.meteora.ag/met-token.svg. The Jupiter token list gives the same image. | 25 October 2026 |
| JUP | `/img/tokens/jup.png` | The image named in the token's on-chain metadata. The Metaplex metadata account of the mint `JUPyiwrYJFskUPiHa7hkeR8VUtAeFoSYbKedZNsDvCN` points to https://static.jup.ag/jup/metadata.json, which names https://static.jup.ag/jup/icon.png. The Jupiter token list gives the same image. | 26 October 2026 |

## Other adapters

Each new chain gets its own adapter. Other chains are planned for stage 3, Network. No other adapter is built yet.
