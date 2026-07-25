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

The backend exposes `GET /api/aeromulti` for recent server multiplier readings from our database. This is **not public** - access is granted on a case-by-case basis. These are the most up to date readings.

**How to request access:**

1. **[Join the AeroHelper Discord server](https://discord.gg/acdQ6BFrFs)**
2. **Open a support ticket** and ask for AeroMulti API access
3. If approved, you receive an API key and documentation for authenticated reads

API keys are exclusive. We do not hand them out in bulk or publish them in the repo. Ingest (`POST /api/aeromulti`) is operator-only and not available to consumers unless you are an AeroMulti Operator.

Full endpoint notes and rate limits are shared in Discord after approval. See also the [AeroMulti page](https://aeronautica-helper.vercel.app/aeromulti) on the website.

---

## What you get

- **Per-server multipliers** for active Aeronautica homepage servers
- **Standard route** (min–max range from Transport-to job samples) and **Leovetsk-Auchenburgh track** readings where detected
- **Regular Discord updates** frequently
- **Optional API access** for bots, dashboards, or your own tools (ticket required)

---

## Scanner (operators)

The live scanner used for Discord/API ingest is **`AeroMulti/`** in this repo (not a public download).

**Flow (high level):**

1. Launch Aeronautica homepage and inventory server IDs (scroll; no page cache)
2. For each server: relaunch → join from top of list → clear teleport queue if needed
3. Optional **Return to Airport** (can be disabled in the UI)
4. Play → Jobs → sample 5 Transport-to rows (Standard min–max range; cache JobRow slots; Play→Jobs retry on empty)
5. Search Leovetsk → track pass (Leovetsk-Auchenburgh) → Back → Play → Jobs on miss
6. Discord + local JSON + optional API ingest

**Notable v2.1 behavior:**

- **Standard range**: sample 5 Transport-to job rows → min–max (e.g. `1.2x` or `1.2x-1.5x`); Play→Jobs retry on empty
- JobRow1–5 click caches; Search/JobRow caches clear on track miss or empty Standard retry
- Jobs UI ROI locked to the **left panel** (Search + list); ignores center Airport Modifiers / HUD
- Server browser: stronger Server ID OCR (hex-like IDs), Join/Queue pairing, focus-once then wheel scroll
- Fail recovery: one retry pass that keeps priors already found; empty-homepage streak closes Roblox and recovers
- WinRT OCR first; EasyOCR only when WinRT misses expected text/boxes
- Homepage ready poll up to **60s** (every 2s)
- Kill lists and "Ignore Return to Airport" persist in `AeroMulti.env`
- Secrets/webhooks stay in `AeroHelper.env`

Legacy scanner code remains under `AeroMulti/` for reference; prefer **AeroMulti**.

---

## Important notes

- AeroMulti is a **community tool by AeroHelper**, not affiliated with or endorsed by Aeronautica staff.
- Multipliers are **OCR-based** - always verify in-game before committing to a route.
- The AeroMulti **scanner app is not distributed** as a public release from the website. This repository documents the project; live data for the community comes from Discord and the API.

---

## Links

- [AeroMulti Website](https://aeronautica-helper.vercel.app/aeromulti)
- [AeroHelper Discord](https://discord.gg/acdQ6BFrFs)
- [Main AeroHelper App (Monitoring / AutoSteer / AutoPilot)](https://aeronautica-helper.vercel.app/)

---

## Version

Current version: **v2.1.0**
