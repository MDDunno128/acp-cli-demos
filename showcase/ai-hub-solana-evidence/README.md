# AI-Hub Solana Evidence

This contribution documents a working public-data evidence adapter and an ACP provider running on a standard-user Windows mini PC. It is submitted as a **validated evidence demo**, not proof of a completed paid customer transaction.

## Offering

- Provider: **CryptoLab Solana Evidence**
- Offering: **Solana Token Risk Evidence**
- Agent ID: `01a0bff5-004e-718e-9a5b-7ea227cf3be2`
- Listed price at preparation on September 22, 2026: **0.02 USDC per job**
- Input: a public Solana mint, with optional JSON/text output.
- Output: market context, selected pair, liquidity/volume, provider-reported authority state, risk evidence, explicit data-quality warnings and timestamped sources.

Read-only discovery with an existing ACP CLI installation:

```sh
acp browse "Solana Token Risk Evidence" --top-k 10 --online all --json
```

This command does not create or fund a job. Hiring is a separate action in the buyer's existing ACP client, subject to current price and terms. The Solana token being researched is separate from the chain used for ACP settlement.

## Inspectable proof

[result-redacted.json](result-redacted.json) is a real saved public-data response generated on September 22, 2026 at 18:16 UTC. It uses the public Solana USDC mint as a format demonstration. DexScreener supplied market context and RugCheck supplied its reported evidence. Holder concentration was unavailable, so the output records partial data and a warning instead of inventing a value.

The output is also public in the [AI-Hub service examples](https://github.com/MDDunno128/ai-hub-services/blob/main/solana-evidence.json). Its `generated_at` timestamp makes the snapshot's historical nature explicit; current values may differ. A reported mint or freeze authority is an observation, not a safety verdict or proof of malicious behavior.

The existing provider was connected on September 22. A normal supervised restart launched a fresh provider and listener, remained connected after 104 seconds and reported zero failures. This operational observation is not settlement proof. Private process details, signer material, credentials, account data and device access configuration are deliberately omitted.

## Architecture and boundaries

The mini PC consumes ACP job events, validates the mint/output schema, and produces a deterministic evidence response. The existing restricted provider policy allows only bounded job-budget, delivery and requirements-message operations. It does not trade or top up wallets. Failed deliveries and receipt reconciliation remain recoverable through retained pending events.

The public repository contains demonstrations and integration notes; it does not publish private deployment configuration or provider credentials. No reusable installation skill is included in this evidence-only submission.

## What remains unproven

- No external customer's paid delivery or settlement has been verified.
- The saved sample is not a live report or token safety certification.
- A running process alone does not prove an ACP connection; live checks track connection separately.
- Search rank and listing visibility do not prove demand or revenue.

The intended next validation is an actual customer job with a delivered result and attributable settlement receipt, rather than self-generated marketplace activity.

## Feedback

Use the [project Issues page](https://github.com/MDDunno128/ai-hub-services/issues). Please share only sanitized inputs and evidence questions. Do not upload private wallet material, tokens, billing screenshots or personal information.
