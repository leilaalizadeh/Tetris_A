<<<<<<< HEAD
# Computer Architectures — Tetris (LandTiger / LPC1768)

## 📌 Project Overview
This repository contains my simplified **Tetris** implementation for the **LandTiger (LPC1768)** platform, developed for the course *Architetture dei Sistemi di Elaborazione (Computer Architectures)*.

The project is intended to run in **Keil µVision** using the LandTiger emulator.

- **Target platform:** LandTiger Board / LPC1768 (Emulator)
- **Keil target:** `SW_Debug` (software debug / emulation)

---

## 🎮 What the Game Does
This is a classic Tetris-style game:

- A random tetromino spawns at the top of the grid
- You can move and rotate it while it falls
- When it can’t move down anymore, it **locks** into the grid
- Full rows are cleared, blocks above shift down, and the score increases
- The game ends when a new piece can’t be spawned safely

---

## 🧩 Playing Field & UI
- **Grid size:** **20 rows × 10 columns**
- **Screen layout:**
  - **Left:** playing field (the grid)
  - **Right:** **Score**, **High Score**, **Cleared Lines**
- **Tetrominoes implemented:** all 7 standard shapes: **I, O, T, J, L, S, Z**

---

## ⏱️ Timing & Movement Rules
- **Normal fall speed:** **1 block per second**
- **Soft drop:** **2 blocks per second** while holding joystick **Down**
- **Hard drop:** instantly drops the piece to the lowest valid position and locks it

---

## 🕹️ Controls

| Input | Action |
|---|---|
| **KEY1** | Start (after reset) / Pause / Resume |
| **KEY2** | **Hard Drop** (instant fall + lock) |
| **Joystick Up** | Rotate **90° clockwise** |
| **Joystick Left / Right** | Move horizontally |
| **Joystick Down (hold)** | **Soft Drop** (faster falling) |
=======
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
| **KEY2** | **Hard Drop**: Current tetromino falls instantly. |
| **Joystick Up** | Rotates the tetromino $90^{\circ}$ clockwise. |
| **Joystick Left/Right** | Moves the tetromino horizontally. |
| **Joystick Down** | **Soft Drop**: Increases fall speed to 2 squares/second while held. |
>>>>>>> ec997470f87f0f44258d80a97c978ab3d6794e77

---

## 📈 Scoring System
<<<<<<< HEAD
Scoring is designed to reward clearing multiple lines at once.

- **Piece locks (placement):** `+10`
- **Clear N lines at once:** `+100 × N`  
- **Clear 4 lines at once (Tetris):** `+600`

> Placement points (`+10`) are still added when the piece locks, even if lines are cleared.

---

## ✅ Line Clearing Logic
A line is cleared when **all 10 columns** of a row are filled.

After clearing:
- the full row is removed
- all rows above shift downward (no gaps remain)

Clearing **4 lines simultaneously** counts as a **Tetris**.

---

## 🛑 Game Over Conditions
The game ends if:
- any locked blocks reach above the top of the playing field, **or**
- a newly spawned tetromino overlaps existing blocks (no space to spawn)

After game over:
- **High Score** is updated if the final score is higher
- the game returns to the initial **paused** state
- a new game can be started again using **KEY1**

---

## 🧱 Build & Run (Keil µVision)
1. Open the `.uvprojx` file in **Keil µVision**
2. Select the `SW_Debug` target
3. Build the project (**Rebuild All** recommended)
4. Start a debug session
5. Run, then press **KEY1** to start playing

---

## 👤 Author
Student project by **[Leila Alizadeh]**
=======
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

>>>>>>> ec997470f87f0f44258d80a97c978ab3d6794e77
