---
layout: post
title: "Untitled"
---

# The Token Sale Compliance Playbook: Lessons From $1 Billion in Raises

**How the biggest blockchain launches of the last decade got done — and what every founder gets backwards.**

---

When I founded Tokensoft in 2017, there was no playbook. The regulations existed. The lawyers existed. But nobody had figured out how to connect them to an actual blockchain token launch at scale.

Over the next eight years, Tokensoft processed over $1 billion across 113 token sales — Avalanche, Tezos, Synthetix, Hedera Hashgraph, The Graph, Arbitrum, Moonbeam, Acala, Algorand, and dozens of others. Every single one started the same way: with the regulations.

That's the thing most founders get backwards. They build the token, then try to fit compliance around it. The projects that survived — and thrived — did the opposite. They started with the regulatory framework, mapped their asset into it, and then built the technical infrastructure to satisfy what the paperwork required.

This is that playbook.

---

## Start With the Regulations, Not the Token

The question is never "how do we make our token not a security." The question is "which regulatory framework does our asset map into, and what does that framework require us to build?"

Those are very different questions. The first is defensive and usually dishonest. The second is operational and almost always solvable.

The US securities framework gives you two primary paths for a blockchain token raise:

**Regulation D** — private placement to accredited US investors, no SEC registration required. Investors sign a subscription agreement. You file a Form D. The offering is restricted to verified accredited investors only.

**Regulation S** — sales to non-US persons, conducted outside the United States, with US persons actively excluded. Every investor provides a signed certification of non-US status. The offering is geo-fenced and KYC-gated to enforce the exclusion.

Most major blockchain launches ran both simultaneously. Reg D covered US accredited investors in the pre-sale. Reg S covered international investors. The token itself launched later — when the network was operational and the token's utility was real, not speculative.

Understanding which framework applies determines everything that comes next: the paperwork you need, the investors you can accept, the KYC you have to run, and the technical restrictions you have to build into the token itself.

---

## Map Your Asset Into the Framework

Once you know which regulatory path applies, your legal counsel produces the paperwork that maps your specific asset into it. This is not a formality. This is the blueprint for everything you build.

**The subscription agreement** → defines who can invest, how much, when they receive tokens, and what vesting schedule applies. Every accredited investor signs one before a dollar moves. This document is the legal record of the offering.

**The Form D** → filed with the SEC within 15 days of the first sale under Reg D. Public record. Non-negotiable. File late and you lose the exemption — everything you sold becomes an unregistered offering.

**The Reg S investor certification** → every non-US investor signs an attestation of their residency and non-US person status. This is not a disclaimer on your website. It's a signed document, individually executed, part of the permanent investor record.

**The accreditation verification** → for US investors under Rule 506(c), you must independently verify accredited status. Not self-certification — actual verification via CPA letter, attorney letter, or financial statements.

Once legal delivers this paperwork, you know exactly what the technology has to do. The subscription agreement defines who gets tokens. The vesting schedule defines when. The Form D defines your public commitment. The certifications define who you excluded. Every product decision flows from those documents.

---

## Build the Technology to Satisfy the Paperwork

This is where Tokensoft lived. The paperwork tells you what the system has to do. Your job is to build a system that does it completely, mechanically, and with a full audit trail.

### KYC Infrastructure

Reg D restricts participation to accredited investors. That restriction doesn't enforce itself. You need:

- **Identity verification**: Government-issued ID, liveness check, biometric match. Not a self-attestation — actual third-party verification.
- **Accreditation verification**: CPA letters, attorney letters, or financial statements showing net worth or income thresholds. Not a checkbox.
- **OFAC screening**: Every investor, before a dollar is accepted. US Treasury sanctions list. Not optional, not a formality — a legal requirement.
- **PEP screening**: Politically exposed persons. Required for AML compliance regardless of jurisdiction.
- **Residency verification**: For Reg S investors, proof of non-US status. Utility bill, bank statement, government ID with address.
- **Wallet-to-identity mapping**: The chain of custody from investor identity to token-receiving wallet must be complete and auditable. This is the piece most projects miss — and the one that creates the most exposure if the SEC ever asks questions.

