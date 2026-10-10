# Rock Paper Scissors

A Rock, Paper, Scissors game for [Scratch](https://scratch.mit.edu/) 3.0 (`Rock_Papers_Scissors.sb3`). You play against the computer using the keyboard. Both sides "speak" their move in speech bubbles, and scores are tracked on screen.

## How to run

1. Open the [Scratch editor](https://scratch.mit.edu/projects/editor/) (or the desktop app).
2. Choose **File → Load from your computer** and select `Rock_Papers_Scissors.sb3`.
3. Click the **green flag**.

## How to play

1. **Unlock the game.** After the green flag, the computer says *"You can only play if you roll a dice"* and asks **"Pick a number between 1 and 6"**. Type a number and press Enter.
   - The game checks your answer against a random 1–6 roll, up to 10 times.
   - On a match, it says *"Starting Game"* and resets both scores to 0.
2. **Play a round.** Press a key:

   | Key | Your move |
   |-----|-----------|
   | `r` | Rock |
   | `p` | Paper |
   | `s` | Scissors |

3. The computer picks randomly at the same moment (1 = Rock, 2 = Paper, 3 = Scissors). Its sprite announces its move and your sprite announces the result: **Draw**, **You Win!** or **Computer Wins**.
4. Scores are shown in the stage variable monitors (`player score`, `computer score`).

### Rules

- Rock beats Scissors
- Scissors beats Paper
- Paper beats Rock
- Same move is a draw

## Project structure

| Sprite / Stage | Role |
|----------------|------|
| **Computer** | Shows the intro, runs the "dice" check procedure, and picks and announces the computer's move on any key press. |
| **PlayerComputerDotSprite1** | Handles the `r`, `p` and `s` key presses, compares them with the computer's choice, announces the result and updates scores. |
| **Stage** | Holds the variables and the backdrops (`backdrop1`, `Boardwalk`). |

**Variables:** `computers choice`, `computer score`, `player score`, `your choice`, `Round Number`, `x factor`.

## Known issues / ideas for improvement

- **Rock win doesn't score.** When you win with Rock, the script increases `your choice` instead of `player score`. This is probably a typo.
- **Unused variables.** `Round Number` and `x factor` are never used.
- **The dice gate can fail silently.** A new random number is rolled on each of the 10 checks and nothing happens if none match. The game never says "try again", and the key controls work even without passing it.
- **Possible timing race.** The computer's pick and the player's comparison both trigger on the same key press. They are separate scripts, so the result can occasionally use the previous round's pick. Using a broadcast, or picking the computer's move inside the player's script, would fix this.
- Ideas: a round counter, a first-to-N winner, and play-again handling.

## Assets

The project includes SVG and PNG costumes and backdrops, plus three sounds (`pop`, `Meow`, `bark`) from the Scratch library.
