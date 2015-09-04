Poker Hands Code Kata
=====================

You have been hired by a client who is a bit rubbish at poker.  Specifically, they can't work out whether their poker
hand is good or bad.  They need some tools to help them play the game.

Here is some reference information about poker hands:

 - **Royal Flush**  As Straight Flush, specifically ace high, e.g.: *TC,JC,QC,KC,AC* 
 - **Straight Flush**  As Straight and as Flush at the same time, e.g.: *8C,9C,TC,JC,QC* 
 - **4 of a Kind**  Four cards of the same number, e.g.: *JC,JH,JS,JD,3H*
 - **Full House**  As 3 of a Kind and a Pair at the same time, e.g. *JC,JH,JS,2D,2S*
 - **Flush**  Five cards of the same suit, e.g. *JC,7C,5C,AC,2C*
 - **Straight**  Five sequentially numbered cards.  Aces are high or low.  E.g. *AC,2H,3S,4D,5S*
 - **3 of a Kind**  Three cards of the same number, e.g.: *JC,JH,JS,AD,3H*
 - **Two Pair**  As a Pair, except twice, e.g. *JC,JH,5S,5D,2S*
 - **Pair**  Two cards of the same number, e.g. *JC,JH,7S,8D,3S*
 - **High Card**  No other hand, player with the highest single card wins.  E.g. *AC,3D,7S,8D,2S*

Here are your client's requirements:

1. Naming All Hands
-------------------

The requirement is that, for a given input, the name of all hands it meets the criteria of is output.

```
> php scripts/run.php all-hands-available 4C,5C,6C,7C,8C
> Straight Flush (8 high), Straight (8 high), Flush (8 high)
```

2. Naming the Best Hand
-----------------------

The requirement is that, for a given input, the name of the best hand is output.

```
> php scripts/run.php name-hand 4C,5C,6C,7C,8C
> Straight Flush (8 high)
```

The name returned is the name of the highest value hand - the above example meets the criteria for a Straight, a Flush
and a Straight Flush, but the Straight Flush is the best, so it is the hand returned.

3. Working Out Who's Won
------------------------

Two hands are presented.  Output says which hand wins, and what they both were.

```
> php scripts/run.php who-wins 4C,5C,6C,7C,8C 4C,5D,6H,7D,8S
> Player 1 wins - Straight Flush (8 high) vs Straight (8 high)
```

```
> php scripts/run.php who-wins 4C,5C,6C,7C,8C 7D,8D,9D,TD,JD
> Player 2 wins - Straight Flush (8 high) vs Straight (Jack high)
```

4. Finding the Best Hand in Texas Hold'em
-----------------------------------------

The above rules are for 5 Card Draw.  Texas Hold'em is slightly different: each player has two private cards, and the
players share five communal cards.  Your hand is whatever is the best five-card combination available, from any of the
seven cards available.

```
> php scripts/run.php holdem KD,KS KH,3D,2D,AD,AS
> Best 5-card hand: KD,KS,KH,AD,AS - Full House (kings and aces)
```
