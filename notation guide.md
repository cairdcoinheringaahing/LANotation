# Notation Guide

This document contains the most up-to-date list of notation used to document a game of Legacy's Allure.

# Format

The notation log is broken up into 8 sections: one section detailing the draft information, and 7 sections for each of the 7 rounds. Each of the 7 round sections follow the same format, and the exact format of the draft section depends on whether the game is a blitz or draft game.

In any game, `Player 1` is the player with the **A1** hex on their bottom left, regardless of who acts first. Additionally, we use abbreviations and acronyms for most unit names, for the sake of brevity. The one exception to this is, during drafting in the Draft section, we list the full name of hero items and abilities. However, when these are explicitly used and mentioned in Round sections, we use abbreviations.

Furthermore, note the difference between "Player 1" and "the first player" - the former refers to the player with the **A1** hex on their bottom left, and the latter refers to the player acting first in a specific round. A similar difference applies with "Player 2" and "the second player". Finally, we occationally use the terms "attacker" and "defender" to refer to the player who needs to take the center hex, and the player who needs to prevent that.

# Standard conventions

Rather than using the name of the hero, we use `Hero` to denote that it took an action. If a unit moves to a hex, even as part of an ability, the hex it is moved to is the first thing folowing the unit's name. This is only violated if the movement occurred after an ability/attack *and* the order matters.

Anything shown below in angle brackets (e.g. `<hex>`) is meant to be replaced by actual game data during a proper log. The angle brackets should also be replaced. Anything not included in angle brackets should be used verbatim in a log. Refer to the various examples for additional clarity.

---

# Draft Section

## Blitz

As the card positions, abilities and items are fixed for blitz games, the only things to note are the gold limit and the hero. Therefore, the section has the following format

    Draft - Blitz <Gold Limit>
    <Player 1>: <Hero>
    <Player 2>: <Hero>
    
## Draft

For draft games, we need to note the gold limits of both the kingdoms and armies, and the specific cards and their placements. Therefore, the format has a lot more information. We list out the full 9 hexes for each row of each player, as well as the hero, abilities and items used. If a specific hex is empty, we indicate this with an `X`. Note that order is listed in the order of each players' PoV, from left to right.

    Draft - <Kingdom Gold> draft <Army Gold>
    <Player 1>: <Hero>. <Abilities>. <Items>
    Front: <A2>, <B2>, <C2>, <D2>, <E2>, <F2>, <G2>, <H2>, <I2>
    Back: <A1>, <B1>, <C1>, <D1>, <E1>, <F1>, <G1>, <H1>, <I1>
    
    <Player 2>: <Hero>. <Abilities>. <Items>
    Front: <I6> <H5> <G6> <F5> <E6> <D5> <C6> <B5> <A6>
    Back: <I7> <H6> <G7> <F6> <E7> <D6> <C7> <B6> <A7>
    
For example, below is a screenshot showing a draft setup, along with the correct draft notation.

