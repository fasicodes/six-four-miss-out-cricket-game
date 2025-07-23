import time

import random

player = [
    "fasiullah", 'jawad', "dani", "shayan", "fazi bahi", "manibahi",
    "ahsibahi", "sani", "fazan baber", "rizwan"
]

indent = 0
runs = 0
whiket = 0
over = 0
ball = 0
if ball == "6":
    over = over + 1

first_ball = print("first ball is comming :")
while True:

    ball = ball + 1
    if ball == 6:
        over = over + 1
        ball = 0
    print(f"\n over = {over}.{ball}")
    if over == 20:
        print("match is over")
        break
    time.sleep(2)
    side = input(
        "which side you hit a ball : (L for lift) (R for right) (F for front) (b for back) : "
    )

    if (side == "l") ^ (side == "r") ^ (side == "f") ^ (side == "b"):
        scores = [
            1,
            1,
            1,
            2,
            2,
            2,
            2,
            3,
            "wide",
            4,
            4,
            4,
            4,
            0,
            0,
            0,
            0,
            6,
            6,
            "out",
            "wide",
        ]
        score = random.choice(scores)

        if score == "out":
            whiket = whiket + 1
            indent = indent + 1
            print(score)
            time.sleep(5)
            if whiket == 1:
                break
        elif score == "wide":
            print(score)
            runs = runs + 1
        else:
            print(score)
            runs = runs + score

    else:
        print("you enter the wrong key ")
        break

    print(f"the player is  {player[indent]}")
    print(f"the runs/whiket is {runs}/{whiket}")
