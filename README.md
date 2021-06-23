# Sudoku Solver

-	Sudoku is one of the most popular logic-based number-placement puzzle game. The literal meaning of "Su-doku" in Japanese is "the number that is single".

-	The objective is to fill a nine-by-nine (9x9) grid with digits so that each row, column and 3x3 section contain number between 1 and 9, with each number used once and only once in each section. The Sudoku game players are provided with partially filled grid meant to be solved.

-	To solve sudoku one doesn't require the knowledge of mathematics but require the logic and reasoning. Solving Sudoku Puzzles daily helps with your brain. It improves the concentration and logical thinking. One can look for sudoku puzzles given in Newspapers or can play them online provided by many websites. 

## About:

This script is a sudoku solver that can solve almost any sudoku puzzle by implementing the **Backtracking Algorithm** which is written in the ```C++``` language.

---

# Documentation

### Backtracking:

Backtracking is a technique which basically tests all possible options recursively and returns all the correct ones. At any point if no possible option is valid or no further action can be taken, it backtracks to the last valid state. It is used to solve various well known problems such as N-Queens, Rat in a Maze, Hamiltonian Cycle etc. 

### Problem Statement: 

Given an unsolved sudoku puzzle, we have to generate all possible solutions of the sudoku.

### Solution:

The language of the problem statement “all the possible solutions” is generally a hint towards applying backtracking algorithm. The approach of the solution has been listed in detail below.

### Approach:

A sudhoku puzzle can be solved like any other **Backtracking** problem. It can be solved by, one by one assigning numbers to empty cells. Before assigning a number, we check whether it is safe to assign. We make sure that it is safe to assign a number in an empty cell by verifying that the same number is not present in the current row, current column and current 3X3 subgrid or the box. After checking for safety, we assign the number, and recursively check whether this assignment leads to a solution or not. If the assignment doesn’t lead to a solution, then we try the next possible number for the current empty cell. And if none of the number possible numbers from 1 to 9 lead to a solution, we return false and print that no solution exists.

## Overview of the Code

### Input:

We’ll take line separated input for each row of the sudoku and space separated input for each digit in the row. The entire sudoku will be stored in a 2D Matrix of 9x9 dimension. The empty cells are denoted by **‘0’** and the non-empty cells by their digits.

```C++
int sudoku[N][N];
    
    for(int  i = 0; i < 9; i++)
    {
        cout<<"Enter space separated elements of row "<<i<<" : ";
        for(int j = 0; j < N; j++)
        {
           cin>>sudoku[i][j];
        }
    }
```   

![Input](https://user-images.githubusercontent.com/53916781/123072386-1ecb6980-d433-11eb-9c8e-af675ee57481.PNG)

   
### Functions:

1. ```findEmptySpace()```: This function searches the sudoku grid to find an entry that is still unassigned. If found, the reference parameters row, column will be set the location that is unassigned, and true is returned. If no unassigned entries remain, false is returned.

2. ```isValid()```: This functon returns a boolean which indicates whether it will be legal to assign number to the given row, column location.

3. ```solveSudoku()```: This function takes a partially filled-in sudoku grid and attempts to assign values to all unassigned locations in such a way to meet the requirements for Sudoku solution (non-duplication or no collision across rows, columns, and boxes).

4. ```isPresentInRow()```: This function returns a boolean which indicates whether an assigned entry in the specified row matches the given number. 

5. ```isPresentInColumn()```: This function returns a boolean which indicates whether an assigned entry in the specified column matches the given number.

6. ```isPresentInBox()```: This function returns a boolean which indicates whether an assigned entry within the specified 3x3 box matches the given number.

7. ```printSudoku()```: This function is a utility function which prints the solved sudoku.

8. ```main()```: This is the main driver function. This function takes the partially-filled sudoku board as input from the user and calls the ```solveSudoku()``` as well as ```printSudoku()``` with the sudoku board as the argument. In case of no solution, it prints "**No solution exists.**".

### Output:

The output prints all the possible solutions of the given sudoku. In our case there is only possible solution for the given input and it is shown below.

![Output](https://user-images.githubusercontent.com/53916781/123075380-d19cc700-d435-11eb-9840-45f943378854.PNG)
