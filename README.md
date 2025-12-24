# 🏓 The Classic Pong Game

A Python-based recreation of the legendary 1972 arcade game.
This project demonstrates the core fundamentals of game development, including **Game Loop logic**, **Collision Detection**, and **Object-Oriented Programming (OOP)**.

It features a 2-player local multiplayer mode with real-time score tracking and dynamic ball physics.

---

## ⚡ Key Features

### 🎮 Smooth Gameplay Mechanics
* **60 FPS Rendering:** Utilizes manual screen updates (tracer method) to ensure smooth paddle movement and ball animation without screen flickering.
* **Responsive Controls:** Implements event listeners for instantaneous keyboard input (W/S for Left Player, Up/Down for Right Player).

### 📐 Physics & Collision Logic
* **Wall Bouncing:** Calculates the angle of reflection when the ball hits the top or bottom boundaries.
* **Paddle Interaction:** detects collision between the ball object and the paddle object using coordinate distance checks (`distance < 50` and `x-coordinate` threshold).
* **Speed Dynamics:** (Optional - if you implemented this) The ball speed increases slightly with every paddle hit to increase difficulty.

### 🏆 Scorekeeping System
* **Live Scoreboard:** A dedicated class handles the UI rendering of the score, updating dynamically whenever a player misses the ball.

---

## 🛠️ Tech Stack & Concepts

| Component | Technology | Concept Demonstrated |
|-----------|------------|----------------------|
| **Language** | **Python 3.x** | Logic, Classes, Inheritance |
| **Graphics** | **Turtle / GUI** | Screen coordinate systems (X, Y axes) |
| **Architecture** | **OOP** | Separate classes for `Ball`, `Paddle`, and `Scoreboard` |
| **Math** | **Vector Geometry** | Calculating reflection angles (`heading * -1`) |

---

## 🔬 How It Works (The Logic)

### 1. The Game Loop
Unlike standard linear programs, this game runs inside a `while game_is_on` loop.
In every iteration, the screen refreshes, and the ball moves a specific number of pixels based on its current vector (X and Y direction).

### 2. Collision Detection
The most complex part of the code involves calculating interactions:
```python
# Pseudo-code logic for collision
if ball.distance(right_paddle) < 50 and ball.xcor() > 320:
    ball.bounce_x() # Reverses the X trajectory
