# 🐍 Snake Game (Python Turtle)

A classic **Snake Game** implementation using Python’s built-in **turtle graphics** library. The game features smooth movement mechanics, collision detection, and **persistent high-score tracking**.

---

## 🎮 How to Play

The objective is simple: **eat the blue food** to grow your snake and increase your score.  
Avoid hitting the walls or your own tail!

### Controls

- **Up Arrow** → Move up  
- **Down Arrow** → Move down  
- **Left Arrow** → Move left  
- **Right Arrow** → Move right  

---

## 🛠️ Features

- **Snake Mechanics**  
  The snake grows longer each time it consumes food.

- **High Score Persistence**  
  High scores are saved to a `data.txt` file, so your record remains even after closing the game.

- **Collision Detection**
  - **Wall Collision:** Resets the game if the snake hits the boundary.  
  - **Tail Collision:** Resets the game if the snake’s head touches any body segment.

- **Dynamic UI**  
  Real-time score updates displayed at the top of the screen.

---

## 📁 File Structure

| File | Description |
|---|---|
| `main.py` | Entry point of the game; handles the main loop and screen updates |
| `snake.py` | Contains the `Snake` class for movement, growth, and resetting |
| `food.py` | Manages the `Food` class and random spawning |
| `scoreboard.py` | Handles score tracking, high-score file I/O, and UI text |
| `data.txt` | Stores the all-time high score |

---

## 🚀 Getting Started

### Prerequisites

- Python **3.x** installed on your system  
- The **turtle** module (included in the Python Standard Library)

### Installation & Execution

1. Clone or download the repository containing the five files listed above.
2. Ensure a file named `data.txt` exists in the same directory with an initial value of `0`.
3. Run the game:

```bash
python main.py
```

---

## 💡 Code Highlights

The snake’s movement is implemented by shifting each segment to the position of the segment in front of it, creating a “follow-the-leader” effect:
```python
# snippet from snake.py
for seg_num in range(len(self.segments) - 1, 0, -1):
    new_x = self.segments[seg_num - 1].xcor()
    new_y = self.segments[seg_num - 1].ycor()
    self.segments[seg_num].goto(new_x, new_y)
self.head.forward(MOVE_DISTANCE)
```

