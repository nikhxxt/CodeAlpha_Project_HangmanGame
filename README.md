import random

def choose_word():
    flowers = ["rose", "lily", "tulip", "daisy", "orchid"]
    return random.choice(flowers)

def display_word(word, guessed_letters):
    display = ""
    for letter in word:
        if letter in guessed_letters:
           display += lettter + " "
        else:
                display += "_"
        return display.strip()
      
def hangman():
    print("Welcome to hangman!")
    print("Lets strat the game.")
    print("Hint: The words are names of flowers.")
    print("You have only 6 tries to guess the word.")
    word = choose_word()
    guessed_letters = []
    incorrect_guessses = 0
    max_incorrect_guesses= 6

    while incorrect_guesses < max_incorrect_guesses:
        print("\nWord:", display_word(word,guessed_letters))
        guess = input("Guesss a letter: ").lower()

    if len(guesss) != 1 or not guess.isalpha():
         print("Please enter a single alphabetic character.")
         continue

    if guess in guessed_lettters:
       print("You already guesed that letter! try another one.")
    elif guess in word:
        print("Correct!")
        guessed_letters.append(guess)
   else:
       print("Incorrect!")
       incorrect_guesses += 1
       guessed_letters.append(guess)

       if set(word) <= set(guessed_letters):
          print("\nCongratulations! You guessed the word:", word)
          break

       print("Tries left:", max_incorrect_guesses - incorrect_guesses)

  if incorrect_guesse >= max_incorrect_guesses:
     print("\nSorry, you ran out of guesses. The word was:",word)


hangman()