![example set up](https://i.imgur.com/rR5iwNK.png)

    Draft - 160 draft 80
    Bob: Kaar'thul. Chain Lightning 3, Lightning Bolt 3. Bulwark Boots, Arcane Stone, Buckler.
    Front: X, Char, WRider, Grunt, GTrench, Grunt, WArcher, Char, X
    Back: X, DHatch, X, TDoctor, Hero, CWyvern, X, SCH, X

    Alice: Kaladrix. Velocity Greaves.
    Front: GHawk, CGuard, NGH, UMinor, Hero, UMajor, NGH, DProc, GHawk
    Back: X, DSen, Wisp, DMystic, TBow, NSorc, Wisp, DSen, X

## Extended Draft

Given the strategic aspect of drafting, sometimes the turn order may provide important insight on the the game. In which case, extended draft format is used, and takes the following format:

    Draft - <Kingdom Gold> draft <Army Gold>
    D1. <Player 1's drafts>, <Player 2's drafts>
    D2. <Player 1's drafts>, <Player 2's drafts>
    ...

Each turn in the draft, the unit and the hex it is drafted to is noted. Multiple unit drafts are separated with a semi-colon. For example, the opening to the above draft may have been:

    Draft - 160 draft 80
    D1. Char B2; Char H2; Hero E1, UMinor F5; UMajor D5; Hero E6
    D2. TDoctor D1, Wisp G7; Wisp C7
    ...
    
---

# Round Sections

Naturally, the rounds take up the meat of the game. Each round consists of a number of turns, where each player takes exactly one action. The first line in a round section looks like

    Round <N>: <Player acting first>
    
It is then followed by a list of turns taken in that round, where each turn lists exactly one action by each player. Each turn is prefixed by a counter of the turns so far in the game, and this does not reset each round. Each player's turn is separated by a comma, and if multiple actions happen on a single turn, they are separated by a semicolon. For example, the opening move from the draft shown above may be

    Round 1: Alice
    1. GHawk (I6) E4, GTrench E3
    2. Hero E6, Char B4
    
Here, Alice opened by moving her Glade Hawk on **I6** into the central hex (**E4**), and Bob responded by moving his Trenchdigger Goblin forward one hex to **E3**. Note that we had to specify which of Alice's Glade Hawks moved to the center, as either would have been able to. However, as only one of Bob's Charbelchers can move to **B4**, we don't need to specify which.

## Moves

The most basic move in Legacy's Allure is to move a unit into an unoccupied hex. This is simply denoted as `<unit> <hex>`, where `<unit>` is the unit moving, and `<hex>` is the hex they are moving to. For example, `GTrench E3` is a movement. It is implicit that when a unit moves into **E4** for the first time, they take the shield - we don't note this. When a unit moves and takes another action (e.g. combinable abilities), we notate it as `<unit> <hex> <action>`. For example, if a Priest moved to **E6** then healed the unit on **D4**, we'd write `Priest E6 heal D4`.

## Ranged attacks

When a unit takes a ranged attack against a hex, we notate it as `<unit> shoot <hex>`, where `<unit>` is the attacking unit, and `<hex>` is the targeted hex. For example, `AWizard shoot C5` would indicate that an Apprentice Wizard shoots the unit on **C5**. If a ranged unit is combinable and moves, we'd denote it as `<unit> <move> shoot <target>`, such as `SArcher F3 shoot F4`, which indicates that a Skorg Archer moved to **F3**, then made a ranged attack against the unit on **F4**.

## Melee attacks

Melee attacks use a similar format to moving. As a "full kill" melee attack results in the attacker moving into the defender's hex, we state a melee attack as `<unit> <hex>`, where `<unit>` is the attacking unit, and `<hex>` is the hex they would move into, if they kill the defending unit. There are three possible outcomes:

- The attacker kills the defender, and moves into the hex. In this case, we don't need to change the notation. Example: `UKnight F4`, with a unit in **F4** with less than 5 health left. Note that if the attacker kills the defender, yet still takes damage from the attack (e.g. Counterstrike or Physical Damage Return), we use the next notation. 
- The attacker does not kill the defender, takes retaliation or additional damage (e.g. Physical Damage Return) and moves back to an adjacent unoccupied hex. If it is unambigous which hex the attacker ends up in (the only avaiable hex, their movement only allows for one specific hex, etc.), then we simply append a `#` to the end of the attacked hex to denote retaliation. However, if there are multiple possible hexes the attacker could und up in, we add a `move <hex>` to the end. Example: `UMinor H3#` means that Ursa Minor attempted to attack the unit in **H3**, but it had more than 3 health remaining. In this case, Ursa Minor remains in an adjacent hex to **H3** and takes some damage in retaliation. We currently don't know the full board, but, as no hex is indicated (e.g. `UMinor H3# move H4`) we can assume that **H3** is the unambiguous point for Ursa Minor to end up at.
- The attacker does not kill the defender, but does not take retaliation or damage from the attack (e.g. Backstab) and moves back to an adjacent unoccupied hex. If it is unambigous which hex the attacker ends up in, we append a `*` to the hex. Again, identical rules apply as when retaliation is taken, the only difference is that we use `*` to denote that not only has an attack against a hex been made, but that it wasn't a killing attack and the attacker took no retaliation.

## Active abilities

When a unit uses an active ability, the format either follows `<unit> <ability keyword> <hex>` (for abilities) or `<unit>: <buff> <hex>` (for buffs), where `<unit>` is the unit using the ability, `<ability keyword>` is an abbreviation to indicate which ability was used, `<buff>` is one of the specific buffs listed below, and `<hex>` is the hex targeted by that ability. The full list of ability keywords can be found below.

### Buffs

When a unit grants another unit either a buff or a debuff, we denote it as `<unit>: <buff> <hex>`. For example, `Tact: +1P D1` would mean that the Tactician grants +1 Power to the unit on **D1**. The list of buff/debuff abbreviations are shown below. If the buff/debuff is combinable, the movement goes before the colon: `Angel C2: +2S E2` would mean that the Angel moves to **C2**, then grants a +2 Shield to the unit on **E2**. If `<hex>` is omitted, the buff is assumed to be given to the unit giving the buff (so `Hero: +1A` would give +1 Action to the Hero).

### Abilities

Most other abilities happen against a specific unit as the turn, such as dealing or healing damage, rooting/silencing/disarming/breaking units and more. These are written as `<unit> <ability keyword> <hex>`. For example, `ATM LStrike E4` would indicate that the Adept Tempest Mage used Lightning Strike on the unit on **E4**. Again, if an ability is combinable, the movement goes immediately after the unit: `TDoctor D2 heal D4` would say that the Troll Doctor moved to **D2**, then healed the unit on **D4**.

## Passive abilities

If a passive ability has no "dynamic" in game effect, then there is no need to make any note of it, beyond in the draft section. For example, if Tristan has Divine Favor 2, including this in the draft section for Draft games is enough information to understand that Tristan has a +2 Shield. However, for passive abilities that require some form of action by the player, or abilities that impact other units on the board during the game, we need to make note of what happens. Some examples:

- `Hero SFervor Charge` would indicate Aurelia using Sun's Fervor to gain Charging
- `SShock C5` says that a unit has used a mana ability, and Kaar'thul's Spellshock deals 1 pure damage to the unit on **C5**
- `TBeserker +1P#` would denote that the Troll Beserker has used its ability to gain +1 Power, and received 1 damage
  - From this, you can see the convention to append actions that deal damage to the indicated unit with a `#`

---

# Buff/Debuff Abbreviations

- `+1P`/`+2P`/`-1P`/`-2P`: +1/+2/-1/-2 Power
- `+1R`/`+2R`/`-1R`/`-2R`: +1/+2/-1/-2 Range
- `+1S`/`+2S`/`+3S`: +1/+2/+3 Shield
- `+1M`/`+2M`/`-1M`/`-2M`: +1/+2/-1/-2 Movement
- `+1A`: +1 Action
- `+1CR`: +1 Cast Range
- `+1SP`/`+2SP`: +1 Spell Power
- `+1MR`/`+2MR`/`+3MR`: +1/+2/+3 Magic Resist
- `+1PDR`/`+2PDR`/`+3PDR`: +1/+2/+3 Physical Damage Return
- `Path`/`APath`: Pathing/Allied Pathing
- `SProof`/`Stead`: Spellproof/Steadfast
- `Charge`/`Pier`/`Imbued`/`EoA`: Charging/Piercing/Imbued/Exhaust on Attack
- `IStead`/`ISProof`: Ignore Steadfast/Ignore Spellproof
- `+1B`/`+2B`: +1/+2 Burned
- `Net`/`Hook`: Net Shot/Hook Shot

---

# Ability Keyword Abbreviations

For abilities that can have a variable amount of mana spent (e.g. Nature's Bosom), the ability has a `<X>M` indicator. For example, `Hero NBosom 2M; Hero heal F4; Hero: +1S F4` means that the Hero spends 2 mana to use Nature's Bosom, where the effects were healing the unit on **F4**, and giving it a +1 Shield.

For abilities that have multiple levels, the ability has an `<N>` indicator to show the level used.

For any ability where it is unambiguous about either `<X>M` or `<N>`, the indicator can be omitted.

## Hero Abilities

### Anwyn

- Nature's Bosom: `Hero NBosom <X>M; Hero <action> <hex>; Hero <action> <hex>; ...`. The number of `Hero <action> <hex>` depends on `<X>`, the amount of mana spent.
- Replace: `Hero Replace <hex 1> <hex 2>`
- Tranquility: `Hero Tranq <X>M <hex>`
- Quicken: `Hero Quicken <hex>`

For Anwyn's standard ability, we add in an additional note at the end of the turn, such as `2. Swords C3, Hero Quicken F5; Hero: +1A`

### Argog

- Inner Vitality: `Hero IVital <N>`. Here, `<N>` is the level of Inner Vitality.
- Swift Strike: `Hero SStrike`
- Omnislash: `Hero Omni`

### Aurelia

- Sunstrike: `Hero SStrike <X>M <hex>`
- Solar Aegis: `Hero SAegis <hex>`
- Sun's Fervor: `Hero SFervor <buff 1> <buff 2>`. If only 1 mana is spent, and so only one buff is used, simply omit the second.
- Glory: `Hero Glory`

### Kaar'thul

- Lightning Bolt: `Hero LBolt <N> <hex>`
- Chain Lightning: `Hero Chain <N> <hex 1> <hex 2> <hex 3> <hex 4>`. If fewer targets are chosen than the maximum, simply omit the remaining hexes. Hexes should be ordered in decending order of damage dealt. For example, `Hero Chain F2 G3 H3` (in this case, using Chain Lightning 2) would deal 3 damage to **F2**, 2 to **G3** and 1 to **H3**.
- Spellshock: `SShock <hex>`. Spellshock is denoted on the turn of the player hit, at the end, separated with a semicolon (e.g. `4. GSling shoot F4, ATM LStrike E4; SShock C6`)
- Battle Fury: `Hero BFury <hex>`.

### Kaladrix

- True Strike: `Hero TStrike`
- Blade Echo: `Hero BEcho <hex 1> <hex 2>`
- Blink: `Hero Blink <hex>`

### Tristan

- Shield Bash: `Hero SBash <hex>`
- Arrest: `Hero disarm <hex>`

## Non-hero abilities

The current abilities on non-hero cards are shown below. As with all other abilities, if an ability is combinable and the unit moves before using the ability, prefex the ability with the movement (`DSen G5 Man F5`):

- Ram: `<unit> Ram <hex>`
- Roar: `<unit> roar <hex 1> to <hex 2>`. Ursa Major's "Greater Roar" ability is also denoted the same way. If the unit moves into `<hex 1>`, denote this as a separate action (e.g. `8. RGriff F4, UMinor roar F4 to F3; UMinor F4`)
- Belch: `<unit> belch <hex 1> <hex 2> ... <hex 6>`. Up to 6 hexes can be affected by this, only list the hexes that are actually affected.
- Taunt: `<unit> taunt <hex>`
- Disarm: `<unit> disarm <hex>`
- Launch: `<unit> launch <hex 1> at <hex 2>`. `<hex 1>` is the hex of the sacraficed unit, `<hex 2>` is the target hex.
- Exhaust: `<unit> exhaust <hex>`
- Healing: `<unit> heal <hex>`
- Rooting: `<unit> roots <hex>`
- Trample: `<unit> trample <hex 1> <hex 2> <hex 3>`. Hexes should be listed in order of movement. Note that `<hex 3>` only exists if `<unit>` kills the unit on `<hex 3>` with Trample.
- Breaking: `<unit> breaks <hex>`
- Detonate: `<unit> detonate <hex>` 
- Ice Nova: `<unit> INova <hex 1> <hex 2> <hex 3>`
- Maneuver: `<unit> Man <hex>`
- Teleport: `<unit> teleport <hex 1> to <hex 2>`
- Sunburst: `<unit> SBurst`
- Frostbite: `<unit> FBite <hex>`
- Hook Shot: `<unit> hooks <hex 1> to <hex 2>`
- Resurrect: `<unit> resurrect <dead unit> to <hex>`. Note that `<dead unit>` should be the name of a previously drafted unit, that has already died.
- Silencing: `<unit> silences <hex>`
- Safe Haven: `<unit> teleports <hex 1> to <hex 2>`
- Flame Sweep: `<unit> FSweep <hex 1> <hex 2> <hex 3>`
- Untouchable: `<unit> untouch <hex>`
- Arcane Blast: `<unit> ABlast <hex>`
- Thunder Clap: `<unit> TClap <hex>`
- Control enemy: `<unit> control <hex>`
- Flame Assault: `<unit> FAssault <hex>`
- Nature's Call: `<unit> summons Treant to <hex>`
- Lackey Empower: `<unit> empower <hex>`
- Clearing debuff: `<unit> clears <hex>`
- Lightning Strike: `<unit> LStrike <hex>`

## Movement after an ability

If an ability is combinable, or if it allows for movement after doing the ability, it is sometimes necessary to denote the ability, then the movement, in that order. In this case, notate the movement as a separate action:

     UMajor roar E5 to E3; UMajor E5
     
This indicates that Ursa Major roars the unit in **E5** to **E3**, then moves into **E5** (as allowed by the Greater Roar ability). This is only necessary is the order of actions matters - otherwise, indicate movement as normal, directly after the unit.

## Passing

If a player decides to pass one specific unit, this is simply notated as `<unit> Pass`. For example, `12. Wisp Pass, SArcher F5` indicates that on the 12th move (out of 14 in this specific round), the first player passed with their Wisp.

If a player decides to pass all remaining units, we simply notate this as `Pass`. As an example, `13. SRanger D1, Pass` indicates that the second player passes with the rest of their units, and that the first player is free to complete all their remaining moves at once. Note that, even in this case, the first player should still list all their moves in a specific clear order, of their choice.

If the first player passes, and the second player still has units to act, the first player's turns are written as `...`:

    29. Arbor F1, AWizard shoot D4
    30. Pass, Angel resurrect Swords E4
    31. ..., Enforcer D1
    32. ..., Angel D2
    33. ..., AWizard F6
    34. ..., Pass
    
As the first player has fewer units than the second player, we use `...` for the first player's turns as the second player makes their final moves.

## Ending the game

There are four ways to denote the end of the game:

- When a player resigns the game, this is written as `Resign.` on their turn.
- If, by Round 7, the attacker has a unit in **E4**, the center hex, then either:
  - The last move was moving the unit into **E4**, in which case, we end the game by postfixing the move with a `.`: `34. ..., Hero E4.`
  - The last move was something else. In which case, we state in a line under the final move `<unit> finishes in E4.`:

        Round 1: Diane
        ...
        
        Round 7: Diane
        52. GTrench E4, Hero H2
        53. IMinotaur trample H2, GHawk H2#

        GTrench finishes in E4.
        
    This would denote the last moves of a game where a Trenchdigger Goblin moves into **E4**, the Hero moves to **H2**, an Ironhoof Minotaur tramples into **H2**, killing the hero, and the Glade Hawk sacrifices itself against the Ironhoof Minotaur. The round ends, and we declare that the Trenchdigger Goblin is in **E4**, so Diane has won the game.
    
- If, by Round 7, the attacker does not have a unit in **E4**, but still has units on the board, we state, similar to above, `No unit finishes in E4.`. Even if a defender's unit is in **E4**, we still state this.
- If the defender completely wipes out the attacker's army before the end of Round 7, then the turn that kills the attacker's final unit is ended with a `.`.
 
    Consider the following game, where, at the start of Round 5, we have Glade Hawk on **C1**, Ursa Major (with 5 damage) on **F3**, Wisp on **H2**, Priest on **F4** and Apprentice Wizard on **C4**. Arengard attacking.
        
        Round 5: Diane
        40. Wisp G3 heal F3, AWizard: -1P F3
        41. UMajor F4
        42. GHawk C4.

    As the Glade Hawk charging to **C4** kills the attacker's last unit, it ends the game. You can optionally include `No unit finishes in E4.`, but this isn't required in this case.
