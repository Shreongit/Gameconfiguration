# GTA V (v1.0.3889) Ultimate Stability `gameconfig.xml`

![GTA V Version](https://shields.io)
![Status](https://shields.io)
![Mods](https://shields.io)

**Personally designed, tuned, and stress-tested by me for Grand Theft Auto V (Build 1.0.3889).**

This custom `gameconfig.xml` is engineered to eliminate `ERR_MEM_EMBEDDEDALLOC` and pool-limit crashes when running massive map expansions, heavy graphics overhauls, and dense vegetation mods simultaneously.

---

## Tested & Compatible Mod Stack

This configuration was specifically built and verified to run all of the following heavy mods together without memory or streaming crashes:

| Category | Mod Name | Notes |
| :--- | :--- | :--- |
| **Map Expansion** | Liberty City Preservation Project (LCPP) | Compatible with Parts 1–5 + Optional HD Textures |
| **Graphics Overhaul** | NaturalVision Evolved (NVE) | By Razed Mods (Skip optional NVE vegetation add-ons) |
| **World & Vegetation** | Lively World Expansion (LWE V3.0) | Full urban, coastal, and world prop density supported |
| **Vegetation Overhaul** | Forests of San Andreas: Revised | Tested alongside LWE V3.0 in dense areas like Paleto Forest |
| **Add-Ons** | Custom Vehicles, Peds & Weapons | Supports hundreds of add-on `.rpf` archives |

---

## Key Pool Tweaks & Improvements

- **Map & Collision Pools (`MapDataStore`, `BoundsStore`, `StaticBounds`):** Expanded to handle Liberty City's full landmass alongside San Andreas without streaming drops.
- **Foliage & Prop Batching (`EntityBatch`, `GrassBatch`):** Boosted to prevent crashes in dense forest regions (Paleto Bay, Vinewood Hills) when stacking **LWE V3.0** and **Forests of San Andreas: Revised**.
- **Texture & Model Dictionaries (`DrawableStore`, `TxdStore`, `FragStore`):** Increased to support high-resolution **NVE** and **LCPP** textures without pop-in or memory leaks.

---

## Mandatory Requirements

To prevent crashes on startup or during loading screens, install these ASI plugins in your main **GTA V root directory** before launching:

1. **Script Hook V** — Latest version supporting Build `1.0.3889`
2. **OpenIV & `OpenIV.asi`** — Installed via OpenIV's ASI Manager
3. **Heap Adjuster** — Open `HeapAdjuster.ini` and set `HeapSize = 2000` *(or `2500` if you have 32GB+ RAM)*
4. **Packfile Limit Adjuster** — Open `PackfileLimitAdjuster.ini` and set `PackfileLimit = 65536`
5. **Resource Adjuster / Weapon Limit Adjuster** — Recommended for LCPP custom peds and scenarios

---

## Installation Instructions

1. Download `gameconfig.xml` from this repository (or the [Releases](../../releases) tab).
2. Open **OpenIV** and enable **Edit Mode**.
3. Navigate to:
   ```text
   mods/update/update.rpf/common/data/
   ```
4. Drag and drop the downloaded `gameconfig.xml` into this folder to replace the existing file.
5. Close OpenIV and launch GTA V.

### Recommended Mod Load Order
1. **NaturalVision Evolved** *(Do not install NVE's optional vegetation add-on)*
2. **Liberty City Preservation Project** *(Parts 1–5)*
3. **Forests of San Andreas: Revised**
4. **Lively World Expansion (LWE V3.0)**
5. **This `gameconfig.xml`**

---

## Disclaimer & Credits

- **Author:** Designed, configured, and stress-tested by me on GTA V Legacy Build `1.0.3889`.
- **Backup Reminder:** Always back up your original `gameconfig.xml` before replacing game files.
- **Credits:** Full credit goes to the creators of **Liberty City Preservation Project**, **NaturalVision Evolved**, **Lively World Expansion**, and **Forests of San Andreas: Revised** for their incredible work.

If this configuration helped stabilize your modded setup, consider giving this repository a ⭐ **Star**!
