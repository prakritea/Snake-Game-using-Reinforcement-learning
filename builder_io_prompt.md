# Prompt for Builder.io / V0 / Bolt

**Goal**: Create a stunning, high-performance landing page for a "Snake Game AI" project that uses Deep Q-Learning (Reinforcement Learning).

## 🎨 Aesthetic & Vibe
*   **Theme**: Cyberpunk / High-Tech / Dark Mode.
*   **Colors**: Deep Abyss Black (`#0a0a0a`) background, Neon Green (`#00ff00`) accents for the "AI/Snake" elements, and Electric Blue (`#00ccff`) for data/graphs.
*   **Typography**: Monospace fonts (e.g., 'JetBrains Mono', 'Fira Code') for code snippets and headers. Clean Sans-serif (e.g., 'Inter', 'Roboto') for body text.
*   **Effects**: Subtle glowing borders, glassmorphism on game containers, matrix-style rain or grid background animations.

## 🧱 Structure & Content

### 1. Hero Section
*   **Headline**: "Snake AI: Evolving Intelligence"
*   **Subheadline**: "Watch a Deep Q-Learning agent master the classic Snake game from scratch using PyTorch and Reinforcement Learning."
*   **CTA Button**: "View Source Code" (Button with Github Icon)
*   **Visual**: A placeholder container for a Video/GIF of the snake playing perfectly at high speed.

### 2. "The Brain" (How it Works)
Create a visually engaging section explaining the Deep Q-Network (DQN) process.
*   **Input Layer (State)**: Visualize 11 Input Neurons (e.g., "Danger Left", "Food Right", "Direction Up").
*   **Hidden Layer**: A representation of the Neural Network processing.
*   **Output Layer (Action)**: 3 Output Neurons ("Straight", "Right", "Left").
*   **Description**: "The agent sees the world through 11 boolean values, processes them through a Neural Network, and decides the optimal move to maximize its reward."

### 3. Key Features (Cards)
*   **Reinforcement Learning**: "Uses the Bellman Equation to optimize long-term rewards."
*   **Experience Replay**: "Learns from past mistakes by training on a memory buffer of 100,000 steps."
*   **Epsilon-Greedy Strategy**: "Balances exploration (random moves) and exploitation (learned knowledge)."

### 4. Interactive Stats (Mockup)
Display a "Live Training Dashboard" mockup.
*   **Game Count**: "Game #1254"
*   **Current Score**: "54"
*   **High Score**: "89"
*   **Mean Score**: "45.2"
*   *Note*: Use animated counters that tick up.

### 5. Tech Stack
Use minimal, monochrome icons that glow on hover:
*   Python
*   PyTorch
*   Pygame
*   NumPy

### 6. Installation (Code Block)
A sleek, copy-pasteable terminal window showing:
```bash
git clone https://github.com/yourusername/snake-rl
cd snake-rl
pip install -r requirements.txt
python agent.py
```

### 7. Footer
*   "Created with ❤️ and ☕️ by [Your Name]"
*   Links to GitHub, LinkedIn, Twitter.

## ⚡️ Technical Requirements
*   Fully Responsive (Mobile friendly).
*   Fast loading animations.
*   Use standard HTML5/CSS3 or React/Tailwind.
