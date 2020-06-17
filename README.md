# Denomination and more

This repository contains resources useful for development and research on pentagame.

## Denomination

Due to recent development with multiple digital versions of pentagame ([boardgame](https://github.com/Penta-Game/boardgame), [pentagame](https://github.com/NikkyAI/pentagame)). The need for an usable identifier system for the fields and events has increased. This system will be implemented in [boardgame backend](https://github.com/Penta-Game/boardgame-backend).

To tackle this problem [Penta](https://github.com/penta-jan) and [Cobalt](https://sinclair.gq) have tried coming up with an easy-to-use system. The requirements were: system should be easy to store in a database *and* must have be comprehensible for a human. To introduce my concept I need to assign some names for points on the board. The "outer" points are called corners, the "inner" points are called junctions. To set a base the junctions and corners are named by integers. Count / name / create corner stops counter-clockwise (0..4) and count / name / create junction stops opposite of those (5..9). The stops are now handled by using two adjacent fields and storing the counter of needed- steps from the first to the second field. If you want to reference a field you just fill the `counter` and `end` with zeros. Set colour and number equivalent: 0= white, 1= green, 2 = yellow, 3=red, 4=blue (you may change the colours as needed). A player figure is named after the corner it stars from/ the colour it bears. Thus, Corner 0 is white and player piece 0 is white.

Gray pieces (5 in total) are denominated as 6-10 and black pieces 11-15. Black pieces are assigned to the junction = number - 11, e.g. piece 11 is on junction 0.

> Field: \[Start, Counter, End\]

If you now attach an identifier for the player with his 5 figures ():

> Move: \[PlayerID, FigureID, Start, Counter, End\]

Examples:

[4, 5, 2, 0, 0] Move by Player 4 with figure 5 to junction 2

[3, 5, 1, 2, 2] Move by Player 3 with figure 5 to the second stop to junction two counted from corner.

If you have any ideas or your own concept open an issue and tell us about it.

### Math

By following this concept a few equations are introduced:

- corner x is at angle (x*\pi/5) and junction (x-5) is at angle (x*\pi/5+\pi/2)
- More are WIP

## Validation

Validation seems like a negligible thing for a simple denomination of fields and moves but for a good and fair game it serves as a base. [boardgame backend](https://github.com/Penta-Game/boardgame-backend) is currently working on this.

## References

- Rules: [Pentgame Rules](https://github.com/Penta-Game/Pentagame-Rulesheets)
- Pentagame (Shop): [pentagame.org](https://pentagame.org)
- Events: WIP
- Creator: [Penta](https://github.com/penta-jan)

For more resources see [denomination/resources](https://github.com/Penta-Game/denomination/blob/master/resources/README.md)
