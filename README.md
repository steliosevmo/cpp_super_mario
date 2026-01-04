# c++_super_mario
# Super Mario C++ Side-Scroller (SGG Engine)

A 2D retro-style platformer inspired by the classic Super Mario Bros, developed in **C++** using the **Simple Game Graphics (SGG)** library. This project focuses on Object-Oriented Programming (OOP) principles, real-time physics simulation, and state management.

## 🚀 Features

* **Physics-Based Movement:** Custom implementation of gravity, acceleration, and jumping mechanics.
* **AABB Collision Detection:** Robust collision logic between the player, enemies, and environment using a dedicated `Box` utility.
* **Side-Scrolling Camera:** A dynamic camera system that follows the player by calculating global offsets.
* **Animation System:** Sprite-based animations for characters and enemies that react to movement and state.
* **Game State Management:** A unified system to handle transitions between the **Main Menu**, **Active Gameplay**, and **Game Over** screens.
* **Debug Mode:** Built-in debugging overlay to visualize hitboxes and coordinates in real-time.

---

## 🛠️ Technical Architecture

### Design Patterns
* **Singleton Pattern:** The `GameState` class is implemented as a singleton to ensure a single, global point of access to game data, assets, and the current level state.



### Class Hierarchy
* **Base Object:** All active elements (Menu, Player, Enemy, Level) inherit from a base `GameObject` class, providing a consistent interface for `init()`, `update()`, and `draw()` cycles.
* **Composition:** Characters inherit both from `GameObject` and `Box` to combine game logic with spatial/collision properties.



### Resource Management
* **Asset Centralization:** All assets (bitmaps, fonts, audio) are preloaded and managed through centralized path resolution within the `GameState`.
* **Audio Integration:** Real-time sound effects for actions like jumping, enemy deaths, and player damage.

---

## 💻 Getting Started

### Prerequisites
* **Visual Studio** (Windows is recommended for SGG).
* **SGG Library:** Ensure the library is correctly linked.
    * [SGG Official Documentation](https://cgaueb.github.io/sgg/index.html)

### Installation
1. Clone the repository.
2. Open the solution file in Visual Studio.
3. Ensure the `assets/` directory is present in your output folder.
4. Build and Run.

---

## ⌨️ Controls

| Key | Action |
| :--- | :--- |
| **A / D** | Move Left / Right |
| **W** | Jump |
| **Enter** | Start Game (from Menu) |
| **M** | Return to Menu (from End Screen) |
| **0** | Toggle Debug Mode |
| **ESC** | Exit Game |

---

## ⚙️ Development & Cleanup
This project was developed with a focus on **Clean Code**:
* Redundant loops and unused static/dynamic object containers were removed to optimize the frame cycle.
* Memory management was prioritized by replacing unnecessary heap allocations (`new int`) with stack variables in the update loop.
* Separation of concerns: Drawing logic is strictly isolated from initialization logic.

---

## ⚖️ License
This project was created for academic purposes. Documentation for the underlying engine can be found at the [SGG Documentation](https://cgaueb.github.io/sgg/index.html).
