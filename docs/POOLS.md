# REFORGEPOOL · Global Pool Connections

**Protocol:** CommonFoundry Pool v2 over pinned TLS. **Not Stratum.**

The six endpoints use numerical IP addresses, not DNS names. The reported city describes the tunnel ingress, not necessarily the location of the underlying mining server. IPs may change.

**Shared TLS certificate SHA-256:**

```text
969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

| Relay | Location | DNS | IP | Port |
|---|---|---|---|---:|
| EU1 | London, United Kingdom | `eu1.cmfd.reforgepool.com` | `212.86.105.165` | 19777 |
| EU2 | Bucharest, Romania | `eu2.cmfd.reforgepool.com` | `79.108.166.58` | 10081 |
| US1 | Atlanta, United States | `us1.cmfd.reforgepool.com` | `192.175.23.44` | 18995 |
| US2 | Seattle, United States | `us2.cmfd.reforgepool.com` | `45.61.62.74` | 14318 |
| JP1 | Tokyo, Japan | `jp1.cmfd.reforgepool.com` | `45.130.166.180` | 12669 |
| HK1 | Hong Kong | `hk1.cmfd.reforgepool.com` | `103.195.6.10` | 12061 |

## Copy-ready endpoints

### EU1 — London

```text
cmfd+tls://212.86.105.165:19777?pin=969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

### EU2 — Bucharest

```text
cmfd+tls://79.108.166.58:10081?pin=969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

### US1 — Atlanta

```text
cmfd+tls://192.175.23.44:18995?pin=969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

### US2 — Seattle

```text
cmfd+tls://45.61.62.74:14318?pin=969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

### JP1 — Tokyo

```text
cmfd+tls://45.130.166.180:12669?pin=969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

### HK1 — Hong Kong

```text
cmfd+tls://103.195.6.10:12061?pin=969c5faf5b90bf6a0026d907073752a73db7bfcee3513df9a2d76d209cfcdec6
```

The official miner selects a relay automatically when no manual pool is specified. Certificate pin checking and Mainnet checks must stay enabled.
