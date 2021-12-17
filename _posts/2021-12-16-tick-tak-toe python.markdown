---
layout: post
title:  "pyhton tick tak toe"
date:   2021-12-12 21:24:41 +1100
categories: [code ,python]
---
Python tic tak toe game

{% highlight java %}
def game():
    poss = []
    game_end = True
    board(poss)
    show(poss)
    player = 'x'

    while game_end:
        play(poss, player)
        show(poss)
        game_end = end(poss, game_end)
        if player == 'x':
            player = 'o'
        else:
            player = 'x'
    
def board(poss):
    for x in range(3):
        row = []

        for z in range(3):
            row.append('-')
        poss.append(row)

def show(poss):
    for x in poss:
        for z in x:
            print(z, end='')
        print()

def play(poss, player):
    invalid = True
    while invalid:
        row = int(input('Player {} pick a row: ' .format(player)))
        column = int(input('Player {} pick a column: ' .format(player)))

        if (row > 3 or row < 0) or (column > 3 or column < 0):
            print('Invalid spot')
        else:
            poss[row - 1][column - 1] = player
            invalid = False

def end(poss, con):
    full = 0
    for x in poss:
        for z in x:
            if z != '-':
                full += 1

    if full == 9:
        print("draw")
        return False
    
    for x in poss:
        if (x[0] == x[1] and x[1] == x[2]) and (x[1] == 'x' or x[1] == 'o'):
            print("player {} wins" .format(x[0]))
            return False
    
    for x in range(3):
        if (poss[0][x] == poss[1][x] and poss[1][x] == poss[2][x]) and (poss[1][x] == 'x' or poss[1][x] == 'o'):
            print("player {} wins" .format(poss[1][x]))
            return False
    
    if (poss[0][0] == poss[1][1] and poss[1][1] == poss[2][2]) and (poss[1][1] == 'x' or poss[1][1] == 'o'):
        print("player {} wins" .format(poss[1][1]))
        return False

    if (poss[0][2] == poss[1][1] and poss[1][1] == poss[2][0]) and (poss[1][1] == 'x' or poss[1][1] == 'o'):
        print("player {} wins" .format(poss[1][1]))
        return False
        
    return True
        

if __name__ == "__main__":
    game()
{% endhighlight %}