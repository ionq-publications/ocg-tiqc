# ocg-tiqc
This repository contains artificially generated circuit graphs used to benchmark our calibration optimization algorithms.

## Benchmark circuit graphs
To benchmark the scalability of our algorithms, we generated artificial batches of circuits for different system sizes. Each batch consists of five line-shaped graphs, five star-shaped graphs, five random trees, and *N* randomly selected small-diameter regular graphs, where *N* is the number of qubits. This particular composition was motivated by the line, star, and tree shapes appearing frequently in our real-world examples. Small diameter, regular graphs of the form (*k,d,n*), where *k* is degree of the graph, *d* is the diameter of the graph, and *n* is the number of vertices, were selected as they are tailor made to leverage the all-to-all qubit connectivity available on a TIQC [1].

## File structure
Benchmark circuits can be found in `batches` as JSON files grouped in folders per system size (10...20). Each JSON file is a batch structured as a list of 15+N circuit graphs. Each circuit graph is represented as a dictionary with keys `graph` and `stat`, where `graph` contains a list of graph edges, and `stat` contains the total numbers of vertices and edges used for indexing. For example, a linear graph on five qubits can be represented as follows:
```json
{"graph":[[0, 1], [1, 2], [2, 3], [3, 4]], "stat":[5,4]}
```
## References
<a id="1">[1]</a> Y. Nam and D. Maslov, Low-cost  quantum  circuits  for  classically  intractable  instances  of  thehamiltonian dynamics simulation problem, npj Quantum Information, 5 (2019).
