# A-Reinforcement-Approach-for-Fleet-Optimization-and-Safety-in-Multi-Agent-Autonomous-Cars

## Table of Contents

- [Overview](#overview)
- [Introduction](#introduction)
- [Reinforcement Learning](#reinforcement-learning)
- [Features](#features)
- [Read More](#read-more)
- [Requirements](#requirements)
- [Working](#working)
- [License](#license)

## Overview

This project simulates a taxi fleet operating in a dynamic environment using reinforcement learning. The taxis navigate through a predefined graph, picking up and dropping off passengers based on generated requests. The simulation visualizes the taxis' movements and updates their Q-learning-based decision-making processes.

## Introduction

Reinforcement learning is a powerful technique for training agents to make decisions in complex environments. This project focuses on using Q-learning for a fleet of autonomous taxis that must learn to navigate efficiently, respond to passenger requests, and optimize their routes in real time.

## Reinforcement Learning 
The project utilizes Q-learning, a popular model-free reinforcement learning algorithm, to train the taxi agents. Below are the key aspects of the RL implementation:

### State Space

The state space for each taxi (agent) is defined as:
\[ S = (text{current location}, \text{passenger status}) \]
- **Current Location**: The node (location) where the taxi is currently positioned in the graph.
- **Passenger Status**: A binary indicator showing whether the taxi is currently carrying a passenger.

### Action Space

The action space defines the actions that a taxi can take in each state. In this simulation, the action space is defined as:
\[ A = \text{each taxi moving to its neighboring nodes (locations) on the graph} \]

### Rewards

Rewards are used to reinforce positive or negative behavior of the taxi agent during its interactions with the environment. In this simulation:
- **Movement Reward**: Each step taken by the taxi incurs a small negative reward (typically -1).
- **Pickup Reward**: The taxi receives a positive reward (typically +10) when it successfully picks up a passenger.
- **Drop-off Reward**: The taxi receives a positive reward (typically +20) when it successfully drops off a passenger.

### Our Approach: Q-Learning

- **Model-free, Off-policy Learning**: The taxis learn like curious explorers, constantly updating their knowledge.
- **Q-value Update**: The Q-value for a state-action pair is updated using the Bellman equation:
  \[
  Q(s, a) \leftarrow Q(s, a) + \alpha \cdot \left[ r + \gamma \cdot \max_{a'} Q(s', a') - Q(s, a) \right]
  \]
  
- **Q-Table**: Each taxi agent maintains a Q-table where it stores Q-values for each state-action pair it encounters during the simulation.

- **Learning Rate (α)**: Controls how much the agent updates its Q-values in response to new information. Set at **0.1**.

- **Discount Factor (γ)**: Determines the importance of future rewards. A lower discount factor makes the agent focus more on immediate rewards, while a higher discount factor values future rewards more. Set at **0.9**.

### Environment

The environment simulates a graph structure representing locations and connections between them. Each taxi navigates through this environment based on the defined state, action, and reward framework.

![Environment Visualization](![image](![image](https://github.com/user-attachments/assets/c55948ed-4b3e-4326-a5dc-79ee20c45ca7)
)
)  <!-- Replace with the path to your environment image -->
## Working
### TaxiRLAgent Class
- **Attributes**:
  - `taxi_id`: Unique identifier for each taxi agent.
  - `current_location`: Tracks the taxi's current position on the graph.
  - `passenger`: Indicates if the taxi is currently carrying a passenger.
  - `destination`: The drop-off location for the current passenger.
  - `q_table`: A table storing Q-values for state-action pairs, which helps the agent determine the best action to take in a given state.

- **Methods**:
  - `get_state()`: Returns the current state of the taxi, which includes its location and passenger status.
  - `choose_action(state)`: Uses an exploration-exploitation strategy to decide the next action:
    - **Exploration**: The agent occasionally tries random actions to discover new strategies.
    - **Exploitation**: The agent primarily chooses the action that it believes will yield the highest reward based on its Q-table.
  - `update_q_table(state, action, reward, next_state)`: Updates the Q-table based on the reward received and the next state observed, using the Q-learning update rule.

### Q-learning Update Rule
The Q-learning algorithm updates the Q-values based on the Bellman equation:

\[
Q(s, a) \gets Q(s, a) + \alpha \left( r + \gamma \max_a Q(s', a) - Q(s, a) \right)
\]

Where:
- \( Q(s, a) \) is the current Q-value for state \( s \) and action \( a \).
- \( \alpha \) is the learning rate, controlling how much new information overrides old information.
- \( r \) is the reward received after taking action \( a \).
- \( \gamma \) is the discount factor, determining the importance of future rewards.
- \( \max_a Q(s', a) \) is the maximum predicted Q-value for the next state \( s' \).

## Features

- **Reinforcement Learning Agent**: Taxis learn to optimize their routes using Q-learning.
- **Dynamic Requests**: Passengers generate requests periodically, adding complexity to the simulation.
- **Graph-Based Navigation**: Taxis operate in a graph environment with nodes and edges representing locations and distances.
- **Visualization**: The simulation includes a visual representation of the graph, taxis, requests, and their movements.
- **Video Compilation**: Frames from the simulation are compiled into a video for easier analysis.

## Observation and Simulation


## Read More

You can read more about this project in the published paper: ([Click here to view the paper.](https://ieeexplore.ieee.org/document/10718531)).

## Requirements

- Python 3.6 or higher
- Libraries:
  - OpenCV
  - NumPy
  - Matplotlib
  - NetworkX
  - Tabulate

You can install the required libraries using pip:

```bash
pip install opencv-python numpy matplotlib networkx tabulate
