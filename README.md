# 井字棋 <sub>&ensp;&emsp;&emsp;&emsp;<sup>极小极大算法</sup></sub> <br> Tic Tac Toe <sub>&emsp;<sup>Minimax Algorithm</sup></sub>

[![LICENSE](https://img.shields.io/github/license/bugstop/tic-tac-toe-game)](https://github.com/bugstop/tic-tac-toe-game)
[![codebeat badge](https://codebeat.co/badges/24c8b2cc-3809-4d16-a1af-adbb35b5fb5d)](https://codebeat.co/projects/github-com-bugstop-tic-tac-toe-game-master)
[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu) <br>

### [**_Webpage Demo_**](https://tictactoe.demo.lmh.li/)

#### How to Play Tic Tac Toe

![TicTacToe](./img/game.png)

<br>

## Algorithms

### 1. British Museum

The **British Museum algorithm** is a general approach to find a solution by checking all possibilities one by one, beginning with the smallest.

### 2. Minimax

**Minimax** is a decision rule for **minimizing** the possible loss for a worst case (**maximum** loss) scenario. When dealing with gains, it is referred to as "maximin" — to maximize the minimum gain.  
The **maximin value** of a player is the highest value that the player can be sure to get without knowing the actions of the other players; equivalently, it is the lowest value the other players can force the player to receive when they know the player's action.

![Minimax](./img/mm.png)

### 3. Alpha–beta Pruning

**Alpha–beta pruning** is a search algorithm that seeks to decrease the number of nodes that are evaluated by the minimax algorithm in its search tree.

![AlphaBeta](./img/ab.png)

The grayed-out subtrees don't need to be explored (when moves are evaluated from left to right), since we know the group of subtrees as a whole yields the value of an equivalent subtree or worse, and as such cannot influence the final result.

The pseudo-code for depth limited minimax with alpha-beta pruning is as follows:

```
function alphabeta(node, depth, α, β, maximizingPlayer) is
    if depth = 0 or node is a terminal node then
        return the heuristic value of node
    if maximizingPlayer then
        value := −∞
        for each child of node do
            value := max(value, alphabeta(child, depth − 1, α, β, FALSE))
            α := max(α, value)
            if α ≥ β then
                break (* β cut-off *)
        return value
    else
        value := +∞
        for each child of node do
            value := min(value, alphabeta(child, depth − 1, α, β, TRUE))
            β := min(β, value)
            if α ≥ β then
                break (* α cut-off *)
        return value
```
