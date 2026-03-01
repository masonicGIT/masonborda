---
layout: post
title: "A Breakdown of the DTCC No Action Letter"
subtitle: "What's under the hood — with diagrams"
canonical_url: https://themasonic.substack.com/p/a-breakdown-of-the-dtcc-no-action
---

DTCC received no action relief for tokenized securities. I've launched $1B of compliant securities on the blockchain since 2017 — both exempt and SEC registered. Let's do a deep dive to see what's happening under the hood.

## Key Definitions

The meat of the no action letter lives in this paragraph:

*"A DTC Participant with a Registered Wallet would be able to instruct DTC to tokenize the DTC Participant's security entitlement to certain eligible securities ("Subject Securities") currently credited to the DTC Participant's Account. Upon acceptance of a Tokenization Instruction, DTC would debit the Subject Securities from the DTC Participant's Account and credit them to the Digital Omnibus Account... DTC would then use its Factory system to mint and deliver to the DTC Participant's specific Registered Wallet a token representing the DTC Participant's security entitlement."*

Let's decompose the terminology:

- **DTC Participant** — A user with a DTC account. Account creation includes agreement to terms, submission of identifying information for Bank Secrecy Act compliance.
- **Registered Wallet** — The blockchain address designated to receive assets on-chain.
- **Subject Securities** — Securities DTCC has determined are eligible to be tokenized.
- **Digital Omnibus Account** — The (likely FBO) account where securities are held when in tokenized form. Bankruptcy remote. This is the right structure.
- **Factory** — The engine managing the smart contract: determines when to mint, burn, or pause wallets.

## How the Token Gets on the Blockchain

**Step 1: Purchase.** The no action doesn't contemplate purchasing directly from the blockchain — the user starts with cash in their account. $100 in a bank account transfers to DTC's designated receiving account. A requisite amount of eligible securities (net of fees) transfers to the user's account.

**Step 2: Tokenization.** The user hits "tokenize." The $100 of securities moves from the user account to the Digital Omnibus Account (an FBO structure, bankruptcy remote). The Factory mints the token and delivers it to the user's registered wallet.

**Step 3: You now have $100 of an eligible security on the blockchain.**

**Step 4: Redemption (DeTokenization).** The user burns the token out of their wallet, or sends it to a designated burning wallet (which reduces some risks). The securities move from the Omnibus Account back to the user's individual securities account.

## What's Actually Significant Here

The no action does not require individual SEC approval of every stock that goes on the blockchain. That's actually a big deal. If you're a company registering stocks on the blockchain individually today, I recommend you stop and adopt a model similar to what DTCC has created here — and get a no action.

This is a highly scalable model. The Omnibus structure also allows DTCC to have securities on multiple blockchains while using a single FBO account, streamlining operational management and reconciliation.

The no action references ERC-3643 — so this is designed for EVM-compatible chains. Just Ethereum addresses.

The no action also allows users to register unlimited wallet addresses — which likely means exchanges are the primary DTC Participants, acting on behalf of many individual users on their platforms. This fits DTCC's existing market infrastructure and role.

## A Note on Transfer Agents

The no action doesn't address transfer agents directly, but it provides the tools necessary to perform transfer agent functionality on top of it. Later in the document it states that "DTC can take steps to address any erroneous entries, lost tokens, or malfeasance" — which is one of the main services a transfer agent provides.

## The Bottom Line

DTCC has created the foundational infrastructure for tokenized securities at scale. It's fully collateralized (every on-chain share has a traditional equivalent in the omnibus account), scalable, and doesn't require individual SEC approval per security.

The architecture is right. Now we build on top of it.
