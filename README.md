# Million Queens: Deep Dive Into Stochastic Local Search

**Author**: Yixian Chen<br /><br />
**Author**: YiMing Chen<br /><br />
**Author**: Junkai Cai<br /><br />


# Abstract

NQueen has been a typical AI problem since last century. There are quite a few algorithms has been developed to solve the problem efficiently. The solver gives a placing of N-queens on the chessboard so that no two queens attack each other. 

In this project, we developed techniques to shrink the problem space and improve the efficiency of generating stochastic moves, resulting in solving the NQueen problem in linear time, around 1000 CPU cycles per Queen for very large N.

In this project, we mainly discussed stochastic local search algorithms for the NQueen problem. Besides, we used backtracking algorithm (with MRV and forward checking) as a comparison. Based on the original local search idea, we developed Random Swapping, Simulating Annealing, Min Conflict, Smart Select and Random Greedy solver. By analyzing the statistics, we gladly observed that the performance increased dramatically. With the combination of Min Conflict solver and Smart Select solver, our Random Greedy solver solves 300 million of queens within 300 seconds. The techniques we developed may be generalized for other problems with high solution density and low barrier of local optimum.

# How to make:
1. Unzip the code.zip
2. Go to the folder NQueen, run 
```
make all
```

# How to run:
1. After make, run the program by
```
./nqueen arg1 arg2 arg3 arg4 arg5 arg6 arg7
```

*noticed that if arg6==3, only arg1 matters (backtrack sovler only takes arg1 and arg6)
*Please don't try N>100 for backtracking search.

- **arg1**: N queens
- **arg2**: repeat N times
- **arg3**: stimulated annealing soft_threshold, 0 means turnnig off
- **arg4**: if in plateau, there is a probablity of 1/(2^(arg3-1)+1) to do swap_soft
- **arg5**: verbose level (bits)
- **arg6**: select solver (0:NQueenSwapSolver 1: SmartSelectSwapSolver 2: RandomGreedySolver 3: Backtrack (ORG and BT+FC+MRV) )
- **arg7**: output path, skip if don't want to write output into file
