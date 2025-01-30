# Codsoft-
<details>
<summary><h2>Task 1:SIMPLE CALCULATOR<h2></summary>

<h4>Code:</h4>

print("SIMPLE CALCULATOR")

print("1-Add")
print("2-Substract")
print("3-Multiply")
print("4-Divide")
option=int(input("choose an operation"))
result=0

if(option in [1,2,3,4]):
    n1=float(input("enter first number: "))
    n2=float(input("enter second number: "))
    
    if(option == 1):
        result = n1 + n2
    elif(option ==2):
        result = n1-n2
    elif(option==3):
        result=n1*n2
    elif(option==4):
        result = n1/n2
else:
    print("Invalid operation")  
    
print("The result = {}".format(result))

</details>

<details>
<summary><h2>Task 2:ROCK PAPER SCISSOR<h2></summary>

<h4>Code:</h4>
 
import random
print("INSTRUCTIONS\n Rock beats Scissor\n Scissors beats paper\n Paper beats Rock\n")

def get_choice():
    while True:
        user_choice = input("Enter your choice: Type 0 for Rock, 1 for Paper, 2 for Scissors, or 'y' to stop playing. ")
        if user_choice.lower() == 'no':
            return 'no'
        try:
            user_choice = int(user_choice)
            if user_choice >= 0 and user_choice <= 2:
                return user_choice
            else:
                print("You entered an invalid number. Please try again.")
        except ValueError:
            print("Invalid input. Please try again.")

def winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a draw."
    elif (user_choice == 0 and computer_choice == 2) or \
         (user_choice == 1 and computer_choice == 0) or \
         (user_choice == 2 and computer_choice == 1):
        return "You win!"
    else:
        return "You lose."

def lets_play():
    while True:
        user_choice = get_choice()
        if user_choice == 'no':
            break
        computer_choice = random.randint(0, 2)
        print(f"\nComputer chose: {computer_choice}")
        print(winner(user_choice, computer_choice))

lets_play()

</details>

<details>
<summary><h2>Task 3:PASSWORD GENERATOR<h2></summary>

<h4>Code:</h4>

import random
import string

print("PASSWORD GENERATOR\n")

def password(len):
    characters = string.ascii_letters + string.digits + string.punctuation
    
    password = [                                 # Each type to be included
        random.choice(string.ascii_lowercase),
        random.choice(string.ascii_uppercase),
        random.choice(string.digits),
        random.choice(string.punctuation)
    ]
    
    for _ in range(len - 4):
        password.append(random.choice(characters))
    
    random.shuffle(password) # Shuffling
    
    return ''.join(password)

len = int(input("Enter the length of Password: ")) # Password length

print("The Generated Password is : ", password(len)) # Generate password

</details>
