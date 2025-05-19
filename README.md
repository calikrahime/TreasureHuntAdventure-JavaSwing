## 🎮 Project Overview

This project is a two-level graphical adventure and strategy game developed in Java using the **Swing GUI library**. The player navigates a 30-cell game board by rolling a dice. Each cell has a distinct feature:

- 💰 **Treasure cells** increase score (+10)
- ☠️ **Trap cells** decrease score (-5)
- ➖ **Empty cells** do not affect score
- 🔁 **Forward / Backward cells** dynamically reposition the player

The primary objective is to reach the **Finish** cell with the highest score. Upon completing Level 1, the player can progress to Level 2, which includes enhanced dynamics such as bidirectional jumps and advanced cell logic.

---

## 🧠 Data Structures Used

### 1. Linked List

The game board is modeled using **linked list** structures where each cell is represented by a node:

- **Level 1**: Uses a **Singly Linked List** for linear progression from Start to Finish.
- **Level 2**: Uses a **Doubly Linked List** enabling forward and backward jumps. Some nodes contain jump references for ±3 cell movements.

### 2. Binary Search Tree (BST)

Player scores are stored and managed using a **Binary Search Tree**:

- Each node includes the player's username, score, and game level.
- Nodes are inserted according to score value, enabling **in-order traversal** for ascending order display.
- `findMin()` and `findMax()` methods retrieve the lowest and highest scores.

---

## 🖥️ System Design

### 3.1 User Interface (GUI)

- A 5x6 grid (30 cells total) visualizes the game board.
- Each cell displays an icon: Treasure, Trap, Empty, Start, or Finish.
- A dice roll button, score panel, and player info are located at the bottom.
- The GUI is built entirely using Java **Swing components**.

### 3.2 Game Flow

- When the player rolls the dice, a number between 1–6 is generated.
- The player moves forward that number of cells.
- The type of the landed cell affects the score and position.
- Forward/Backward cells cause additional jumps.
- A pop-up dialog displays the move details and score change.
- Reaching the Finish cell ends the level and saves the score.

### 3.3 Score System

- Player scores are saved to a `score.txt` file in the format:  
  `username, level, score`
- The file is read into a BST for efficient score tracking.

### 3.4 Scoreboard Feature

- Scores are read from the `score.txt` file and parsed.
- Displayed using **in-order traversal** (ascending order).
- Maximum and minimum scores are shown by accessing BST leaf nodes.

---

## 🧪 Sample UI Features

- 🎲 Dice roll button with sound effect
- 🧩 Icon-based buttons representing cells (Treasure, Trap, etc.)
- 🧾 Info panel with player name and score
- 📌 Dialog box showing jump and score details after each move

---

## 🛠️ Challenges & Solutions

| Issue | Solution |
|-------|----------|
| Null pointer errors in linked list navigation | Carefully linked all `next`, `prev`, and `jump` references |
| File writing issues during score saving | Used `BufferedWriter` in append mode with error handling |
| Visual glitches on player movement | Updated all cell icons on each step to ensure accuracy |
| Infinite jumps due to loops | Limited jumps to max 3 per move to avoid endless loops |

---

## ✅ Learning Outcomes

Through this project, we gained practical understanding of essential data structures:

- **Singly Linked List** for linear cell navigation in Level 1  
- **Doubly Linked List** for bidirectional and jump-based movement in Level 2  
- **Binary Search Tree (BST)** for organizing and retrieving scores efficiently

This project allowed us to solidify theoretical knowledge with practical GUI-based application, reinforcing the real-world utility of data structures in game design.
