# Twin3 Human API — Historical Record

> **Retired (2026-10-30):** the `human.twin3.ai` service has been retired and no longer resolves. This document is a historical record only; it describes no callable interface and must not be used to make requests or payments.

## Former Payment Terms

| Network | Network ID (CAIP-2) | Token | Token Contract | Amount per call |
|---|---|---|---|---|
| X Layer | `eip155:196` | USD₮0 | `0x779ded0c9e1022225f8e0630b35a9b54be713736` | 1000 (= $0.001) |
| Base | `eip155:8453` | USDC | `0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913` | 1000 (= $0.001) |

## Score Weights

| Weight | Verification |
|---|---|
| 15 | reCAPTCHA |
| 30 | Google OAuth |
| 25 | Discord |
| 10 | LINE |
| 30 | Telegram |
| 55 | Apple ID |
| 90 | 2FA (g2fa) |
| **255** | All of the above combined |

Verification method names: `recaptcha`, `google`, `discord`, `line`, `telegram`, `apple`, `g2fa`, `onchain`, `worldid`.

## Former Response Fields

| Field | Type | Notes |
|---|---|---|
| `wallet` | string (0x…40hex, lowercase) | Echo of the input wallet, normalized |
| `isHuman` | boolean | True if a Twin3 humanity verification existed for the wallet (i.e. SBT minted) |
| `score` | integer 0-255 | Humanity score (sum of verification weights) |
| `scoreFloor` | integer | Baseline weight (15 = reCAPTCHA) |
| `scoreSource` | string | `"firestore"` (canonical registry) or `"chain"` (on-chain SBT byte 0) |
| `sbtId` | integer or null | Twin Matrix SBT id on BNB Chain; null if the wallet had no SBT |
| `queriedAt` | string (ISO-8601 UTC) | When the verdict was computed |
| `passes` | boolean | Present only when a minimum score was supplied |
| `verifications` | object | Per-method booleans for only the methods the caller named |
| `verifiedAt` | string (ISO-8601) | SBT mint timestamp, when requested |
| `dimensionsFilled` | integer 0-256 | Non-zero Twin Matrix dimension count, when requested |

Former error codes: `invalid_wallet`, `invalid_min_score`, `invalid_check`, `invalid_include` (HTTP 400) and `internal_error` (HTTP 500).

## Score Source

1. **`firestore`** — the canonical off-chain registry, including off-chain verifications such as Apple ID and 2FA.
2. **`chain`** — byte 0 of the Twin Matrix SBT's `tokenURI()` SVG, mirrored by periodic batch jobs.

## See Also

- Twin3: [https://twin3.ai](https://twin3.ai)
- Twin Matrix SBT on BNB Chain: contract `0xE3ec133e29adDfbBA26a412c38ed5De37195156f`
