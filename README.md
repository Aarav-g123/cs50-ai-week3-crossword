# AI Crossword Puzzle Generator

This Python program generates crossword puzzles by solving a constraint satisfaction problem using an AI approach. Given the structure of a crossword puzzle grid and a list of words, the program determines which words should be placed in each sequence of squares to fill in the puzzle. The solution is modeled as a constraint satisfaction problem where variables represent sequences of squares and their associated values are words from the given list.

## Background

The generation of crossword puzzles involves determining which words fit into the grid while adhering to the structure and constraints. The problem can be approached as a constraint satisfaction problem, where variables correspond to sequences of squares and the goal is to assign words to these variables while satisfying constraints.

### Puzzle Structure

The crossword puzzle structure is defined in a text file (e.g., `structure1.txt`) with a grid that indicates the layout of the puzzle. Each cell is either marked as empty or blocked. The grid cells define the placement of words in the puzzle.

### Words List

A list of words is provided in a separate text file (e.g., `words1.txt`). These words are the candidates for filling the crossword puzzle.

### Variables and Constraints

In the provided structure, each word to be placed corresponds to a variable. Each variable is defined by:
- Starting row index (i)
- Starting column index (j)
- Direction (across or down)
- Length of the word

Unary constraints are imposed by the length of the word. If a word's length does not match the variable's length, it is immediately eliminated from consideration.

Binary constraints arise from the overlap between neighboring variables. Two variables that share a common square must have matching characters at the overlapping positions. Overlaps are represented as character indices within the variables' words.

An additional constraint is that all words must be distinct to prevent repetition in the puzzle.

## Running the Program

To generate a crossword puzzle, run the `generate.py` script with the following command:

```shell
python generate.py data/structure1.txt data/words1.txt output.png
```

Replace `structure1.txt` and `words1.txt` with the appropriate filenames for the puzzle structure and words list you want to use. The generated crossword puzzle will be saved as `output.png`.

## Optimization and Constraint Propagation

The program enforces node consistency and arc consistency to narrow down the domain of possible words for each variable. This helps to efficiently explore the solution space. The AI uses backtracking search with the minimum remaining values and degree heuristics to find a solution.

## License

This project is licensed under the MIT License.

## Acknowledgments

This project was developed as part of CS50 AI Week 3, a Harvard computing course.

For any questions or concerns, please contact me.
