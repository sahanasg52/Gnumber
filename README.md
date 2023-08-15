# Gnumber
import random
def generate_target_number():
    return random.randint(1, 50)

def calculate_score(attempts):
    base_score = 50
    penalty = 10
    return max(base_score -(attempts * penalty), 0)


def play_guess_the_number():
    target_number = generate_target_number()
    max_attempts = 4
    attempts = 0
    score = 0

    while attempts < max_attempts:
        user_guess = int(input("Guess a number between 1 and 50:  "))
        attempts +=1

        if user_guess == target_number:
            print(f" Congratulations! You guessed the number {target_number} in {attempts} attempts. ")
            score = calculate_score(attempts)
            print(f" Your score: {score}")
            break


        elif user_guess > target_number:
            print("Too high! Try again.")
        else:
            print("Too low! Try again.")

    if attempts >= max_attempts:
        print(f"Sorry, you reached the maximum number of attempts. The target was {target_number}. ")

    play_again = input("Do you want to play again? (yes/no): ").lower()
    if play_again == "yes":
        play_guess_the_number()
    else:
        print("Thanks for playing ")

if __name__ == "__main__":
    print("Welcome to the Guess the Number game!")
    play_guess_the_number()

            
