#  for generating a random number we have to import random
import random

# defining function
def number_guessing_game():
    print("WELCOME TO  THE NUMBER GUESSING GAME! \n")
    player_name = input("Enter your name:  ")
    print("Hello,{}! I'm thinking of a number between 1 to 100.\n".format(player_name))
    print("You have 10 attempts to guess the correct number. \n")


    while True:
        secret_number = random.randint(1,100)
        attempts = 0

        while attempts < 10:
            guess = int(input("attempt{}: \n\n enter your guess: ".format(attempts + 1)))

            if guess < secret_number:
                print("your guess is too low!Try again \n")
            elif guess > secret_number:
                print("your guess is too high!Try again \n")
                print("\n")
            else:
                print("CONGRATULATIONS,{}! You Guessed the number {} in {} attempts".format(player_name,secret_number,attempts+1))
                print("\n")

                break
            attempts += 1

        if attempts == 10:
            print("SORRY, {}! you've use all your attempts. The secret number was {} \n".format(player_name,secret_number))



        play_again=input("Do you want to play again? (yes/no):  ")
        print("\n")
        if play_again.lower()!='yes':
            print("\n")
            print("THANK YOU for PLAYING!")

            break

number_guessing_game()
