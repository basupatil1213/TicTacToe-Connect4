# TicTacToe and ConnectFour Games

## Overview
This project contains implementations of the TicTacToe and ConnectFour games, along with the Monte Carlo Tree Search (MCTS) algorithm for game playing. The games are designed for playing against an MCTS-based player and a random player.

## Classes
### TicTacToe
- **Position:** Represents the TicTacToe board and provides methods for game state manipulation and analysis.
- **TicTacToe:** Defines the game logic, including starting positions, moves, and state transitions.
- **TicTacToeNode:** Implements the MCTS algorithm specifically for TicTacToe, including node management and backpropagation.

### ConnectFour
- **ConnectFourPosition:** Represents the Connect Four board and handles game state operations.
- **ConnectFour:** Implements the Connect Four game rules and logic.
- **ConnectFourNode:** Manages the MCTS algorithm specifically for Connect Four gameplay.

## Monte Carlo Tree Search (MCTS)
MCTS is a heuristic search algorithm used in decision processes, particularly in games. It works by simulating multiple random games (playouts) from the current game state to determine the best move. The algorithm consists of four main steps:
1. **Selection:** Traverse the tree from the root node based on certain criteria (e.g., UCB1 algorithm) to select a promising child node.
2. **Expansion:** If the selected node has unexplored moves, expand the tree by adding child nodes for those moves.
3. **Simulation:** Perform a simulation (playout) from the selected node until a terminal state is reached.
4. **Backpropagation:** Update the statistics of all nodes visited during the simulation, such as wins and total playouts.

## Installation
To run the project:

1. Clone the repository and build it with Maven (JDK 18+ and Maven required; see `pom.xml`):

   ```bash
   git clone https://github.com/basupatil1213/TicTacToe-Connect4.git
   cd TicTacToe-Connect4
   mvn compile
   ```

2. Run a game (MCTS player vs. random player):

   ```bash
   # Tic-Tac-Toe
   mvn exec:java -Dexec.mainClass=edu.neu.coe.info6205.mcts.tictactoe.TicTacToe
   # Connect Four
   mvn exec:java -Dexec.mainClass=edu.neu.coe.info6205.mcts.ConnectFour.ConnectFour
   ```

   Or run the `main` method of either class directly from your IDE.

In our implementation, the MCTS algorithm is used to make intelligent moves in TicTacToe and ConnectFour games, competing against a random player.

## Test Cases
Comprehensive test cases have been implemented for both TicTacToe and ConnectFour classes to ensure their correctness and functionality. The test cases cover various game scenarios, moves, and edge cases to validate the game logic and algorithms.

Run the tests with:

```bash
mvn test
```

Test classes live under `src/test/java/edu/neu/coe/info6205/mcts/` (`tictactoe/`, `connectfour/`, `core/`).

## Report
The full project report is in [`Report_Final_Project_PSA.pdf`](Report_Final_Project_PSA.pdf).
