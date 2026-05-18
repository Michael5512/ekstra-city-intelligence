# Ekstra City Intelligence — Data Starter

> The missing data-persona starter for [Ekstra.ai](https://ekstra.ai).
> A cinematic, real-time city intelligence dashboard consuming the full Ekstra public API surface.

![Ekstra City Intelligence Dashboard](https://ekstra.ai/build-with-ekstra/demo)

---

## What This Is

The `build-with-ekstra` repo ships motion starters only.
The official docs acknowledge:

> *"For data apps (parking, cities) there is no dedicated starter yet — use the curb-rules endpoint directly against a vanilla HTML or React page."*

**This is that starter.**

A production-quality, zero-dependency HTML dashboard that demonstrates every public Ekstra data endpoint:

| Endpoint | Used For |
|---|---|
| `GET /api/v1/network/stats` | Live device count, operators, packet totals |
| `GET /api/v1/network/devices` | Device map markers, type filtering, trust scores |
| `GET /api/v1/curb-rules/near` | Real-time parking rules with active/inactive state |
| `GET /api/v1/platform/facts` | Live editorial ticker in footer |

**No authentication required.** All endpoints are public reads.

---

## Run It in 30 Seconds

```bash
git clone <this-repo>
cd ekstra-city-intelligence
python3 -m http.server 8080
# Open http://localhost:8080
```

No npm. No build step. No config. One file.

---

## Features

- **Live network map** — All Ekstra devices plotted with type-color coding (cyan = camera, magenta = screen, orange = phone IMU)
- **Device type filter** — Filter the map and list by device type in real time
- **Curb rules query** — Enter any lat/lng (or use your location) to pull live NYC parking rules within a configurable radius
- **Active/legal state** — Rules color-coded red (restricted now) vs green (legal now) with countdown to state change
- **Network stats panel** — Live device count, operators, and total packets with animated counter
- **Platform facts ticker** — Rotating editorial content from Ekstra's data feed
- **Auto-refresh** — Stats refresh every 30s, devices every 60s
- **Dark cinematic aesthetic** — Scan-line overlay, glowing markers, Syne + JetBrains Mono typography

---

## Extending This Starter

### Add motion control (phone pointer)
Layer in `@ekstraai/runtime-sdk/browser` from the `web-phone-pointer` starter to let a phone control the map.

### Add Director AI chat
Embed the Director AI panel (`/OS` chat surface) to let users query the data in natural language.

### Add spaces layer
When `GET /api/v1/spaces/near` matures, add a third marker layer for detected parking gaps.

### Web3 extension (Proof-of-Presence)
Ekstra Motion Addresses use ed25519 — the same curve as Solana wallets.
Connect device motion packets to on-chain attestation for physical presence proofs.

---

## File Structure

```
ekstra-city-intelligence/
├── index.html    ← Everything. One file, zero dependencies.
└── README.md     ← This file.
```

---

## Built For

- [Ekstra Build Contest](https://x.com/EkstraAi) — "Coolest build using build-with-ekstra relevant to your own project, voted by verified X users, wins 5 SOL"
- Submission by [@Myke_Kript](https://x.com/Myke_Kript) — Web3 community builder & AI content creator

---

## License

Apache-2.0 — Same as the Ekstra SDK ecosystem.
Free to use, fork, and submit as a PR to `build-with-ekstra/starters/`.

---

## Links

- [Ekstra Platform](https://ekstra.ai/OS)
- [build-with-ekstra repo](https://github.com/imxdemetri/build-with-ekstra)
- [Ekstra API Reference](https://ekstra.ai/api/v1/openapi.json)
- [Developer Context Pack](https://ekstra.ai/llms-full.txt)
