# ⚒️ REFORGEPOOL · CMFD Miner

**CUDA-accelerated CommonFoundry / ForgeMatrix mining for NVIDIA GPUs.**

![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20WSL2-343a40) ![CUDA](https://img.shields.io/badge/Backend-NVIDIA%20CUDA-76b900) ![Official fee](https://img.shields.io/badge/REFORGEPOOL-0%25%20developer%20fee-0d9872) ![Other pools](https://img.shields.io/badge/Other%20pools-5%25%20developer%20fee-d18a21)

> **Release status:** Documentation published; verified release artifacts will be provided separately. Do not download unofficial binaries.

## Features

- NVIDIA CUDA mining with optimized SM86, SM89, and SM120 paths (compatibility and performance vary).
- Ten kernel candidates with optional `-autotune`.
- Live terminal dashboard: FW/s, GPU power, temperature, VRAM and accepted/rejected/stale shares.
- Automatic REFORGEPOOL relay selection or manual `-pool` override.
- Custom worker labels via `-worker`.
- Certificate-pinned TLS, Mainnet identity and 384-layer CUDA parity checks.
- Verified ForgeMatrix model download and GPU tuning telemetry limited to kernel-test results.

## Installation (Linux x86-64 / WSL2)

An official binary will be provided in [Releases](../../releases) **after final testing**. The ForgeMatrix model is approximately 6.4 GB; allow sufficient disk space and GPU memory. A working NVIDIA driver is required.

When an official release has been published, download its Linux executable and verify the supplied checksum before running:

```bash
sha256sum -c SHA256SUMS
chmod +x ./cmfd-miner-reforgepool-v1.0.0
./cmfd-miner-reforgepool-v1.0.0 --mine \
  -wallet "YOUR_64_HEX_CMFD_PAYOUT_ADDRESS" \
  -worker "my-gpu-01"
```

A manual pool URL must use a numeric IP and a TLS certificate fingerprint:

```bash
./cmfd-miner-reforgepool-v1.0.0 --mine \
  -wallet "YOUR_64_HEX_CMFD_PAYOUT_ADDRESS" \
  -worker "my-gpu-01" \
  -pool "cmfd+tls://NUMERIC_IP:PORT?pin=64_HEX_CERT_SHA256"
```

See [Installation & CLI](docs/QUICKSTART.md) and [Pool connections](docs/POOLS.md).

## Official global relay locations

| Relay | Location | Numeric IP | Port |
|---|---|---|---:|
| EU1 | London, United Kingdom | `212.86.105.165` | `19777` |
| EU2 | Bucharest, Romania | `79.108.166.58` | `10081` |
| US1 | Atlanta, United States | `192.175.23.44` | `18995` |
| US2 | Seattle, United States | `45.61.62.74` | `14318` |
| JP1 | Tokyo, Japan | `45.130.166.180` | `12669` |
| HK1 | Hong Kong | `103.195.6.10` | `12061` |

See [complete ready-to-copy pool URLs](docs/POOLS.md). These are **CommonFoundry Pool v2**, not Stratum, endpoints.

## Transparent developer fee

| Mining destination | Allocation | Developer route |
|---|---|---|
| Official REFORGEPOOL | **0%** | None |
| Compatible third-party pool | **95% user / 5% developer GPU work** | Developer's REFORGEPOOL session |

Developer fee is measured in computation, **not** the percentage of accepted shares. Real-world accounting and fallback behavior require final validation before public binary release.

## Telemetry and privacy

The miner transmits GPU tuning results, up to one result per kernel in a ten-kernel tuning session. Periodic mining telemetry is not uploaded. Device identifiers and the worker name may appear in tuning data; do not use confidential names as worker labels. Address-only pool mining does not require a payout private key if permitted by the pool.

## Licenses and legal notices

REFORGEPOOL-original components and the official packaged distribution are subject to the [REFORGEPOOL Proprietary License](LICENSE), **except where upstream or other third-party licenses grant independent rights**. CommonFoundry components remain available under their upstream MIT terms. Read [Third-party notices](THIRD_PARTY_NOTICES.md). The proprietary terms do not revoke any MIT rights.

## Disclaimer

Cryptocurrency mining can generate no revenue and depends on hardware, difficulty, availability and fees. Screenshots and benchmark numbers are not earnings guarantees. Verify downloads against official checksums.
