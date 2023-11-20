# RockPaperScissorsGame
import random

def check(comp, user):
    if comp == user:
        return 0
    if comp == 0 and user == 1:
        return -1
    if comp == 1 and user == 2:
        return -1
    if comp == 2 and user == 0:
        return -1
    return 1

while True:
    comp = random.randint(0, 2)
    user_input = input("Enter 0 for rock, 1 for paper, 2 for scissors, or 'e' to exit: ")

    if user_input.lower() == 'e':
        break  # Exit the loop if 'e' is entered

    try:
        user = int(user_input)

        if user not in (0, 1, 2):
            print("Invalid input. Please enter 0, 1, 2, or 'e' to exit.")
            continue

        score = check(comp, user)

        if score == 0:
            print("It's a draw")
        elif score == -1:
            print("You lose")
        else:
            print("You won")
    except ValueError:
        print("Invalid input. Please enter 0, 1, 2, or 'e' to exit.")

