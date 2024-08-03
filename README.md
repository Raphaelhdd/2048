# 2048 Game AI Project

This project involves designing AI agents to play the popular 2048 game using various search algorithms and evaluation functions.

## Key Files

- **multi_agents.py**: Contains all multi-agent search agents.
- **2048.py**: Main file to run the 2048 game.
- **game_state.py**: Describes the 2048 GameState type.
- **game.py**: Contains the game logic and supporting types like Agent, OpponentAction, and Action.
- **util.py**: Contains useful data structures for implementing search algorithms.

## Agents Overview

### ReflexAgent

- **Improved Evaluation Function**: Enhances the agent's performance.
- **Scores**: Ranges from 1316 to 6060.
- **Highest Tiles**: Up to 512.
- **Consistency**: Varies with an average game duration indicating quick decision-making but a win rate of 0.0.

### MinimaxAgent

- **Adversarial Search**: Implements minimax search with a depth of up to 3.
- **State Evaluation**: Evaluates states rather than actions, suitable for look-ahead strategies.

### AlphaBetaAgent

- **Alpha-Beta Pruning**: Optimized version of MinimaxAgent for more efficient search.
- **Performance**: Achieves similar minimax values with improved performance due to pruning.

### ExpectimaxAgent

- **Expectimax Search**: Models probabilistic outcomes.
- **Performance**: Achieves higher scores compared to Minimax and AlphaBeta agents by considering expected values rather than worst-case scenarios.

## Evaluation Function

The custom evaluation function uses a linear combination of heuristic features:

1. **Max Tile in Corners**: Encourages placing the highest tile in a corner.
2. **Monotonicity**: Ensures rows and columns follow a monotonic pattern for easier merges.
3. **Smoothness**: Measures differences between adjacent tiles to maintain a manageable board.
4. **Empty Tiles**: Counts empty tiles to prioritize move opportunities.
5. **Legal Actions**: Considers the number of possible moves to maintain gameplay flexibility.
6. **Score**: Aligns with the primary objective of maximizing the score.
7. **Max Tile**: Rewards achieving high tiles directly.

## Running the Agents

To run the provided ReflexAgent:
```bash
python3 2048.py --agent=ReflexAgent
```
To run the MinimaxAgent:
```bash
python3 2048.py --agent=MinmaxAgent --depth=2
```
To run the AlphaBetaAgent:
```bash
python3 2048.py --agent=AlphaBetaAgent --depth=2
```
To run the ExpectimaxAgent:
```bash
python3 2048.py --agent=ExpectimaxAgent --depth=2
```

##Results and Performance
The agents and evaluation function have been tested extensively, with results showing significant performance improvements in specific scenarios. The ExpectimaxAgent, in particular, demonstrates higher and more consistent scores due to its probabilistic approach.
