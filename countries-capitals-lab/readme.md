# Let's Learn Countries Capitals

We're going to create a game to help us memorize the names of some capitals of countries.

## Game Features:

- Provide a welcome message to introduce the player to the game.

- Your game should prompt the user to enter the capital associated with a given country.
  > Make sure the countries don't appear in alphabetical order in the prompts. This will make the game a bit more challenging for the user.

- There should be running tallies on the number of correct and incorrect answers **for each country**.

- After getting through all countries one time, users should be given the chance to play again.

- After a user enters their answer, display a message telling the user how many times the state was answered correctly out of the total number of times the state has been answered.


## Getting Started

You're given an array of hashes that contain each country name and capital in `capitals.rb`. Do all of your work in this file.

### Hints

- For the purposes of developing this program, start with a test array of three hashes so you don't have to play through all countries each time.

- Initialize new keys in each country's Hash to store the number of times a user gets a capital `correct` and the number of times the answer is `wrong`.
  > Recall that Hashes are Ruby's equivalent of javascript object literals

- Through all countries, prompt the user to name the capital of the country.

  - If the answer is correct, display a message saying so, and increment the `correct` key.
  - If the answer is wrong, display a message saying so, and increment the `wrong` key.
  
- If you ever need to manually stop your Ruby script, enter <kbd>CTRL</kbd> + <kbd>C</kbd>

### Potentially Useful Methods

- `puts`

- `gets`

- `.map`

- `.each`

- `.sort_by`

- `.shuffle`

## Bonus!

- If the user plays again, set the order of how the prompts appear to start with the ones they got wrong the most often.

- Calculate an overall total score, display a running tally for each prompt.

- Add a hint functionality that prints the first 3 letters of a capital.

