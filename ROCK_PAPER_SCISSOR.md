# my_codes_python
import random

options=["ROCK","PAPER","SCISSOR"]
player= None
computer= random.choice(options)
kk=int(input("Enter Score limit:"))
h = 0
j = 0
while h<=kk and j<=kk:
    # kk = int(input("Enter Score limit:"))
    player=input(f"select rock: paper: scissor:")
    player=player.upper()
    print(f" Player:{player}")
    print(f" Computer:{computer}")
    x="PLAYER WON"
    y="COMPUTER WON"

    if player=="ROCK" and computer=="PAPER":
        print(y)
        if y=="COMPUTER WON":
            j=j+1
        print(f"Computer point is:{j}")

    elif player=="ROCK" and computer=="SCISSOR":
        print(x)
        if x=="PLAYER WON":
            h=h+1
        print(f"Player point is:{h}")

    elif player=="PAPER" and computer=="ROCK":
        print(x)
        if x=="PLAYER WON":
            h = h + 1
        print(f"Player point is:{h}")

    elif player=="PAPER" and computer=="SCISSOR":
        print(y)
        if y=="COMPUTER WON":
            j=j+1
        print(f"Computer point is:{j}")

    elif player=="SCISSOR" and computer=="ROCK":
        print(y)
        if y=="COMPUTER WON":
            j=j+1
        print(f"Computer point is:{j}")

    elif player=="SCISSOR" and computer=="PAPER":
        print(x)
        if x=="PLAYER WON":
            h=h+1
        print(f"Player point is:{h}")

    elif player==computer:
        print("Match draw")

    else:
        print("Error")

else:
    pass
    print("Match Result:")
    print(f"Your Final point is:{h}")
    print(f"Computer Final point is:{j}")

