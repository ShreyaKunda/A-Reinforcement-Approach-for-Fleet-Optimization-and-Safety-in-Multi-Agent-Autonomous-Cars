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

- **Agent**: The taxi acts as the agent that interacts with the environment.
- **Environment**: The graph structure where the taxis operate, consisting of nodes (locations) and edges (distances between locations).
- **State**: A representation of the agent's current situation, including its location, whether it has a passenger, and the passenger's destination.
- **Action**: The choices available to the agent, such as moving to a neighboring node, picking up a passenger, or dropping off a passenger.
- **Reward**: Feedback from the environment that quantifies the effectiveness of the agent's action. Positive rewards are given for successful pickups and drop-offs, while negative rewards may be assigned for poor actions, such as moving to an undesirable location.

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
