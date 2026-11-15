# Noventia method

How Noventia reads Solana: what a fact is and what proves it, how warnings and levels are made, what the rules count, and how a freeze is appealed. Everything here is the text Noventia publishes at https://noventia.xyz/docs, kept as plain files so a change of the method can be followed line by line.

Noventia builds a passport from what a wallet did, with a transaction behind every fact. The method has a few rules that hold everywhere:

* A fact is on a passport or a card only with a transaction behind it.
* There is no single score for a wallet or a person.
* A warning is shown with the facts behind it and says nothing about intent.
* Exchanges, bridges, launchpads and other shared services do not link wallets to each other.
* Every freeze has a case id and an appeal.

## Pages

### Concepts

| Page | What it says |
|---|---|
| [Facts and proofs](method/facts-and-proofs.md) | A fact is something that happened, with the transactions that prove it. No proof, no fact. |
| [Branches](method/branches.md) | A passport is split into branches, each with its own EP and its own level, and nothing adds them up. |
| [Warnings](method/warnings.md) | Four warning levels, each shown with the facts behind it, and the exact rules the developer card uses. |
| [Cases and the council](method/cases-and-council.md) | How to appeal a freeze or a mark today, and how the council planned for stage 3 is to decide cases. |

### Rules and thresholds

| Page | What it says |
|---|---|
| [Card facts](method/card-facts.md) | The exact definition of every fact on the developer card, and the stamps rule. |
| [Thresholds](method/thresholds.md) | Every number the card rules and the report metrics use, from one config file, confirmed on 18 October 2026. |
| [Rules versions](method/rules-versions.md) | Card rules are numbered, and each developer card records the rules version and the thresholds version it was made with. |
| [Known limits](method/known-limits.md) | What the developer card and the airdrop report method do not catch, what they cannot see, and what is not confirmed yet. |
| [Method changes](method/method-changes.md) | Each airdrop report names the method version it was measured with, and this page says what changed between versions and why. |

### Data

| Page | What it says |
|---|---|
| [Data sources and adapters](method/data-sources.md) | Every data source is an adapter that only emits facts with proofs. Today there is one, for Solana. |
| [Chain data is hostile input](method/hostile-input.md) | Token names, symbols, descriptions, links and metadata are written by anyone, so Noventia does not trust them. |

### Rules we hold

| Page | What it says |
|---|---|
| [Rules we hold](method/rules-we-hold.md) | The five rules that hold in every Noventia product at every stage, and the rule for transactions a user starts. |

## The rules in force

[rules/rules.json](rules/rules.json) is the answer of `GET https://core.noventia.app/v1/rules` as read on 2026-11-15: every rule with its version, its inputs and its outputs, the levels of each branch and the rules of a freeze. The core answers the same call live, with no key.

The addresses of services the core recognizes are in the repository `noventia-lists`, and at https://noventia.xyz/docs/what-we-recognize.

## Versions

Rules, thresholds and the report method are numbered, and every result names the versions it was made with. What changed between versions is in [Rules versions](method/rules-versions.md) and [Method changes](method/method-changes.md). The pages here follow the site at its commit `2dbaa0b`.

The thresholds of the signals that link wallets are not published. The pages say what each signal is and what it rests on.

## Questions, corrections, appeals

* A question or a correction of the method: open an issue here, or write to support@noventia.app.
* An appeal of a freeze or a mark: the Appeal button on the passport, or support@noventia.app with the case id. Appeals are not handled in issues, so that nobody has to name a wallet in public.
* A vulnerability: https://noventia.xyz/docs/reporting-vulnerabilities.

## License

The text is under [CC BY 4.0](LICENSE). Attribution: "Noventia method, https://noventia.xyz".
