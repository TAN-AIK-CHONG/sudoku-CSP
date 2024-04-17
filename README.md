# sudoku-CSP
Jupyter notebook is used to display the sudoku puzzle. A few different search algorithms to solve sudoku is explored.

## Sudoku as a Constraint Satisfaction Problem
- The current state of the Sudoku Board is determined by its variables. 
- In the case of Sudoku, there are 81 variables, which are the individual cells in the board.
- The variables have values in the domain {1,2,3 ... 7,8,9}
- The constraints are the rules of sudoku: 
    - No repeat number in the same row
    - No repeat number in the same column
    - No repeat number in the same grid

## Solving with Breadth First Search
Explore each state of the board by filling in one cell at a time. Using a queue, implement BFS to explore all possible states of the board at each depth. A solution is found once all cells are filled.

## Solving with Backtracking
Explore each state of the board with Depth First Search instead, and backtracking whenever a constraint is violated.

## Solving with Greedy Seach
In the context of Sudoku, a greedy search algorithm might select the best possible move based on some heuristic, such as selecting the cell with the fewest remaining possible values. In sudoku, there will always be cells with a possible move of 1 only. As such, we are able to solve the puzzle much faster by filling in these cells first, and in turn, it reduces the number of possibilities of other cells.

## Solving Sudoku with A* Search
In the context of Sudoku, we can also consider that solving cells that impact more unsolved cells might be more efficient, as it reduces the total number of possibilities of as many cells as possible.
For the algorithm, I prioritise choosing cells with the least number of possibilities, as we want to reduce the amount of backtracking, and amongst the cells with lowest possibility, we prioritise the cell with the greatest impact. 
However the time complexity seems to take even longer, since even for greedy search there is already no backtracking. For this algorithm, we also have to consider the time taken to determine the highest impact cell.
