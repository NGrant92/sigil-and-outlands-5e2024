# Sigil and the Outlands — 5e2024 Port

A resource pack for the [RPG Companion App](https://rpg-companion.app) that ports the *Sigil and the Outlands* planar feat chain and its two backgrounds to the **5e2024** (2024 revised rules) system.

## Why this exists

The official [rpg-companion-app-systems](https://github.com/blastervla/rpg-companion-app-systems) repo already has this content fully built out for the **5e** (2014 rules) system, but it was never ported to **5e2024**. This pack closes that gap without needing a PR into the main systems repo — install it directly via the URL below and it layers on top of whatever 5e2024 content you already have.

## Installing

In the RPG Companion App (Developer Mode on), add this as a custom repository:

```
<GitHub Pages URL goes here once published>
```

## What's included

**6 feats** (the full planar feat chain):

| Feat | Role |
| --- | --- |
| Scion of the Outer Planes | Origin feat — choose a plane, granting a damage resistance + cantrip |
| Agent of Order | Level 4+ follow-up (Lawful Outer Plane) |
| Baleful Scion | Level 4+ follow-up (Evil Outer Plane) |
| Cohort of Chaos | Level 4+ follow-up (Chaotic Outer Plane) |
| Righteous Heritor | Level 4+ follow-up (Good Outer Plane) |
| Outlands Envoy | Level 4+ follow-up (The Outlands) |

(Planar Wanderer, the sixth follow-up feat available regardless of plane chosen, already ships with the official 5e2024 system — not included here.)

**2 backgrounds:**

- Gate Warden
- Planar Philosopher

Feat mechanics were ported essentially unchanged from the 5e (2014) version — same rules text, same automated effects (Ability Score Increase choices are mechanically wired up; everything else, like Stasis Strike's damage/save/condition, is text-only since the app's effect engine has no primitive for that — this matches how the official 5e2024 system already handles comparable abilities like Telekinetic Shove). The one addition: `Scion of the Outer Planes` now explicitly declares `type: origin`, which the 2014 source never needed to set.

## Backgrounds: 2014 → 2024 conversion

The 2024 ruleset redesigned how backgrounds work (Ability Score Increase + a single embedded origin feat + a fixed equipment package, replacing 2014's gold-pieces-and-granular-equipment-list style). Since this sourcebook was never officially updated for 2024 rules, converting it required some judgment calls — flagged below.

### Gate Warden

| Field | 2014 (`5e`) | 2024 (`5e2024`, this pack) |
| --- | --- | --- |
| Origin feat | Prose only — a wrapper feature named "Planar Infusion" whose text says *"You gain the Scion of the Outer Planes feat..."* | Scion of the Outer Planes embedded directly as the background's actual `Feat` object |
| Extra flavor benefit | "Free, modest lodging and food in the community you grew up in" | Preserved — appended as a final sentence on the embedded feat's description |
| Ability Score Increase | None (2014 backgrounds don't have this) | **Design call**: 3-point allocation among Int/Wis/Cha — ties to Scion's own spellcasting-ability choice, not arbitrary |
| Equipment | Always: Ring of Keys to Unknown Locks, Blank Book, Bottle of Black Ink, Traveler's Clothes, plus choice of 1 from {Ink Pen, Quill} | Same 6 items, reframed as "pick 5 of 7" with a **design call**: added 50gp cash alternative, matching the documented 2024 PHB convention that every background's gear package is valued at 50gp |
| Skills | Two "choose 1 from {Persuasion, Survival}" picks (nets both) | Simplified to two fixed grants: Persuasion + Survival |
| Languages | 2× "Any" | Unchanged |
| Tools | None | Unchanged (2014 source never granted one) |
| Gold pieces | 10 | N/A — field doesn't exist in 2024 schema |

### Planar Philosopher

| Field | 2014 (`5e`) | 2024 (`5e2024`, this pack) |
| --- | --- | --- |
| Origin feat | Prose only — wrapper feature named "Conviction": *"You gain the Scion of the Outer Planes feat. In addition, members of your organization provide you free, modest lodging and food..."* | Scion of the Outer Planes embedded directly as the actual `Feat` object |
| Extra flavor benefit | "Free lodging/food at faction holdings" | Preserved — appended as a final sentence on the embedded feat's description |
| Ability Score Increase | None | **Design call**: 3-point allocation among Int/Wis/Cha |
| Equipment | Always: Portal Key, Manifesto of Guiding Philosophy, Clothes (Common) — no choice | Same 3 items, reframed as "pick 3 of 4" with a **design call**: added 50gp cash alternative |
| Skills | Arcana (fixed) + 1 skill of your choice from the other 17 | Unchanged in substance, just reordered (Arcana listed first) |
| Languages | 2× "Choose 1" | Unchanged |
| Tools | None | Unchanged |
| Gold pieces | 10 | N/A |

## Known limitations

This pack inherits a hard limitation of the app's current effect engine: automation only covers flat, unconditional, single-outcome mechanics (a number added to a stat, a spell permanently learned, a spell castable N times, advantage on one specific roll). Anything requiring a player choice between different benefit packages, an opposed roll with a pass/fail branch, a status condition, or a resource pool sized by a formula (like "uses = proficiency bonus") is text-only:

- **Scion of the Outer Planes**: the plane choice, its damage resistance, and its cantrip are not automated — read the table in the feat description and apply them manually
- **Agent of Order / Baleful Scion / Cohort of Chaos / Righteous Heritor / Outlands Envoy**: each follow-up feat's active ability (Stasis Strike, etc.) is described in full but not mechanically triggered — roll the damage, call for saves, and track uses manually

## License

Content ported from *Sigil and the Outlands* (Planescape: Adventures in the Multiverse), sourced via [rpg-companion-app-systems](https://github.com/blastervla/rpg-companion-app-systems), licensed [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
