# Hangman 
# Changed Hangman
``` mermaid
flowchart TD
    Start["Start Hangman Game"] --> ChooseWord["Choose a random word"]
    ChooseWord --> Initialize["Initialize: guessed_letters = {}, attempts = 6"]
    Initialize --> DisplayWord["Display current word state"]
    DisplayWord --> Input["Prompt user for a letter"]

    Input -->|Invalid input| Invalid["Print 'Please enter a valid character'"]
    Invalid --> DisplayWord

    Input -->|Already guessed| AlreadyGuessed["Print 'You already guessed that letter'"]
    AlreadyGuessed --> DisplayWord

    Input -->|Valid guess| ProcessGuess["Add letter to guessed_letters"]

    ProcessGuess -->|Correct guess| Correct["Print 'Correct!'"]
    Correct --> CheckWin["Check if all letters are guessed"]

    ProcessGuess -->|Wrong guess| Wrong["Print 'Wrong!', Decrease attempts by 1"]
    Wrong --> CheckAttempts["Check if attempts > 0"]

    CheckAttempts -->|Attempts > 0| DisplayWord
    CheckAttempts -->|Attempts == 0| GameOver["Print 'Game over! The word was: [word]'"]

    CheckWin -->|All letters guessed| Victory["Print 'Congratulations! You guessed the word!'"]
    CheckWin -->|Not all guessed| DisplayWord
```
