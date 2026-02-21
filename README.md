# Computer Architectures: Tetris (First Edition)

## 📌 Project Overview
This project is a simplified implementation of **Tetris** developed for the **Land Tiger Board (LPC1768)**. It was created for the course *Architetture dei Sistemi Di Elaborazione* (Computer Architectures) to demonstrate proficiency in the **KEIL µVision** software debug environment.

* **Target Hardware**: Land Tiger Board / LPC1768 Emulator.
* **Compilation Target**: `SW_Debug` for emulation.

---

## 🎮 Game Mechanics
The game follows traditional Tetris rules with specific implementation details for the Land Tiger hardware:

### Playing Field & UI
* **Grid Size**: A playing field consisting of $20\times10$ squares.
* **Display Layout**: The left side shows the playing field, while the right side displays the **Current Score**, **High Score**, and **Cleared Line** count.
* **Tetrominoes**: All seven standard shapes (I, O, T, J, L, S, Z) are implemented as global variables[cite: 97, 99, 101, 103, 105, 107, 109, 111].



### Controls
The game utilizes the board's joystick and buttons for interaction:

| Input | Action |
| :--- | :--- |
| **KEY1** | Starts the game (after reset) or toggles between "paused" and "playing" states. |
| **KEY2** | **Hard Drop**: Current tetromino falls instantly[cite: 126]. |
| **Joystick Up** | Rotates the tetromino $90^{\circ}$ clockwise. |
| **Joystick Left/Right** | Moves the tetromino horizontally. |
| **Joystick Down** | **Soft Drop**: Increases fall speed to 2 squares/second while held. |

---

## 📈 Scoring System
Points are awarded to incentivize clearing multiple lines at once:

* **Tetromino Placement**: 10 points.
* **Single Line Clear**: 100 points + 10 points for placement.
* **Multiple Line Clear**: ($100 \times \text{number of cleared lines}$) + 10 points for placement.
* **Tetris (4 lines)**: 600 points + 10 points for placement.

---

## ⚠️ Important Implementation Details
* **Default Speed**: Without interaction, tetrominoes fall at a rate of 1 square per second.
* **Game Over**: The game ends if a placed tetromino goes over the top or if a new piece overlaps an existing block upon generation.
* **High Score**: If the final score exceeds the current high score, it is saved for the next session.

