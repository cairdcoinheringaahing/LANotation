# Notation Guide

This document contains the most up-to-date list of notation used.

# Format

The notation log is broken up into 8 sections: one section detailing the draft information, and 7 sections for each of the 7 rounds. Each of the 7 round sections follow the same format, and the exact format of the draft section depends on whether the game is a blitz or draft game.

In any game, `Player 1` is the player with the **A1** hex on their bottom left, regardless of who acts first. Additionally, we use abbreviations and acronyms for most unit names, for the sake of brevity. The one exception to this is, during drafting in the Draft section, we list the full name of hero items and abilities. However, when these are explicitly used and mentioned in Round sections, we use abbreviations.

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
    
For example, below is a screenshot showing a draft setup, along with the correct draft notation (names anonymised).

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

# Rounds

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

- The attacker kills the defender, and moves into the hex. In this case, we don't need to change the notation. Example: `UKnight F4`, with a unit in **F4** with less than 5 health left.
- The attacker does not kill the defender, takes retaliation or additional damage (e.g. Physical Damage Return) and moves back to an adjacent unoccupied hex. If it is unambigous which hex the attacker ends up in (the only avaiable hex, their movement only allows for one specific hex, etc.), then we simply append a `#` to the end of the attacked hex to denote retaliation. However, if there are multiple possible hexes the attacker could und up in, we add a `move <hex>` to the end. Example: `UMinor H3#` means that Ursa Minor attempted to attack the unit in **H3**, but it had more than 3 health remaining. In this case, Ursa Minor remains in an adjacent hex to **H3** and takes some damage in retaliation. We currently don't know the full board, but, as no hex is indicated (e.g. `UMinor H3# move H4`) we can assume that **H3** is the unambiguous point for Ursa Minor to end up at.
- The attacker does not kill the defender, but does not take retaliation or damage from the attack (e.g. Backstab) and moves back to an adjacent unoccupied hex. If it is unambigous which hex the attacker ends up in, we append a `*` to the hex. Again, identical rules apply as when retaliation is taken, the only difference is that we use `*` to denote that not only has an attack against a hex been made, but that it wasn't a killing attack and the attacker took no retaliation.

## Active abilities

When a unit uses an active ability, the format generally follows `<unit> <ability keyword> <hex>`, where `<unit>` is the unit using the ability, `<ability keyword>` is an abbreviation to indicate which ability was used, and `<hex>` is the hex targeted by that ability. The full list of ability keywords can be found below. There are two types of active abilities: buffs vs immediate actions.

### Buffs

When a unit grants another unit either a buff or debuff, we denote it as `<unit>: <buff> <target>`. For example, `Tact: +1P Catapult` would mean that the Tactician grants +1 Power to the Catapult. The list of buff/debuff abbreviations are shown below. If the buff/debuff is combinable, the movement goes before the colon: `Angel C2: +2S Hero` would mean that the Angel moves to **C2**, then grants a +2 Shield to the Hero.

### Immediate Actions

---

# Buff/Debuff Abbreviations

---

# Unit Abbreviations

## Arengard Units

## Gath Units

## Sylvan Units

---

# Ability Keyword Abbreviations
