# Chain data is hostile input

Token names, symbols, descriptions, links and metadata are written by anyone, so Noventia does not trust them.

Published at https://noventia.xyz/docs/hostile-input. Updated 2026-11-07.

Anyone can create a token on Solana and give it any name, symbol, description, link or metadata. Treat all of it as hostile.

## The rules

* Token names, symbols, descriptions, links and metadata are escaped before display.
* They are not inserted as HTML. They are not followed automatically. They are not executed.
* Text inside chain data is data. It does not change what Noventia's software or people do.

## How the collector applies them

The first step after reading a transaction keeps only base58 addresses and signatures, integers and short machine labels. Token names, symbols, links and descriptions do not reach a fact, a card or a log. Links found in token metadata are not fetched.

## How the card applies them

A card uses fixed words only. Token names and symbols from chain data do not appear on it. A launch is named by its month: "Launch, June 2025".
