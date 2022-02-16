# Notation Guide

This document contains the most up-to-date list of notation used.

## Format

The document is broken up into 8 sections: one section detailing the draft information, and 7 sections for each of the 7 rounds. Each of the 7 round sections follow the same format, and the exact format of the draft section depends on whether the game is a blitz or draft game.

In any game, `Player 1` is the player with the **A1** hex on their bottom left, regardless of who acts first.

---

## Draft Section

### Blitz

As the card positions are fixed for blitz games, the only things to note are the gold limit and the hero. Therefore, the section has the following format

    Draft - Blitz <Gold Limit>
    <Player 1>: <Hero>
    <Player 2>: <Hero>
    
### Draft

For draft games, we need to note the gold limits of both the kingdoms and armies, and the specific cards and their placements. Therefore, the format has a lot more information. We list out the full 9 hexes for each row of each player, as well as the hero, abilities and items used. If a specific hex is empty, we indicate this with an `X`. Note that order is listed in the order of each players' PoV, from left to right.

    Draft - <Kingdom Gold> draft <Army Gold>
    <Player 1>: <Hero>. <Abilities>. <Items>
    Front: <A2>, <B2>, <C2>, <D2>, <E2>, <F2>, <G2>, <H2>, <I2>
    Back: <A1>, <B1>, <C1>, <D1>, <E1>, <F1>, <G1>, <H1>, <I1>
    
    <Player 2>: <Hero>. <Abilities>. <Items>
    Front: <I6> <H5> <G6> <F5> <E6> <D5> <C6> <B5> <A6>
    Back: <I7> <H6> <G7> <F6> <E7> <D6> <C7> <B6> <A7>
    
For example, below is a screenshot showing a draft setup, along with the correct draft notation (names anonymised).

![example set up](https://imgur.com/a/NjcvZa0)

    Draft - 160 draft 80
    Bob: Kaar'thul. Chain Lightning 3, Lightning Bolt 3. Bulwark Boots, Arcane Stone, Buckler.
    Front: X, Char, WRider, Grunt, GTrench, Grunt, WArcher, Char, X
    Back: X, DHatch, X, TDoctor, Hero, CWyvern, X, SCH, X

    Alice: Kaladrix. Velocity Greaves.
    Front: GHawk, CGuard, NGH, UMinor, Hero, UMajor, NGH, DProc, GHawk
    Back: X, DSen, Wisp, DMystic, TBow, NSorc, Wisp, DSen, X
