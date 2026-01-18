# Snake Game using Reinforcement Learning

A Reinforcement Learning (RL) agent that learns to play the classic Snake game using Deep Q-Learning (DQN). The agent is built using **PyTorch** and the game environment is built using **Pygame**.

## 🎮 Demo

The AI agent starts with no knowledge of the game. Through trial and error, it learns to:
1.  Avoid walls and its own tail.
2.  Locate food.
3.  Navigate efficiently to eat food and grow.

## 🧠 How it Works

This project uses **Deep Q-Learning**, a reinforcement learning technique where a neural network approximates the Q-value function (expected future rewards) for each action given a state.

### 1. The Agent (AI)
The agent observes the environment (State) and chooses an action based on its current policy.
-   **Exploration vs. Exploitation**: Initially, the agent acts randomly to explore the environment. As training progresses, it relies more on the Neural Network's predictions (Exploitation) to maximize its score.
-   **Memory**: The agent stores its experiences (State, Action, Reward, Next State, Done) in a replay memory (`deque`) and trains on random mini-batches to break correlation between consecutive steps.

### 2. State Vector (Input)
The `agent.py` calculates a state vector with **11 boolean values** for each frame:
1.  **Danger Straight**: Is there a collision risk immediately ahead?
2.  **Danger Right**: Is there a collision risk to the right?
3.  **Danger Left**: Is there a collision risk to the left?
4.  **Direction Left**: Is the snake moving left?
5.  **Direction Right**: Is the snake moving right?
6.  **Direction Up**: Is the snake moving up?
7.  **Direction Down**: Is the snake moving down?
8.  **Food Left**: Is the food to the left of the head?
9.  **Food Right**: Is the food to the right of the head?
10. **Food Up**: Is the food above the head?
11. **Food Down**: Is the food below the head?

### 3. Action Space (Output)
The neural network outputs 3 values, representing the probability (Q-value) of taking each action:
-   `[1, 0, 0]` -> **Straight** (Keep same direction)
-   `[0, 1, 0]` -> **Right Turn**
-   `[0, 0, 1]` -> **Left Turn**

### 4. Reward System
The environment (`game.py`) gives feedback to the agent:
-   **+10**: Snake eats food.
-   **-10**: Snake dies (hits wall or self).
-   **0**: Snake survives but doesn't eat.

### 5. Neural Network Architecture (`model.py`)
A simple feed-forward neural network:
-   **Input Layer**: 11 nodes (State size)
-   **Hidden Layer**: 256 nodes (ReLU activation)
-   **Output Layer**: 3 nodes (Action size)
-   **Loss Function**: Mean Squared Error (MSE)
-   **Optimizer**: Adam

The goal is to minimize the difference between the predicted Q-value and the target Q-value (Bellman Equation):
`Q_new = Reward + Gamma * max(Q(next_state))`

## 📂 Project Structure

-   **`agent.py`**: The main entry point. Initializes the game and agent, runs the training loop, and manages memory.
-   **`game.py`**: The Pygame implementation of the Snake game. Handles graphics, user input (if manual), and game logic (collisions, food placement).
-   **`model.py`**: Defines the `Linear_QNet` (Neural Network) and `QTrainer` class for backpropagation.
-   **`helper.py`**: Utility for plotting the scores and mean scores in real-time.
-   **`requirements.txt`**: List of Python dependencies.

## 🛠 Installation

1.  **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd Snake-Game-using-Reinforcement-learning
    ```

2.  **Install dependencies**:
    Make sure you have Python installed. Then run:
    ```bash
    pip install -r requirements.txt
    ```

## 🚀 Usage

To start training the agent, simply run:

```bash
python agent.py
```

-   A Pygame window will open showing the training process.
-   A graph will be plotted in real-time showing the **Score** (per game) and **Mean Score** (average).
-   The best model is automatically saved to a `./model` folder as `model.pth`.

## 📈 Performance

-   The agent usually starts scoring consistently after ~80-100 games.
-   The "Randomness" (epsilon) reduces as the number of games increases.

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.
