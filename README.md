# Introduction
This was the final project I submitted for my algorithms class in Fall of 2015. It finds all possible ways to fill a given board with a given set of tiles.

# Inputs/Outputs
For an example of the input this program accepts <a href="/tiling_problem/boards/checkerboard">see here</a>. The input files are hardcoded in <a href="/tiling_problem/read.py">read.py</a>. The program sets the largest contiguous area as the board and every other contiguous area as the pieces. Also, the characters that compose the pieces must match with the characters of the board.

The program outputs each solution (in text) and the time it took for the solution to be discovered for all solutions. Then once all solutions have been found, one of the solutions is displayed graphically.

# Algorithm
This is an NP-hard problem. This algorithm attempts to solve the problem as quickly as possible by first recognizing all rotational and reflectional symmetries of the board and pieces, in order to test the minimum number of configurations. Then the piece that fits in the least number of places is fixed in the board. This process is repeated for the remaining pieces. In order to greatly speed up the run time, connectedness of the board (is it still contiguous or has it been broken into two pieces) is checked at each step. If the board has been split, then the program will attempt to fill the smaller half of the board and if it can then it will fill in the larger remaining half. Because this algorithm returns all solutions, all solutions must either be tested or eliminated. Checking if the board is split allows for branches to get eliminated as quickly as possible. It also takes into consideration a special case where all pieces are of the same size, say n, and if the size of one of the split boards is not divisible by n, it will eliminate that possibility.
