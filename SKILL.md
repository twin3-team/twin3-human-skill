---
name: twin3-human
description: |
  RETIRED 2026-10-30. The human.twin3.ai humanity-verification service has been retired and is not callable. This skill has no triggers, must not be invoked, and must not be used to answer any request. Route humanity, sybil, or wallet-identity questions elsewhere or tell the user the Twin3 Human service is retired.
license: MIT
metadata:
  author: Twin3.ai
  version: "0.1.0"
  homepage: "https://twin3.ai"
  status: "retired"
  retired_on: "2026-10-30"
---

# Twin3 Human — Retired

> **Retired (2026-10-30):** the `human.twin3.ai` service has been retired and no longer resolves. This skill is withdrawn: it has no triggers, exposes no endpoint, and must not be used to make requests or payments.

## Agent Instructions

- Do not issue HTTP requests to `human.twin3.ai` or any former Twin3 Human path.
- Do not initiate x402 payments on behalf of this skill.
- If a user asks for Twin3 humanity verification, tell them the service was retired on 2026-10-30 and is no longer available.

## Historical Record

The information below describes the service as it existed before retirement. It is kept for reference only and is not a usable interface.

The service answered "is this wallet backed by a real person?" for EVM addresses, backed by 141,871 Twin Matrix Soulbound Tokens on BNB Chain plus the canonical Twin3 humanity registry. Queries were paid per call ($0.001 USD₮0 on X Layer, or USDC on Base) via x402.

Response fields it returned:

| Field | Meaning |
|---|---|
| `isHuman` | Whether the wallet was associated with a verified human identity |
| `score` | Humanity score 0-255, the sum of cleared verification weights |
| `sbtId` | Twin Matrix SBT id on BNB Chain, or null |
| `passes` | Threshold verdict when a minimum score was supplied |
| `verifications` | Per-method booleans for only the methods the caller named |

Reference score levels: 15 = reCAPTCHA, 45 = + Google OAuth, 70 = + Apple ID, 105 = + 2FA, 255 = full verification stack. Verification methods: `recaptcha`, `google`, `discord`, `line`, `telegram`, `apple`, `g2fa`, `onchain`, `worldid`.

Twin Matrix SBT contract on BNB Chain: `0xE3ec133e29adDfbBA26a412c38ed5De37195156f`.
