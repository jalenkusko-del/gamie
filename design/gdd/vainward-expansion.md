# VAINWARD Expansion: Maps, Waves, Properties, Infusion

Status: Draft. Source of truth for the playable prototype in `prototypes/vainward/`. LOCKED items come from the owner briefs; PROVISIONAL items are tuning values.

## 1. Overview
The original world has exactly nine maps and 28 rooms (3, 4, 5, 2, 4, 6, 2, 1, 1), themed Limbo (casino), Lust, Gluttony, Greed, Wrath, Heresy, Violence, Fraud and Treachery. Rooms are multi-wave. The Vainbound realm is a separate destination unlocked by the first Hybrid. Everything owned is a card.

## 2. Player Fantasy
Keep getting stronger by collecting, fusing and infusing, while the best fights still demand understanding of what you built. Fusion changes what you own; Infusion changes what you are.

## 3. Detailed Rules
- **Cards (LOCKED):** one authoritative collection; tiers 1 to 5 only; five categories shown (Creature, Weapon, Armor, Ability, Item) over the internal categories; Red Artifacts are Item cards.
- **No cooldowns (LOCKED).**
- **Waves (LOCKED):** health and resources carry between waves with no automatic recovery. Each cleared wave secures marks and one card. Retreat keeps secured wave rewards and forfeits the room-clear reward. Defeat forfeits the run's wave rewards (PROVISIONAL).
- **Auto-clear (LOCKED direction):** only after a legitimate clear; unattended; can lose.
- **Remembrance (LOCKED):** only Nullbrand Knight, Temper Leech, Redwater Ravager and the Unbound Professor resist the previous victory's most-used ability family. The Ravager also changes formation.
- **Shops (LOCKED):** a listing unlocks permanently on first acquisition of the card; selling or fusing never relocks it.
- **Properties:** a property is a list of executable parts (effect, value, optional key). Parts with the same effect key are mechanically equivalent and never add.
- **Strengthen, evolve, fuse are distinct.** Evolution at tier-up offers Strengthen, Expand or Combine choices derived from the card's own properties; Tier 3 allows two (approved). Choices are permanent and shown together before confirming.
- **Fusion tier:** result = max(L, ceil(H/2)). Hybrid (two evolved Tier 5 cards) stays Tier 5 and opens the Vainbound realm. A bridge (third) card adds properties and never changes the tier (approved).
- **Craft:** every fusion keeps a record. Craft More, Craft max, Repeat last fusion and favorites exist. Auto-picks prefer unmodified base copies and skip favorites, locked, equipped, evolved and strengthened cards unless allowed. Batches are atomic.
- **Infusion (LOCKED):** five active slots; eligibility by card properties; upgrades spend 2 to 4 matching cards; stages persist when unequipped. Families: Sepulchral Covenant, Umbral, Ironblood, Sanguine, Gravitic, Chimeric, Heretical.

- **Rogue Descent:** begins with exactly one card copied from the collection. The permanent collection is set aside and restored at the end. Every floor is one fight with scaling enemies; after a win choose 1 of 3 cards. A boss every 5 floors pays a permanent card and marks. A defeat loses all run cards. Floor-to-floor healing is PROVISIONAL (30%).
- **Scavenger Runs:** real team and collection. Loot is unsecured (protected from selling and fusing) until you extract. Continuing adds loot and danger; a defeat loses the satchel.
- **Trials of Fusion:** a fixed puzzle fight with a small temporary card set. Any winning loadout or fusion counts. First clear pays marks and one card.

- **Development model:** Strengthening raises levels by spending cards (stats only, no marks, no combat XP; level cap rises with tier; never reset by evolution). Feeding adds evolution progress only. Evolution changes properties. Tier-up needs progress, not a level.
- **Species drops:** each enemy species has an exact Creature Card; naturally Tier 1, rarely Tier 2. A Pet Shop listing unlocks on first acquisition.
- **Fusion inheritance:** result level is 60% of the higher ingredient level, never summed. A fusion has a 20% chance of a Surprise that adds one function derived from an existing property.
- **Bounds:** dodge capped at 75%, any probability at 95%, a hit at 9999.

## 4. Formulas
- Fusion tier: `max(min(a,b), ceil(max(a,b)/2))`, capped at 5.
- Wave marks: `round(winCoin * WAVES.coinShare)`. Win marks: `(base + perThreat * threat + boss) * (first ? 2 : 0.5) * (hard ? 1.5 : 1)`.
- Property merge: for equivalent parts, keep `max(v1, v2)`.
- Strengthen: `v = min(cap, v + step)` per effect (see `PSTEP`).

## 5. Edge Cases
- Preview and failed fusions never unlock the realm or write properties.
- Batch craft that fails midway restores the previous state.
- Selling a Hybrid never removes the realm unlock.
- Summoned allies dying never ends a fight.
- Old saves: rooms keep ids; marks are credited from cleared rooms; new fields are normalized on load.

## 6. Dependencies
Collection and shop systems, battle engine (`hit`, `enemyAct`), save code (`encode`, `migrate`, `validate`).

## 7. Tuning Knobs
`ECON`, `WAVES`, `SHOPS`, `FERRY`, `WHISTLE`, `LANTERN`, `INF`, `PSTEP`, `EXPAND`, `EVO_CHOICES`, enemy tables in `EN`.

## 8. Acceptance Criteria
- 9 maps, 28 rooms, all reachable and completable.
- Hybrid unlock only from a completed two-evolved-Tier-5 fusion.
- No cooldown mechanics exist.
- Equivalent properties never stack; different mechanics coexist.
- Tier 3 development choices are permanent and bulk-applicable only to identical histories.
- Batch crafting and multi-sell never produce partial or duplicated results.

## Open decisions (not canon)
Whether Tiers 2, 4 and 5 keep one choice each; Infusion stays automatic by decision (recommendation: 1, 1, 2); respec and refund for infusions; defeat rules between runs; trait capacity (tier + 1) versus the three-property Wolf example;  Rogue Descent reward breadth, scavenger loot tables and trial rewards are placeholders.
