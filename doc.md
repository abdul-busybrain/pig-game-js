---

## Pig Game Pseudocode and Explanation

### Step 1: Setup

- **Select HTML Elements**: Choose the dice, player containers, current score displays, score displays, and buttons for actions like starting a new game, rolling the dice, and holding the current score.

```markdown
- Select elements like `<div class="dice">`, `<div class="player--0">`, etc., and store them in variables.
```

### Step 2: Initialize Game State

- **Set Initial Scores**: Start with scores of 0 for both players.
- **Hide Dice Initially**: The dice image starts hidden until a roll action occurs.
- **Define Game Variables**: Create arrays and variables to manage scores, current score, and active player.

```markdown
- Set `score0El.textContent = 0;` and `score1El.textContent = 0;` to start with zero scores.
- Add `"hidden"` class to `diceEl` to hide the dice initially.
- Define `scores = [0, 0];`, `currentScore = 0;`, and `activePlayer = 0;` to manage game state.
```

### Step 3: Switch Players Function

- **Switch Players**: After certain conditions (like rolling a 1), switch to the other player. Reset the current score and toggle the active player indicator.

```markdown
- Define a function `switchPlayer()` that resets the current score, switches the active player, and toggles the active player's visual indicator.
```

### Step 4: Roll Dice Action

- **Generate Random Number**: On clicking the roll button, generate a random number between 1 and 6.
- **Display Dice Image**: Show the dice image with the generated number.
- **Update Score**: If the number is not 1, add it to the current score. If it's 1, switch to the next player.

```markdown
- Attach a click event to `btnRoll`. Inside this event:
  - Generate a random number and update the dice image accordingly.
  - If the number is not 1, add it to `currentScore`.
  - If the number is 1, call `switchPlayer()` to switch to the next player.
```

### Step 5: Hold Score Action

- **Add Current Score**: On clicking the hold button, add the current score to the active player's total score.
- **Check for Win Condition**: If the player's score reaches or exceeds 100, end the game. Otherwise, switch to the next player.

```markdown
- Attach a click event to `btnHold`. Inside this event:
  - Add `currentScore` to the active player's total score.
  - Check if the player's total score is 100 or more. If so, end the game and show the winner.
  - If not, call `switchPlayer()` to switch to the next player.
```

---
