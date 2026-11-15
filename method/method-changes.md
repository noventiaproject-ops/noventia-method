# Method changes

Each airdrop report names the method version it was measured with, and this page says what changed between versions and why.

Published at https://noventia.xyz/docs/method-changes. Updated 2026-11-07.

The airdrop report method is numbered. Every report page names its method version next to its title, and every number on it comes from that version. A report keeps its version until it is measured again. The [thresholds](thresholds.md) have their own version number.

The published report on MET Season 1 now shows its sample size and a range at 95% for each line, from the Wilson score interval. Its numbers are unchanged.

On 26 October 2026 the MET Season 2 and JUP reports went live for a few hours by mistake, before the projects had 5 working days to reply. We returned them to draft. MET Season 2 was published on 30 October 2026, after Meteora replied. The JUP report was published on 2 November 2026.

## Method version 3

* **Read window.** From 26 October 2026 the claim account is read from the claim to the end of the last checkpoint, at most 5,000 transactions. Version 2 read at most 1,000 transactions from the account's first one, which left out recipients whose accounts had a long history before the claim.
* **Deposits.** "Still in the claim wallet or deposited in a program" counts only deposits made from the claim on, at most what the claim account held right after the claim, so a withdrawal from a pool before the claim or tokens bought later no longer change it.

These changes affect MET Season 2, which was published on 30 October 2026 with method version 3. Season 1 numbers are unchanged. The report on the Jupiter JUP airdrop, published on 2 November 2026, also uses version 3.

## Method version 2

In use since 24 October 2026. The report on the Meteora MET airdrop uses it.

What changed from version 1:

* **What the thresholds are shares of.** A sale, a move and holding are measured against the MET the claim account held right after the claim: what it already held plus the claim. Version 1 used what was claimed.
* **SOL counts net.** A transaction is a sale when the wallet got a different token back, or at least 0.01 SOL. That SOL is now net of what the wallet sent in the same transaction, so its own wrapped SOL coming back, or a rent refund, is not a sale.
* **One amount per transaction.** Only the change in the claim account's balance in a transaction counts. Tokens that a swap route passes through the account and sends on in the same transaction are neither a sale nor a move.

Why:

* In the report's sample of 1,056 recipients, 13 already had MET on the claim account before they claimed. Version 1 counted that MET as if it came from the claim.
* A check of every sale and move transaction in the sample against the claim account's balance before and after it found 4 transactions where version 1 counted more than the balance fell. With version 2, every counted amount equals the change in the balance, apart from a claim made in the same transaction, which the balance change also holds.

The report lists the recipients version 2 moved, line by line, under "Changes from version 1" in its Method section.

## Method version 1

From 19 October 2026 to 24 October 2026. The first draft of the report on the Meteora MET airdrop was measured with it, on 19 October 2026. No published report uses it. The differences are listed under version 2.
