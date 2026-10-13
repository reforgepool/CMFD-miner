# Installation and CLI

**Status:** Public binaries are not released yet. This guide applies once a verified official Linux build appears under GitHub Releases.

## Requirements

- Linux x86-64, including Ubuntu in WSL2.
- NVIDIA GPU and compatible NVIDIA driver.
- Disk space for the approximately 6.4 GB model and verified caches.
- 64-character hex CommonFoundry payout address.

## Quick start

After downloading and verifying a release alongside its SHA256SUMS file:

```bash
sha256sum -c SHA256SUMS
chmod +x ./cmfd-miner-reforgepool-v1.0.0
./cmfd-miner-reforgepool-v1.0.0 --mine \
  -wallet "YOUR_64_HEX_CMFD_PAYOUT_ADDRESS" \
  -worker "rig-01"
```

Run `--help` for options supported by your installed release.

| Argument | Purpose |
|---|---|
| `--mine` | Start pool mining |
| `-wallet ADDRESS` | Payout address |
| `-worker NAME` | Optional worker name; 1–32 letters, digits, dots, underscores or hyphens |
| `-pool URL` | Optional numeric IP + pinned TLS Pool v2 server |
| `-autotune` | Optional full 10-kernel comparison |
| `--help` | CLI usage |

When `-pool` is omitted, the miner selects an official REFORGEPOOL relay.

### Third-party pool

```bash
./cmfd-miner-reforgepool-v1.0.0 --mine \
  -wallet "YOUR_64_HEX_CMFD_PAYOUT_ADDRESS" \
  -worker "rig-01" \
  -pool "cmfd+tls://NUMERIC_IP:PORT?pin=64_HEX_CERT_SHA256"
```

Developer work allocation: **0%** on REFORGEPOOL; **5%** on other supported pools. These are CommonFoundry Pool v2 connections, **not** Stratum.

## Troubleshooting

- Run `nvidia-smi` if no compatible GPU is detected.
- Check disk space and network if model acquisition or SHA-256 verification fails; do not bypass integrity checks.
- Check the IP, port, TLS certificate fingerprint, wallet policy and Mainnet identity if the pool rejects authentication.
- Telemetry is sent during kernel evaluation, not during every periodic mining update.
