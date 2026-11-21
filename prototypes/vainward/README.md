# Prototype: VAINWARD playable build (v1.2)

**Hypothesis:** A single-file, card-only tactical RPG can carry three modes (Rogue Descent, Scavenger Runs, Trials of Fusion) and nine themed maps with multi-wave rooms, structured card properties, fusion with forecasts, five-slot Vainbound Infusion and the Vainbound realm, without a second inventory.

**How to run:** Open `index.html` in a browser. It needs no build step. The published artifact starts from the same file. Progress lives in the in-game save code.

**Status:** In progress. Systems are playable; numbers are provisional and live in config blocks near the top of the script (`ECON`, `WAVES`, `WHISTLE`, `LANTERN`, `FERRY`, `INF`, `PSTEP`, `EVO_CHOICES`).

**Findings:**
- An auto-played team advanced to Tier 3 clears all 28 rooms; starting-strength teams clear Maps 1 and 2 only.
- Equivalent property parts never stack on fusion; different mechanics coexist, integrate or convert (dodge + thorns gives a counter).
- Tier 3 gives two permanent development choices. Counts for Tiers 2, 4 and 5 are not approved.
- Unverified by a human playtest: balance, pacing, and mobile feel beyond a 390px layout check.
- Modes use a run-scoped card set: Rogue Descent and Trials swap the collection out and restore it afterwards, so there is still one collection at a time. Run cards never unlock shop listings, and infusions cannot be changed during a run.
- Trials: each of the six has several winning loadouts and at least one naive loadout that loses.