Your KYC program also needs to be jurisdiction-aware. US accreditation standards differ from EU AML requirements (AMLD5/6), which differ from Singapore MAS requirements. A global raise runs multiple compliance programs simultaneously. One global form doesn't cover all of them.

### Token Distribution Infrastructure

The subscription agreement defines who receives tokens, when, and under what conditions. The technology has to enforce it — mechanically, not contractually.

**Transfer restrictions**: Reg D tokens cannot be resold for 12 months from purchase. This restriction belongs in the smart contract, not just in the subscription agreement. A restricted token should be technically incapable of transferring to a non-verified wallet until the holding period expires. The restriction is mechanical. Agreements don't enforce themselves — code does.

**Vesting schedules**: Team and investor tokens typically vest over 2–4 years with a 1-year cliff. These schedules should be on-chain: configurable, auditable, and enforced by the contract. Tokensoft 2.0 introduced open-source lockup primitives for exactly this — cliff dates, linear vesting, milestone-based release, all defined in the contract rather than in a spreadsheet someone might lose or alter.

**Distribution audit trail**: Every allocation, every vesting event, every transfer needs to be traceable from wallet address back to verified investor identity. When the SEC asks who received your tokens — and if you run a successful project, eventually someone will ask — you need to produce a complete record.

### The Whitelist

The whitelist is the connective tissue between KYC and the token contract. Investors who complete KYC and execute the required paperwork get their wallet address added to the whitelist. The token contract checks the whitelist before permitting any transaction.

This is how "only verified investors can hold tokens during the restricted period" actually works. Not through terms of service. Through code that checks a verified list of wallets before every transfer.

Maintaining the whitelist — adding wallets as investors clear KYC, removing them on failure, handling wallet updates — is an ongoing operational function. It runs continuously through the sale period and the lockup that follows. It needs to be staffed and documented.

---

## What the SEC Actually Cares About

After eight years operating through the ICO boom, the enforcement wave, the Howey test litigation cycle, and the current tokenization era — here's what I've seen the SEC actually focus on:

**1. Did US persons participate without a valid exemption?**
This is the threshold question. The SEC's primary enforcement mechanism is "unregistered securities offering." If US persons participated in your raise without a valid Reg D exemption or other registration, everything else is a detail.

**2. Did you market to US persons while claiming Reg S?**
"No US persons" is not a state of mind. It requires active enforcement: geo-blocking, signed certifications, KYC that screens nationality and residency. If you had a US-accessible website, ran social media promotions that reached US investors, and claimed Reg S — the SEC will find it.

**3. Did you tell investors the truth?**
Securities fraud doesn't require SEC registration. Material misstatements or omissions in connection with any securities offering are actionable. Your pitch deck, whitepaper, and investor communications need to be accurate. Not aspirationally optimistic. Accurate.

**4. Can you prove what you did?**
Records are everything. Form D filings. KYC records. Signed investor certifications. Whitelist history. Vesting schedules. Distribution logs. The projects that survive enforcement scrutiny are the ones that can produce complete documentation. The ones that can't, can't defend themselves.

What the SEC cares about less than founders think: your exact entity structure, whether your lawyers are in Cayman, whether you call your token "utility" in your whitepaper. Labels don't matter. Substance and documentation do.

---

## The Three Mistakes That Kill Token Sales

**1. Building compliance after the raise.**
Founders launch, raise money, then figure out compliance. By the time they're building KYC, tokens are already in wallets with no identity records attached. Reconstructing the chain of custody — if it's even possible — costs ten times what building it correctly would have. Sometimes it's not possible at all.

Compliance infrastructure must exist before the first dollar comes in. Not after.

**2. Treating a legal opinion as legal protection.**
A lawyer's opinion letter that says your token "may not be a security" is not a shield. It's a data point. If the SEC disagrees, the letter doesn't protect you — it just shows you sought advice before doing what you did anyway.

