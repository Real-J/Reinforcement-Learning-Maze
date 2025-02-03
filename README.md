# Reinforcement Learning Maze 🏆🚀

This project implements a **Reinforcement Learning (RL) agent** that learns to navigate a maze using **Q-learning**. The agent interacts with a **Tkinter-based grid environment**, avoiding obstacles and reaching the goal while improving its performance over multiple training episodes.

---

## 🎯 **Project Overview**
- **Environment:** A 4x4 grid-based maze.
- **Agent:** Moves in four directions (`up`, `down`, `left`, `right`).
- **Obstacles (`hells`)**: Black squares that penalize the agent with a **-1 reward**.
- **Goal (`paradise`)**: A yellow circle that rewards the agent with a **+1 reward**.
- **Ground (`neutral states`)**: All other cells provide **0 reward**.
- **Q-Learning:** The agent learns an optimal policy through trial and error using an evolving Q-table.

---

## 📂 **Project Structure**
```
📦 RL-Maze
 ┣ 📜 maze_env.py     # Maze environment (Tkinter visualization & environment logic)
 ┣ 📜 RL_brain.py     # Q-learning agent (learning algorithm & Q-table management)
 ┣ 📜 main.py         # Training loop and agent-environment interaction
 ┣ 📜 README.md       # Project documentation
```

---

## 🚀 **How to Run**
### **1️⃣ Install Dependencies**
Ensure you have **Python 3** installed. Install required dependencies using:
```bash
pip install numpy pandas tk
```

### **2️⃣ Run the Program**
To start training the agent and visualize the maze environment, run:
```bash
python main.py
```
This will launch the **maze environment**, where the agent will attempt to learn the optimal path through reinforcement learning.

---

## 🔬 **How It Works**
### **1️⃣ Training Process**
- The agent starts at the **red square**.
- It explores the maze using the **ε-greedy policy**:
  - **Exploits** the best-known action (90% of the time).
  - **Explores** new actions (10% of the time).
- The agent updates the **Q-table** using the Q-learning formula to improve future decision-making.
- After multiple episodes, it learns the **optimal path** to reach the goal efficiently.

### **2️⃣ Q-Learning Explanation**
Q-learning is a model-free reinforcement learning algorithm used to find the best action to take in a given state. It follows the **Bellman equation**:
```
Q(s, a) ← Q(s, a) + α [r + γ max Q(s', a') - Q(s, a)]
```
Where:
- **`Q(s, a)`** → The expected utility of taking action `a` in state `s`.
- **`α` (learning rate)** → Controls how much new information overrides old knowledge.
- **`r` (reward)** → Immediate reward received after taking action `a`.
- **`γ` (discount factor)** → Balances the importance of future rewards (0 ≤ γ ≤ 1).
- **`max Q(s', a')`** → The highest expected reward from the next state `s'`.

#### **How Learning Works**
1. The agent starts with a **Q-table** initialized to zero.
2. It selects an action using an **ε-greedy policy** (choosing between exploitation and exploration).
3. The agent performs the action, observes the **reward** and next state.
4. The **Q-table** is updated using the formula above.
5. Over time, the agent learns the **optimal policy**—the sequence of actions that maximize the expected cumulative reward.
6. The **policy improves** as more training episodes refine the action-value estimates.

#### **Advantages of Q-Learning**
- **Model-Free:** The agent does not need prior knowledge of the environment.
- **Guaranteed Convergence:** Given sufficient exploration, Q-learning converges to the optimal policy.
- **Handles Stochastic Environments:** Can adapt to changes in rewards and state transitions.
- **Off-Policy Learning:** Learns the optimal policy regardless of the agent's action selection strategy.

#### **Challenges of Q-Learning**
- **Exploration-Exploitation Dilemma:** Balancing between exploring new actions and exploiting known good actions.
- **Slow Convergence:** Can require many episodes for complex environments.
- **Curse of Dimensionality:** Large state-action spaces can make learning impractical without optimizations.

#### **Enhancements to Q-Learning**
- **Decay ε Over Time:** Gradually shift from exploration to exploitation.
- **Experience Replay:** Store past experiences and reuse them to stabilize learning.
- **Function Approximation:** Use **Neural Networks (Deep Q-Networks, DQNs)** to generalize learning.
- **Double Q-Learning:** Reduce overestimation of action values to improve stability.

---

## 🔥 **Features**
✅ **Q-learning with exploration & exploitation**  
✅ **Graphical visualization using Tkinter**  
✅ **Dynamic interaction with the environment**  
✅ **Customizable training episodes**  
✅ **Adjustable learning parameters**  
✅ **Step-by-step Q-table updates**
✅ **Discussion of Q-learning advantages & challenges**

---

## 🛠️ **Possible Enhancements**
- **Larger & More Complex Mazes** 🏗️
- **Adaptive Exploration Rate (`ε` Decay)** 📉
- **Save & Load Q-Table for Continued Training** 💾
- **Deep Q-Networks (DQN) for More Complex Environments** 🧠
- **Obstacle & Maze Customization** 🛠️
- **Multiple agents with collaborative learning** 👥

---

## 📜 **License**
This project is open-source and free to use under the MIT License.

