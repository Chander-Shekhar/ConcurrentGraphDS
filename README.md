# ConcurrentGraphDS
This repository contains the implementation of a lock-based Concurrent Graph Data Structure.
The algorithm is described in technical report '**Maintaining Acyclicity of Concurrent Graph Objects**' which can be accessed here: https://arxiv.org/abs/1611.03947.

Binary files can be found in *bin* directory.
Source files can be found in *src* directory.

The subdirectory *src/data_structure* provides the source code for Graph data structure variants, as decribed below:
1. Sequential Graph data structure
2. Concurrent Coarse Lock Graph Data Structure
3. Concurrent Fine Lock Graph Data Structure without deletion of incoming edges
4. Concurrent Fine Lock Graph Data Structure with deletion of incoming edges

The subdirectory *src/acyclicity* provides the source code for Graph data structure variants which maintain acyclicity, as decribed below:
1. Sequential Graph data structure
2. Concurrent Coarse Lock Graph Data Structure
3. Concurrent Fine Lock Graph Data Structure without deletion of incoming edges of deleted vertices (Cycle detection using collect)
4. Concurrent Fine Lock Graph Data Structure with deletion of incoming edges of deleted vertices (Cycle detection using Reachability)
5. Concurrent Fine Lock Graph Data Structure without deletion of incoming edges of deleted vertices (Cycle detection using collect)
6. Concurrent Fine Lock Graph Data Structure with deletion of incoming edges of deleted vertices (Cycle detection using Reachability)

To compile any source file, run the command:
`g++ -std=c++11 filename.cpp -lpthread -o filename.o`

To run this binary file, use the following format:
`./filename numOfThreads numOfInitialVertices numOfOperationsPerThread`

Example:
1. For sequential program run: ./sequential 1 1000 150000
2. Whereas for a Concurrent program run: ./conc 150 1000 1000
(A concurrent program of 150 threads with 1000 operations per thread means total 150000 operations.)

You can vary the workload distribution of these operations inside each of these programs.

If you have any questions, please contact: cs15mtech01004@iith.ac.in
