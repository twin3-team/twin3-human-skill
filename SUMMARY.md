## Overview

> **Retired (2026-10-30):** the `human.twin3.ai` service has been retired and no longer resolves. This skill is withdrawn and is not usable; do not install or invoke it.

Twin3 Human was a humanity-verification API that answered "is this wallet a real person?" for any EVM address, backed by 141,871 Twin Matrix Soulbound Tokens on BNB Chain plus the canonical Twin3 identity registry. It no longer accepts requests or payments, and there is no replacement endpoint.

## Historical Score Reference

| Score | Verification stack the wallet had cleared |
|---|---|
| 0 | No Twin3 verification |
| 15 | reCAPTCHA (baseline anti-bot) |
| 45 | + Google OAuth |
| 70 | + Apple ID |
| 105 | + 2FA |
| 255 | Full verification stack (all methods including g2fa, onchain proof, optional WorldID) |
