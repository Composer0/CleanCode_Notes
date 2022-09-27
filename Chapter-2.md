# Chapter 2 Takeaways: Meaningful Names

## Use Intention-Revealing Names
"Names should reveal intent." p.18
Should make clear "why it exists, what it does, and how it is used." p.18
"If a name requires a comment, then the name does not reveal its intent." p.18

ex.  int d; // elapsed time in days  p.18

ex. Explicit Code
public List<int[] > getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    for (int[] cell : gameBoard)
        if (cell[STATUS_VALUE] == FLAGGED)
            flaggedCells.add(cell);
        return flaggedCells;
}

ex. Increased Clarity
public 