import random

'''
1 for snake
-1 for water 
0 for gun
'''

# Computer makes a random choice
computer = random.choice([1, -1, 0])

# User input
youstr = input("Enter your choice (s/snake for snake, w/water for water, g/gun for gun): ").lower().strip()

# Mapping dictionaries
youDict = {
    "s": 1,
    "snake": 1,
    "w": -1,
    "water": -1,
    "g": 0,
    "gun": 0,
}
reverseDict = {1: "snake", -1: "water", 0: "gun"}

# Convert user input to corresponding value
if youstr not in youDict:
    print("Invalid input! Please choose from s, w, g or their full forms.")
else:
    you = youDict[youstr]
    print(f"You chose: {reverseDict[you]}")
    print(f"Computer chose: {reverseDict[computer]}")

    # Determine winner
    if computer == you:
        print("It's a tie!")
    elif (computer == -1 and you == 1) or (computer == 1 and you == 0) or (computer == 0 and you == -1):
        print("You Win!")
    else:
        print("You Lose!")
