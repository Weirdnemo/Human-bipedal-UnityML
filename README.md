# Humanoid Agent: Learning to Walk with Deep Reinforcement Learning

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project explores the fascinating challenge of teaching a humanoid agent to walk and maintain balance from scratch using Deep Reinforcement Learning in a physics-based environment. The agent learns complex, stable walking behaviors through trial-and-error, driven by a carefully designed reward system.

<br>

![Humanoid Agent Gameplay](./walker-showcase/ML-walker(game).gif)

---

## Table of Contents

- [About The Project](#about-the-project)
- [Key Features](#key-features)
- [Built With](#built-with)
- [The Training Process](#the-training-process)
- [Results & Observations](#results--observations)
- [Contact](#contact)

---

## About The Project

Bipedal locomotion is a notoriously difficult problem in robotics and AI. This project tackles it by creating a Unity-based simulation where a humanoid agent, controlled by a neural network, learns to walk without any hard-coded instructions.

The entire learning process is powered by the **Unity ML-Agents** toolkit, using a Python backend for training the model. The goal was to observe if complex, human-like walking patterns could emerge purely from a simple set of rewards and penalties in a simulated physical world.

*Unity Editor "Scene" View:*

![Unity Scene View](./walker-showcase/ML-Walker(scene).gif)

---

## Key Features

- **Real-Time Physics Simulation:** The agent operates within a Unity environment governed by real-time physics, ensuring the learned skills are dynamically robust.
- **Emergent Walking Behavior:** The agent's walking gait is not pre-programmed; it emerges naturally as the optimal strategy to maximize rewards.
- **Advanced Reward Shaping:** The reward function is carefully tuned to encourage forward momentum, maintaining balance, and minimizing effort, leading to a more efficient and stable gait.
- **Proximal Policy Optimization (PPO):** The agent's "brain" is a neural network trained using the state-of-the-art PPO algorithm, known for its stability and performance in continuous control tasks.
- [cite_start]**Multi-Agent Training:** The environment was structured to support multi-agent training, significantly accelerating the learning process through parallel data collection.

---

## Built With

This project was made possible by these incredible open-source tools:

* [Unity](https://unity.com/): The core 3D environment and physics engine.
* [Unity ML-Agents](https://github.com/Unity-Technologies/ml-agents): The framework connecting the Unity environment to the Python training backend.
* [Python](https://www.python.org/): For writing the training pipelines.
* [PyTorch](https://pytorch.org/): Used by ML-Agents for defining and training the neural network models.

---

## The Training Process

The agent learns through a process of trial, error, and reward. At each step, it observes its state and decides on an action to maximize its reward.

1.  **Objective:** The primary goal is to walk forward without falling.
2.  **Reward Function:**
    * **`+` Positive Reward:** Given for moving in the target direction and for keeping the head oriented upwards.
    * **`-` Negative Reward (Penalty):** Given if the agent's body touches the ground.
3.  **Learning Algorithm:** The PPO algorithm updates the agent's neural network based on its experiences. To accelerate this, the environment was set up for multi-agent training, allowing multiple agents to learn in parallel, as shown below.

*Multi-Agent Training in Action:*

![Multi-Agent Training Video](./walker-showcase/ML-walker(multiagent%20video).gif)

---

## Results & Observations

The training process revealed a fascinating progression of learning:

-   **Initial Stages:** The agent's movements were random and chaotic, leading to immediate falls.
-   **Mid-Training:** The agent learned to balance but remained stationary. It discovered that keeping its torso upright was a key component of not falling.
-   **Late-Training:** The agent successfully connected forward movement with high rewards, leading to the emergence of a coordinated, stable walking gait. The final agent, as seen in the main demo, can walk continuously and maintain balance in real-time.

---

## Contact

Nimesh Chauhan - [nimesh.chn@gmail.com](mailto:nimesh.chn@gmail.com)

Project Link: `https://github.com/Weirdnemo/Human-bipedal-UnityML`
