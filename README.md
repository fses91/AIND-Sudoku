# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: We reduce the search space, because we are removing values which can't occur on a specific position,
because they have to occur on another position. 
For example if we have a unit (row, column, diagonal, square) which contains two times a value of length two,
we know that these are the only possible values for these two boxes, we don't now which value should go in which
of the two boxes, but we know that none of these values can be placed in any other box in the same unit.
We can generalize this solving strategy for n boxes of length n in the same unit, and so we are reducing the search space.
So when we add this function to our reduce_puzzle() function, we don't need to try out so many values. It would also be possible
to solve the sudoku without constraint propagation but we would have to generate all possibilities where the values can be, and
then take the solution which is not violating our sodoku rules.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Diagonal sudokus have a smaller search space than non diagonal sudokus, because of the
diagonal constraints.
For example we add the two diagonals (top left - bottom right, bottom left - top right), we have 
less possibilities to place a value. Because the initial constraints where column, row and square if
we now add the diagonal constraint we are now are not allowed to place values, where we were allowed 
without the diagonal constraint.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

