# [AeroMulti](https://aeronautica-helper.vercel.app/aeromulti)

**Live Aeronautica server multiplier data** - by [AeroHelper](https://aeronautica-helper.vercel.app/).

AeroMulti scans [Aeronautica](https://www.roblox.com/games/6647962258/UPD-Aeronautica) servers, reads job supply/demand multipliers via OCR, and publishes what it finds so you can pick the best server without hopping around yourself.

---

## Discord feed

**Multiplier digests are posted in the AeroHelper Discord**

Each update lists alive servers with their latest multipliers (Standard and Leovetsk-Auchenburgh track routes), so you always have a fresh snapshot without running anything locally.

**[Join the Discord server →](https://discord.gg/acdQ6BFrFs)**

Look for the AeroMulti multiplier channel after you join. No setup required - just read the feed.

---

## API access (exclusive)

The backend exposes `GET /api/aeromulti` for recent server multiplier readings from our database. This is **not public** - access is granted on a case-by-case basis. These are the most up to date readings.**

**How to request access:**

1. **[Join the AeroHelper Discord server](https://discord.gg/acdQ6BFrFs)**
2. **Open a support ticket** and ask for AeroMulti API access
3. If approved, you receive an API key and documentation for authenticated reads

API keys are exclusive. We do not hand them out in bulk or publish them in the repo. Ingest (`POST /api/aeromulti`) is operator-only and not available to consumers unless you are an AeroMulti Operator.

Full endpoint notes and rate limits are shared in Discord after approval. See also the [AeroMulti page](https://aeronautica-helper.vercel.app/aeromulti) on the website.

---

## What you get

- **Per-server multipliers** for active Aeronautica homepage servers
- **Standard route** and **Leovetsk-Auchenburgh track** readings where detected
- **Regular Discord updates** frequently
- **Optional API access** for bots, dashboards, or your own tools (ticket required)

---

## Important notes

- AeroMulti is a **community tool by AeroHelper**, not affiliated with or endorsed by Aeronautica staff.
- Multipliers are **OCR-based** - always verify in-game before committing to a route.
- The AeroMulti **scanner app is not distributed** from this repo or the website. This repository documents the project; live data comes from Discord and the API.

---

## Links

- [AeroMulti Website](https://aeronautica-helper.vercel.app/aeromulti)
- [AeroHelper Discord](https://discord.gg/acdQ6BFrFs)
- [Main AeroHelper App (Monitoring / AutoSteer / AutoPilot)](https://aeronautica-helper.vercel.app/)

---

## Version

Current version: **1.2.4**
