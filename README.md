# Path-Planning-in-a-2D-environment-using-A*-Algorithm-

# README

## Overview

This project implements a path-planning algorithm using a custom graph-based approach with different motion primitives in a 2D environment containing obstacles. The code allows the user to input start and goal coordinates along with other parameters to find the optimal path for a robot to navigate from the start to the goal position, avoiding obstacles. An animation of the path planning process is generated to visualize the solution.

## Table of Contents

1. [Description](#description)
2. [Files](#files)
3. [Prerequisites](#prerequisites)
4. [Usage](#usage)
5. [Parameters](#parameters)
6. [Example](#example)
7. [Results](#results)
8. [Notes](#notes)

## Description

This project is designed to find the shortest path for a robot navigating through a 2D plane populated with obstacles. The robot can move in steps with specific angles (0, ±30, ±60 degrees), and each step is of a fixed size defined by the user. The program visualizes the robot’s movement and plots the explored nodes and the final path if the goal is reached.

The main components of the project include:
- **Vertex Class:** Represents each point in the search space, storing its coordinates, orientation, cost, and parent node.
- **Movement Functions:** Defines five types of movements (0°, ±30°, ±60°) that the robot can take from any given point.
- **Shape Map Function:** Constructs a 2D grid that represents the obstacle map with different buffer zones.
- **Search Algorithm:** Uses a breadth-first search approach to explore possible paths from the start to the goal vertex.
- **Path Visualization:** Plots and animates the explored nodes and final path using Matplotlib.

## Files

- **main.py:** The primary script containing the implementation of the path-planning algorithm and visualization.
- **README.md:** This file.
- **results.mp4:** A video demonstration of the path planning result for the specified test case.

## Prerequisites

Ensure that you have the following Python libraries installed:

- `numpy`
- `matplotlib`

You can install these dependencies using the following command:

```bash
pip install numpy matplotlib
```

## Usage

To run the script, use the following command:

```bash
python main.py
```

### Input Parameters

You will be prompted to enter the following parameters:

1. **Start X:** X-coordinate of the starting position.
2. **Start Y:** Y-coordinate of the starting position.
3. **Start Orientation:** Orientation angle of the robot at the start position (in degrees).
4. **Goal X:** X-coordinate of the goal position.
5. **Goal Y:** Y-coordinate of the goal position.
6. **Goal Orientation:** Orientation angle of the robot at the goal position (in degrees).
7. **Clearance:** Minimum distance from the obstacles.
8. **Robot Radius:** Radius of the robot.
9. **Step Size:** The step size for each move (range: 1 <= L <= 10).

### Example

For the following input:

- **Start X:** 20
- **Start Y:** 20
- **Start Orientation:** 30
- **Goal X:** 575
- **Goal Y:** 125
- **Goal Orientation:** 60
- **Clearance:** 5
- **Robot Radius:** 2
- **Step Size:** 6

The algorithm will attempt to find a path from the start to the goal position, avoiding any obstacles.

### Running the Program

Once you enter the parameters, the program will:

1. Validate the start and goal positions.
2. Create the shape map with the provided clearance and robot radius.
3. Use a breadth-first search algorithm to explore potential paths.
4. If the goal is reachable, display the explored path and animate the final path from start to goal.
5. Display the total cost to reach the goal and the execution time of the program.

## Results

If the program finds a valid path from the start to the goal, it will display:

1. **Explored Vertices:** Red points representing the explored nodes.
2. **Final Path:** A green line representing the optimal path.
3. **Animation:** An animation of the path planning process will be shown in a pop-up window.

For a visual demonstration, refer to the `results.mp4` file, which contains an example run of the path planning algorithm.

## Notes

- The start and goal positions must be within the map boundaries and not within any obstacle.
- The step size affects the smoothness and efficiency of the path planning. A larger step size might miss narrow passages, while a smaller step size increases computation time.
- The animation will be generated only if a valid path is found from the start to the goal.
- The `results.mp4` file showcases the implementation and provides a visual understanding of the program's functionality.

For further information or if you encounter any issues, please feel free to reach out. Happy coding!