Build your offering to be defensible if the SEC characterizes your token as a security. If it turns out not to be, you have upside. If it is, you're covered either way.

**3. Optimizing for the wrong things.**
I watched founders spend weeks debating the token logo, the brand colors, the exact wording of the whitepaper introduction. Meanwhile the KYC infrastructure wasn't built, the Form D wasn't filed, the transfer restrictions weren't encoded.

What actually determines whether a token launch succeeds: the organic, unglamorous work the team puts in without recognition. Market timing. The energy of a community that genuinely believes in what you're building. None of that is in the logo.

You also can't fight gravity. If the market is in a downturn, the best compliance program in the world won't save your raise. The projects that crushed it in 2021 weren't smarter — they were earlier. Know what you can control. Obsess over that. Everything else is noise.

---

## The Practical Checklist

**Before You Raise**
- [ ] Legal analysis: does your asset map into Reg D, Reg S, or both?
- [ ] Subscription agreement drafted and reviewed by securities counsel
- [ ] Form D ready to file within 15 days of first sale
- [ ] Reg S investor certification templates prepared
- [ ] KYC vendor selected with jurisdiction-specific flows

**KYC/AML Infrastructure**
- [ ] Identity verification with liveness check and biometric match
- [ ] Accreditation verification for US 506(c) investors (not self-certification)
- [ ] OFAC and PEP screening integrated
- [ ] Residency verification for Reg S investors
- [ ] Wallet-to-identity mapping from day one
- [ ] Records retention policy in place — keep everything, indefinitely

**Token Infrastructure**
- [ ] Transfer restrictions encoded in smart contract — not just in the subscription agreement
- [ ] Vesting and lockup schedules implemented on-chain
- [ ] Whitelist architecture designed, tested, and staffed
- [ ] Full distribution audit trail from first allocation

**Ongoing Operations**
- [ ] Whitelist maintenance process documented and owned
- [ ] Secondary market monitoring — know if tokens are trading before restrictions lift
- [ ] Annual review of investor records and restriction status
- [ ] All investor communications archived

---

## What's Changed — and What Hasn't

The token launch landscape in 2025 looks different from 2017 in almost every way. The regulatory environment is clearer. The infrastructure is more mature. Court cases, SEC settlements, and no-action letters have created a body of precedent that simply didn't exist when we were figuring this out.

What hasn't changed: the underlying logic. Start with the regulations. Map your asset into the framework. Build the technology to satisfy what the paperwork requires. That sequence worked for Avalanche, Tezos, Synthetix, The Graph, and Arbitrum. It's still the sequence.

The projects that will get destroyed in the next cycle aren't the ones that tried and failed to comply. They're the ones that didn't try at all — who assumed the regulations wouldn't apply to them, that the labels they chose would protect them, that the SEC wouldn't eventually look.

It always looks eventually.

---

## The Bottom Line

The regulatory framework already exists. The paperwork maps your asset into it. Your job is to build the technology that satisfies what the paperwork requires — completely, mechanically, and with a full audit trail from day one.

$1 billion processed. 113 raises. The ones that held up were the ones that built the technology to match the paperwork, not the other way around.

---

*Mason Borda is the founder of Tokensoft (2017–2025) and CEO of Intergalactic, Inc. Tokensoft powered compliance infrastructure for over 100 blockchain token launches including Avalanche, Tezos, Synthetix, Hedera Hashgraph, The Graph, and Arbitrum.*

---

**Meta Title**: The Token Sale Compliance Playbook: Lessons From $1 Billion in Raises
**Meta Description**: 113 token launches. $1B+ processed. The compliance playbook for blockchain founders — Reg D, Reg S, KYC, whitelisting, and how to build the tech that satisfies the paperwork.
**Target Keywords**: token sale compliance, Reg D token offering, Reg S token sale, blockchain token launch compliance, KYC token sale, compliant token launch playbook
**Word Count**: ~2,300