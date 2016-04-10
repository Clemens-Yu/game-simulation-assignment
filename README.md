def craps(n):
    # import the library
    import random
    # main program starts here
    probability = 0
    finish = 0
    win = 0
    for i in range(0, n):
        finish = 0
        firsttime = 1
        # beginining of a game
        while (finish == 0):
            value = random.randrange(1, 13)
            if firsttime == 1:
                # execute this part when the dice is thrown the first time
                 if value == 7 or value == 11:
                    # print "You win."
                    finish = 1
                    win = win + 1
                 elif value == 2 or value == 3 or value == 12:
                    # print "You lose."
                    finish = 1
                 firsttime = 0
                 initial_value = value
            else:
                # execute this part when the dice is thrown after the frist time
                if value == 7:
                    # print "You lose."
                    finish = 1
                elif value == initial_value:
                    # print "You win."
                    finish = 1
                    win = win + 1
        # end of a game
# end of n games
    return win
def main():
    print craps(500) / 500.0
if __name__ == '__main__':
    main()
    
Doctest File:
>>> from game_simulation_partnerA_partnerB import *

General Case #1:
>>> w = craps(500)
>>> 200 < w and w < 300
True

General Case #2:
>>> w = craps(1000)
>>> 300 < w and w < 500
True

Unusual Case #1: Negative Number of Games
>>> craps(-2)
0
