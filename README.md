# Snake , Water , Gun Game

name = input('Enter Your Name:')
age = int(input('Enter your Age:'))
print (f"Hello {name} ")
if age > 18:
    print("You are over 18 \nEligible")
else:
    print("You are not over 18")
    quit('NOT ELIGIBLE')
     
 
import random

def check(computer, you):
    if computer == you:
        return 0
    # 1: snake, 2: water, 3: gun
    if (computer == 1 and you == 2) or (computer == 2 and you == 3) or (computer == 3 and you == 1):
        return -1
    else:
        return 1
    
    

for _ in range(10):
    computer = random.randint(1, 3)
    print(f"computer: {computer}")
    try:
        you = int(input("1 for snake, 2 for water, 3 for gun: "))
    except ValueError:
        print("Invalid input, please enter 1, 2, or 3")
        continue
    print(computer)
    if you not in (1, 2, 3):
        print("Please enter 1, 2 or 3")
        continue

    result = check(computer, you)
    if result == 0:
        print("It's a tie")
    elif result == 1:
        print("You win")
    else:
        print("Computer wins")
