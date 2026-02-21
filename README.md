# Computer Architectures: Tetris (First Edition)

## 📌 Project Overview
[cite_start]This project is a simplified implementation of **Tetris** developed for the **Land Tiger Board (LPC1768)**[cite: 82]. [cite_start]It was created for the course *Architetture dei Sistemi Di Elaborazione* (Computer Architectures) [cite: 1, 3] [cite_start]to demonstrate proficiency in the **KEIL µVision** software debug environment[cite: 15, 32].

* [cite_start]**Target Hardware**: Land Tiger Board / LPC1768 Emulator[cite: 32].
* [cite_start]**Compilation Target**: `SW_Debug` for emulation[cite: 15, 32].

---

## 🎮 Game Mechanics
[cite_start]The game follows traditional Tetris rules with specific implementation details for the Land Tiger hardware[cite: 82]:

### Playing Field & UI
* [cite_start]**Grid Size**: A playing field consisting of $20\times10$ squares[cite: 87, 89].
* [cite_start]**Display Layout**: The left side shows the playing field, while the right side displays the **Current Score**, **High Score**, and **Cleared Line** count[cite: 88].
* [cite_start]**Tetrominoes**: All seven standard shapes (I, O, T, J, L, S, Z) are implemented as global variables[cite: 97, 99, 101, 103, 105, 107, 109, 111].



### Controls
[cite_start]The game utilizes the board's joystick and buttons for interaction[cite: 122]:

| Input | Action |
| :--- | :--- |
| **KEY1** | [cite_start]Starts the game (after reset) or toggles between "paused" and "playing" states[cite: 92, 93]. |
| **KEY2** | [cite_start]**Hard Drop**: Current tetromino falls instantly[cite: 126]. |
| **Joystick Up** | [cite_start]Rotates the tetromino $90^{\circ}$ clockwise[cite: 122]. |
| **Joystick Left/Right** | [cite_start]Moves the tetromino horizontally[cite: 122]. |
| **Joystick Down** | [cite_start]**Soft Drop**: Increases fall speed to 2 squares/second while held[cite: 124]. |

---

## 📈 Scoring System
[cite_start]Points are awarded to incentivize clearing multiple lines at once[cite: 133]:

* [cite_start]**Tetromino Placement**: 10 points[cite: 133].
* [cite_start]**Single Line Clear**: 100 points + 10 points for placement[cite: 134].
* [cite_start]**Multiple Line Clear**: ($100 \times \text{number of cleared lines}$) + 10 points for placement[cite: 135].
* [cite_start]**Tetris (4 lines)**: 600 points + 10 points for placement[cite: 136].

---

## ⚠️ Important Implementation Details
* [cite_start]**Default Speed**: Without interaction, tetrominoes fall at a rate of 1 square per second[cite: 121].
* [cite_start]**Game Over**: The game ends if a placed tetromino goes over the top or if a new piece overlaps an existing block upon generation[cite: 137, 138].
* [cite_start]**High Score**: If the final score exceeds the current high score, it is saved for the next session[cite: 139].

