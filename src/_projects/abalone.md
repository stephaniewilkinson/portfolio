---
layout: post
title:  "Abalone"
date:   2008-01-19
category: Open source
image_url: './images/abalone.jpg'
blurb: "A playable, in-browser version of the strategy game Abalone."
tags:
- javascript
- angular
---

_A playable, in-browser version of the strategy game Abalone._

&nbsp;

Abalone is a challenging game of strategy that for two players. Each take turns moving marbles around the board, with the objective to remove other player's marbles.

&nbsp;

Since Abalone is a relatively little-known game, user experience is foremost. Rather than showing all moves and alerting the user when they pick an invalid move, the UI only shows arrows for possible move directions. In addition, arrows turn red when you are interacting with opponent marbles for further user education.

&nbsp;

Another facet of the user experience design is the highlighted marbles to show valid next selections. For users who are unfamiliar with the rules of Abalone, this helps to educate them on how many of their own marbles they can select to move.

## References

+ http://entertainment.howstuffworks.com/leisure/brain-games/abalone2.htm
+ http://www.cs.nott.ac.uk/~pszeo/docs/publications/ABLA_id136final.pdf

&nbsp;

### Initial concept
I planned to use the official notation for marble coordinates, similar to chess notation. This would mean that cells are oriented along an A-I and 1-9 axis. However, this kind of notation didn't lend itself well to an array data structure, so I decided to use rows and columns, in an array of cell objects.

&nbsp;

### Challenges
Abalone is a complex game because each player can select up to three marbles, and can move in as many as six directions. In addition, interactions with other players follow a strict set of rules and a lot of logic had to be written in to include those rules.
