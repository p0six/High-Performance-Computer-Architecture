# High-Performance-Computer-Architecture

## ForeWord
The prjects are the course projects of CS6290 High Performance Computer Architecture.
Three projects are based on sesc simulator(link) and C++ programming. In each projects, source code of the simulator is modified to realize the requirement. 

The benchmark used is Splash 2.

## Environment Setting
To implement the simulator, compile it.
Use command:
```
cd
$ make 
```


## Project 1 Branch Prediction

Raytrace benchmark is used in this project to test the sesc branch prediction.

Part 3 requires the program to count the execution number of each branch prediction. Instructions are classified into four groups according to exe times of each(1-9, 10-99, 100-999, 1000+).

The modified part in Bpred.h and Bpred.cpp is clearly marked as `//My code`.

The output count format is:
Group | Group exe times | Group correct times | Number of Instructions

Only one core is working in this case, thus only one line is valid.


## Project 2 Cache Misses

fmm benchmark is used to test.

Implementation of NXLRU and seperating cache misses into three catogories: Compulsory, Conflict and Compacity.

The algorithm is:

First check compulsory misses, if the block never comes to the cache, the block is defined as compulsorymiss.

A Hashset is used to record the block information.

Then A fully associate structure is simulated to be a fully associated cache to check the miss is a conflict miss. This is because the defination of the conflict misses is it never happens in a fully associate cache. So if the coming miss is not in the data structure, it is a capacity miss. If not, it is a conflict miss.

## Project 3 Coherence Misses and 3Cs
lu is used to test.

Based on Project 2, coherence misses are considered since multi processors are introduced.

One more data structure is added to monitor the coherence misses during the communication of cores. 