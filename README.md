import random

# List of names for the puzzle
names = ["Nithya", "Ganesh", "Pradeep", "Chanikya", "Bealuah", "Dharani"]

def shuffle_name(name):
    name_letters = list(name)
    random.shuffle(name_letters)
    return ''.join(name_letters)

def start_game():
    print("Welcome to the Name Puzzle Game!")
    score = 0
    rounds = 3

    for _ in range(rounds):
        # Pick a random name
        original_name = random.choice(names)
        scrambled = shuffle_name(original_name)

        # Ask user to guess
        print(f"Unscramble this name: {scrambled}")
        guess = input("Your guess: ").strip()

        if guess.lower() == original_name.lower():
            print("Correct!")
            score += 1
        else:
            print(f"Wrong! The correct name was: {original_name}")
        print()

    print(f"Game Over! Your score: {score}/{rounds}")

if __name__ == "__main__":
    start_game()
