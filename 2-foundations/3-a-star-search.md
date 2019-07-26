# 1 - Intro
Going to use output from previous lesson as input for this lesson
  - output previously was a maze
  - output now will be maze + path from start to end of maze
A* is algorithm professional mapping apps use to find path from one point in city to another

# 2 - Motion Planning
Have to devise a plan on getting from point A to point B

# 3 - Quiz: Maze
7 steps to get from a to b in shortest path

# 4 - Quiz: Maze 2
11 steps to get from a to b in shortest path

# 5 - Coding the Shortest Path Algorithm
Give grid cell names


   0   1   2   3

0

1

2

3

Keep a list of nodes that you'd like to investigate further
  - Open [0,0] (your starting state)
  - make sure to mark it as checked so you don't recheck it later
  - check if it's your final goal state
Check spaces around you and see if they're open
  - Store the state that needs to be checked and how many expansions it took to get there (that's your g-value)
  [1,0] (1), [0,1] (1)
Now you continue expanding
  - always expand the one with the smallest possible g-value first
  [1,0] has 3 neighbors
    - [0,0] (already checked)
    - [2,1](2)
    - [1,1](2)
  - now go back and check the next lowest
    - [0,1] has three neighbors but they've already been expanded so we don't do any checks
You'll probably need to recurse to keep checking
When you get to the end, you'll have the path with the shortest g-value because you always expanded the lowest g-value node first

# 6 - A* Search
Variant of the general search algorithm that's more efficient than expanding every node
  - does minimum amount of work necessary to make progress to the goal

Uses a heuristic function
h(x,y) <= distance to goal from x,y

Now, f-value is g-value + heuristic value
  - start point is g-value 0, but heuristic value of 9 (because you're really far from the goal) so f-value is 9
  - always expand space with lowest f-value

Pseudocode for A*:
```
Search( grid, initial_point, goal_point ) :

Initialize an empty list of open nodes.

Initialize a starting node with the following:

x and y values given by initial_point.
g = 0, where g is the cost for each move.
h given by the heuristic function (a function of the current coordinates and the goal).
Add the new node to the list of open nodes.

while the list of open nodes is nonempty:

Sort the open list by f-value
Pop the optimal cell (called the current cell).
Mark the cell's coordinates in the grid as part of the path.
if the current cell is the goal cell:

return the grid.
else, expand the search to the current node's neighbors. This includes the following steps:

Check each neighbor cell in the grid to ensure that the cell is empty: it hasn't been closed and is not an obstacle.
If the cell is empty, compute the cost (g value) and the heuristic, and add to the list of open nodes.
Mark the cell as closed.
If you exit the while loop because the list of open nodes is empty, you have run out of new nodes to explore and haven't found a path.
```

# 7 - CODE: Starting A* Search


# 8 - CODE: Writing the A* Heuristic


# 9 - Pass by Reference in C++


# 10 - CODE: Adding Nodes to the Open Vector


# 11 - CODE: Initialize the Open Vector


# 12 - CODE: Create a Comparison Function


# 13 - CODE: Write a While Loop for the A* Algorithm


# 14 - CODE: Check fro Valid Neighbors


# 15 - Constants


# 16 - CODE: Expand the A* Search to Neighbors


# 17 - Arrays


# 18 - CODE: Adding a Start and End to the Board


# 19 - Congratulations!!


# 20 - How to Become More Proficient at C++
