# Denomination and more

This repository contains resources useful for development and research on pentagame.

## Denomination

Due to recent development with multiple pentagame digital games ([boardgame](https://github.com/Penta-Game/boardgame), [pentagame](https://github.com/NikkyAI/pentagame)). The need (at least for me ;)) for an unique identifier system for the fields and events has increased. This system will be implemented in [boardgame backend](https://github.com/Penta-Game/boardgame-backend).

To tackle this problem I have tried coming up with an easy-to-use system. The requirements were: system should be easy to store in a database *and* must have be comprehensible for a human. To introduce my concept I need to name some points for orientation on the board. The "outer" points are called corners, the "inner" points are called junctions. To set a base the junctions and corners are named by integers. To get these start on the top left junction and count from 1 clockwise. If finished continue with the next number (5) on the corners from the top corner clockwise. Repeat this for the corners starting from 6 and you have unique identifiers for the Fields. The stops are now handled by Using two adjacent fields and storing the counting the steps from the first to the second field. If you want to reference a field you just fill the `counter` and `end` with zeros. A player figure is named after the junction (6-10) it started on.

> Field: \[Start, Counter, End\]

If you now attach an identifier for the player with his 5 figures ():

> Move: \[PlayerID, FigureID, Start, Counter, End\]

Examples:

[4, 5, 1, 2, 0, 0] Move by Player 4 with figure 5 to junction 2

[3, 7, 1, 1, 2, 2] Move by Player 3 with figure 7 to the second stop to junction two counted from corner .

## Validation

Validation seems like a negligible thing for a simple denomination of fields and moves but for a good and fair game it serves as a base. [boardgame backend](https://github.com/Penta-Game/boardgame-backend) is currently working on this.

## Resources

- Rules: [Pentgame Rules](https://github.com/Penta-Game/Pentagame-Rulesheets)
- Pentagame (Shop): [pentagame.org](https://pentagame.org)
- Events: WIP
- Creator: [Penta](https://github.com/penta-jan)

For more resources see [denomination/resources](https://github.com/Penta-Game/denomination/blob/master/resources/README.md)
