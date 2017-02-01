# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

#########################################################
# Question 1 (Naked Twins) 

Q: How do we use constraint propagation to solve the naked twins problem?  

A: The constraint propagation principles were already present in the existing search process, as there are functions such as eliminate and only_choice to reduce the number of potential solutions to be evaluated.

The "eliminate" and "only_choice" functions reduce the problem to a human-like interaction, making the search function a little more manageable - and reducing the risk of “combinatorial explosion”.

The "naked_twins" function reduces further the number of potential combinations analyzed by the "reduce_puzzle" function.

We propagate the constraints found by those functions onto other peers of the twins, making the search converge to a solution quicker than otherwise.

I have tested the naked_twins right after eliminate and right after "only_choice", and found that, in both cases, the solution for the diagonal sudoku was found in 12 iterations.

##############################################################
# Question 2 (Diagonal Sudoku)

Q: How do we use constraint propagation to solve the diagonal sudoku problem? 

A: The existing solution defines units where constraints must be satisfied: rows, columns, and square boxes. In each of these units, digits 1 to 9 must appear only once.

The diagonal sudoku is a similar game, but has two extra diagonal units, where digits from 1..9 may appear only once.

In order to transform the existing standard sudoku into a diagonal sudoku, I simply added two more sets to the list of units that were analyzed: forward diagonal (A1..I9) and backward diagonal (I1..A9) 

From then on, I used the existing search with contstraint propagation to resolved the problem.

###############################################################

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.