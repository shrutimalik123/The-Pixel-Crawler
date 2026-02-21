# 🗡️ The Pixel Crawler - Procedural Roguelike Sim

A turn-based dungeon delver where survival depends on resource optimization. Every room is procedurally generated, offering a mix of combat, loot, traps, and brief moments of rest. As a player, you must decide when to spend your limited Stamina to fight and when to sacrifice Health to survive another day.

This project focuses on teaching:
* **Procedural Event Logic:** Using `random.choice` to create unique gameplay sessions.
* **Resource Capping:** Implementing `min()` functions to ensure stats stay within realistic bounds.
* **State Machine Loops:** Managing a continuous game loop that shifts based on player health and choice.
* **Inventory Interaction:** Automatically processing items to influence player stats in real-time.

---

## ✨ Features

* **Infinite Dungeon:** No two runs are the same; the map generates as you move.
* **Risk vs. Reward Combat:** Choose to fight (Safe but costs Stamina) or run (Damaging but saves energy).
* **Resource Management:** Balance HP and Stamina to ensure you aren't defenseless during monster encounters.
* **Auto-Loot System:** Finds and applies potions and snacks to help you dive deeper into the dungeon.

---

## 🚀 How to Run the Game

### 1. Prerequisites
You need **Python 3** installed.

### 2. Setup and Execution
1.  **Save the Code:** Save the script as `pixel_crawler.py`.
2.  **Open Terminal:** Navigate to your project folder.
3.  **Run the Script:**
    ```bash
    python pixel_crawler.py
    ```

### 3. Gameplay Instructions
1.  **Monitor Your Stats:** Keep an eye on your HP (Life) and Stamina (Energy).
2.  **Make Choices:** When you hit a monster, check your stamina. If it's below 20, fighting will be extra dangerous!
3.  **Loot:** Grab potions to restore HP and snacks to restore Stamina.
4.  **The Goal:** See how many rooms you can clear before your HP hits zero.



---

## 🧠 Code Structure Highlights

### Capping Values
To prevent a player from having "120% Health" after drinking a potion, we use the `min()` function. It compares the new value to our maximum (100) and picks the smaller of the two.

```python
# If hp + 20 is 110, it picks 100.
hp = min(100, hp + 20)

