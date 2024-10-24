# A-Reinforcement-Approach-for-Fleet-Optimization-and-Safety-in-Multi-Agent-Autonomous-Cars

## Table of Contents

- [Overview](#overview)
- [Introduction](#introduction)
- [Features](#features)
- [Read More](#read-more)
- [Requirements](#requirements)
- [How to Use and Run the Code](#how-to-use-and-run-the-code)
- [License](#license)

## Overview

This project simulates a taxi fleet operating in a dynamic environment using reinforcement learning. The taxis navigate through a predefined graph, picking up and dropping off passengers based on generated requests. The simulation visualizes the taxis' movements and updates their Q-learning-based decision-making processes.

## Introduction

Reinforcement learning is a powerful technique for training agents to make decisions in complex environments. This project focuses on using Q-learning for a fleet of autonomous taxis that must learn to navigate efficiently, respond to passenger requests, and optimize their routes in real time.

## Features

- **Reinforcement Learning Agent**: Taxis learn to optimize their routes using Q-learning.
- **Dynamic Requests**: Passengers generate requests periodically, adding complexity to the simulation.
- **Graph-Based Navigation**: Taxis operate in a graph environment with nodes and edges representing locations and distances.
- **Visualization**: The simulation includes a visual representation of the graph, taxis, requests, and their movements.
- **Video Compilation**: Frames from the simulation are compiled into a video for easier analysis.

## Read More

You can read more about this project in the published paper: [Transcribing Natural Language To Python Code: A Compiler Based Approach](link-to-your-paper).

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
