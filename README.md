<div align="center">

# GTA V Ultimate Stability `gameconfig.xml`

**A tuned `gameconfig.xml` for Grand Theft Auto V Legacy (Build 1.0.3889) that eliminates `ERR_MEM_EMBEDDEDALLOC` and pool-limit crashes in heavily modded setups.**

[![GTA V Build](https://img.shields.io/badge/GTA%20V-Build%201.0.3889-orange?style=for-the-badge&logo=rockstargames&logoColor=white)](#)
[![Status](https://img.shields.io/badge/Status-Stable-brightgreen?style=for-the-badge)](#)
[![Mode](https://img.shields.io/badge/Mode-Single%20Player-blue?style=for-the-badge)](#disclaimer)
[![Mods](https://img.shields.io/badge/Mod%20Stack-LCPP%20%2B%20NVE%20%2B%20LWE%20%2B%20FoSA-purple?style=for-the-badge)](#tested-mod-stack)

[Download](../../releases/latest) · [Installation](#installation) · [Requirements](#requirements) · [Troubleshooting](#troubleshooting)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Tested Mod Stack](#tested-mod-stack)
- [What's Tuned](#whats-tuned)
- [Requirements](#requirements)
- [Installation](#installation)
- [Recommended Load Order](#recommended-load-order)
- [Troubleshooting](#troubleshooting)
- [Disclaimer](#disclaimer)
- [Credits](#credits)

---

## Overview

Stacking a full map expansion, a graphics overhaul and dense vegetation mods quickly exhausts the game's default memory pools. This `gameconfig.xml` raises the relevant limits so the whole stack runs together without streaming drops, loading-screen crashes or `ERR_MEM_EMBEDDEDALLOC`.

Designed, tuned and stress-tested on **GTA V Legacy, Build 1.0.3889**.

---

## Tested Mod Stack

| Category | Mod | Notes |
| :-- | :-- | :-- |
| 🗺️ Map Expansion | **Liberty City Preservation Project (LCPP)** | Parts 1–5 + optional HD textures |
| 🎨 Graphics Overhaul | **NaturalVision Evolved (NVE)** | By Razed Mods. Skip the optional NVE vegetation add-on |
| 🌆 World & Props | **Lively World Expansion (LWE V3.0)** | Full urban, coastal and world prop density |
| 🌲 Vegetation | **Forests of San Andreas: Revised** | Tested alongside LWE V3.0 in dense areas such as Paleto Forest |
| 🚗 Add-Ons | **Custom vehicles, peds & weapons** | Supports hundreds of add-on `.rpf` archives |

---

## What's Tuned

| Area | Pools | Purpose |
| :-- | :-- | :-- |
| **Map & Collision** | `MapDataStore`, `BoundsStore`, `StaticBounds` | Handle Liberty City's full landmass alongside San Andreas without streaming drops |
| **Foliage & Props** | `EntityBatch`, `GrassBatch` | Prevent crashes in dense forest regions (Paleto Bay, Vinewood Hills) with LWE V3.0 + Forests of San Andreas: Revised |
| **Textures & Models** | `DrawableStore`, `TxdStore`, `FragStore` | Support high-resolution NVE and LCPP textures without pop-in or memory leaks |

---

## Requirements

Install these into your main **GTA V root directory** *before* launching, otherwise the game may crash on startup or during loading.

| # | Requirement | Setup |
| :-: | :-- | :-- |
| 1 | **Script Hook V** | Latest version supporting Build `1.0.3889` |
| 2 | **OpenIV** + `OpenIV.asi` | Install via OpenIV's ASI Manager |
| 3 | **Heap Adjuster** | In `HeapAdjuster.ini`, set `HeapSize = 2000` (or `2500` with 32 GB+ RAM) |
| 4 | **Packfile Limit Adjuster** | In `PackfileLimitAdjuster.ini`, set `PackfileLimit = 65536` |
| 5 | **Resource Adjuster / Weapon Limit Adjuster** | Recommended for LCPP custom peds and scenarios |

---

## Installation

> [!IMPORTANT]
> **Back up your original `gameconfig.xml` first.**

1. Download `gameconfig.xml` from the [Releases](../../releases/latest) page.
2. Open **OpenIV** and enable **Edit Mode**.
3. Navigate to:
   ```text
   mods/update/update.rpf/common/data/
   ```
4. Drag and drop the downloaded `gameconfig.xml` into this folder, replacing the existing file.
5. Close OpenIV and launch GTA V.

---

## Recommended Load Order

1. **NaturalVision Evolved** *(do not install NVE's optional vegetation add-on)*
2. **Liberty City Preservation Project** *(Parts 1–5)*
3. **Forests of San Andreas: Revised**
4. **Lively World Expansion (LWE V3.0)**
5. **This `gameconfig.xml`**

---

## Troubleshooting

| Problem | Fix |
| :-- | :-- |
| Crash on startup | Confirm Script Hook V matches Build `1.0.3889` and `OpenIV.asi` is installed |
| `ERR_MEM_EMBEDDEDALLOC` persists | Check `HeapSize` in `HeapAdjuster.ini` and that Heap Adjuster is actually loading |
| Crash while loading | Verify `PackfileLimit = 65536` and that the load order above was followed |
| Game ignores the file | Make sure it was placed in `mods/update/update.rpf/common/data/` with Edit Mode on |
| Want to revert | Restore your backed-up original `gameconfig.xml` |

Still stuck? [Open an issue](../../issues) with your game build, mod list and crash log.

---

## Disclaimer

- Built for **GTA V Legacy Build 1.0.3889** only. Other builds are untested.
- Intended for **single-player** use. Do not use mods or modified game files in GTA Online.
- Provided as-is, with no warranty. Always keep a backup of original game files.
- Not affiliated with or endorsed by Rockstar Games or Take-Two Interactive.

---

## Credits

- **Author:** Designed, configured and stress-tested by me.
- Full credit to the creators of **Liberty City Preservation Project**, **NaturalVision Evolved**, **Lively World Expansion** and **Forests of San Andreas: Revised** for their work.

<div align="center">

If this configuration stabilized your setup, please consider giving the repo a ⭐

</div>
