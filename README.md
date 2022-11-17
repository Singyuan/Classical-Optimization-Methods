# Classical-Optimization-Methods-4-TSP

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#data">Data</a></li>
    <li><a href="#demo">Demo</a></li>
	<li><a href="#references">References</a></li>
  </ol>
</details>

## Introduction
This repo is a note about applying classical optimization methods to traveler salesman problem (TSP) from the 2021 fall class "Computation in Data Science" by Prof. Fred Phoa in NTU. Here are miscellaneous methods including hill climbing, random walk, genetic algorithm (GA), simulated annealing (SA), tabu search (Tabu), particle swarm optimization (PSO) and ant colony optimization (ACO).

## Data
In the folder `data`, there are three files: `seven_test.json`, `adjacency_matrix_test.json` and `position_test.json` and two python code `scrap_distance_matrix.ipynb` and `scrap_position_matrix.ipynb`.
* The file `seven_test.json` contains the position you hold to find. Here, list 10 7-Eleven convenient store.

* The file `adjacency_matrix_test.json` contains the distance matrix which is shown the distance between any two nodes and the file `position_test.json` contains the longitude and latitude of these nodes.

* Two python code `scrap_distance_matrix.ipynb` and `scrap_position_matrix.ipynb` are used to generate the files `adjacency_matrix_test.json` and `position_test.json` by Web Scrapying.

## Demo
>Note that
>* the particle is a path which pass through all nodes and back to the first nodes;
>* the length of route path is the length of all route path.

1. **Hill climbing method**: I will randomly choose two nodes to swap, which stands for moving to next step.

2. **Random walk method**: Similar as hill climbing method.

3. **Genetic algorithm**: Genetic algorithm is contained three main parts: "Selection", "Crossover" and "Mutation".
	* Selection: The method I apply is as usual “roulette wheel selection” method. However, I convert the route length to fitness value by reciprocal.
	* Crossover: Here, I modify the "uniform crossover" method.
	* Mutation: Here, I modify the "consecutive multi-bits" method. I randomly choose consecutive multi-bits, and re-order these bits by counterclockwise change.

4. **Simulated annealing method**: Similar as hill climbing method.

5. **Tabu search method**:  The "swap" is chosen as "move", i.e. there are (choose 2 from n) of move in the candidate list. Moreover, the “expectation improvement aspiration” is chosen as aspiration criteria.

6. **Particle swarm optimization method**: 
	* Velocity: The difference of two positions are defined as 2-cycle permutations.
	* Scalar multiply Velocity (permutations): The scalar must be belongs to [0,1]. And it represents how many permutations you need to choose.
	* Position (path) plus Velocity (permutations): It means permuations acts on path.

7. **Ant colony optimization method**:
	* The amount of pheromone is related to evaporate rate and pheromone which is dropped by ants.
	* The transition probability is related to amount of pheromone and desirability values.

# References
The following references are from S.-J Chen in NUU.
1. [GA](http://debussy.im.nuu.edu.tw/sjchen/MachineLearning/final/Opt_GA.pdf)
2. [SA](http://debussy.im.nuu.edu.tw/sjchen/MachineLearning/final/Opt_SA.pdf)
3. [Tabu](http://debussy.im.nuu.edu.tw/sjchen/MachineLearning/final/Opt_Tabu.pdf)
4. [PSO](http://debussy.im.nuu.edu.tw/sjchen/MachineLearning/final/Opt_PSO.pdf)
5. [ACO](http://debussy.im.nuu.edu.tw/sjchen/MachineLearning/final/Opt_AntAlgo.pdf)