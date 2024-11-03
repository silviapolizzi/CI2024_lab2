# Lab 2 Computational Intelligence
## TSP description
The Traveling Salesman Problem (TSP) is an NP-hard problem in combinatorial optimization. Given a list of cities and the distances between each pair of cities, the task is to find the shortest possible tour that visits each city exactly once and returns to the original city.

---

## Algorithms implemented

The laboratory task is to implement two algorithm: one fast but more approximated and one slower but more precise. The algorithms implemented are the Greedy Algorithm and the Genetic Algorithm.

### Greedy Algorithm
The Greedy Algorithm is a simple algorithm that starts from a random city and at each step selects the nearest city that has not been visited yet. The algorithm stops when all the cities have been visited.

### Genetic Algorithm
The Genetic Algorithm is a metaheuristic inspired by the process of natural selection. The algorithm starts by generating an initial population of individuals, each representing a possible solution to the problem. The individuals are then evaluated and the best ones are selected to generate the next generation. The selection process is based on the fitness of the individuals, which is calculated based on the distance of the path. The selected individuals are then crossed over and mutated to generate the next generation. The process is repeated for a number of generations.

#### Fitness Function
The fitness function is used to evaluate the quality of the individuals. In this laboratory task, the fitness function is based on the total distance of the path. The fitness of an individual is calculated as the inverse of the total distance of the path, so that the higher the fitness, the better the individual.

---

#### Parent Selection
The parent selection process is used to select the individuals that will be used to generate the next generation. There are several methods that can be used for parent selection, such as roulette wheel selection, tournament selection, and rank selection. All these methods have been tried in this laboratory task to find the best one.

1. The roulette wheel selection method is based on the fitness of the individuals. The probability of an individual being selected is proportional to its fitness.

2. The tournament selection method is based on selecting a random subset of individuals and then selecting the best individual from that subset.

3. The rank selection method is based on ranking the individuals based on their fitness and then selecting the best individuals.


After some tests, the best parent selection method has been found to be the *tournament* method.

#### Crossover
The crossover process is used to generate new individuals by combining the genetic information of the parents. There are several methods that can be used for tsp, such as Edge Recombination and Inver Over. All these methods have been tried in this laboratory task to find the best one.

1. The edge recombination crossover method is based on the edges of the parents. The method starts by selecting a random edge from one of the parents and then selects the next edge based on the edges that are adjacent to the current edge.

2. The inver over crossover method is based on taking a random element from one parent and then selecting an edge of this element from the other parent and then preserve this edge in the offspring, swapping the other elements between them as appear in the first parent, in the offspring.

After some tests, the best crossover method has been found to be the *edge recombination* method.

#### Mutation
Mutation is used to introduce diversity in the population and prevent premature convergence. There are several methods that can be used for tsp, such as Inverse, and Scramble. All these methods have been tried in this laboratory task to find the best one.

1. The inversion mutation method is based on selecting a random subset of the path and then inverting the order of the cities in that subset.

2. The scramble mutation method is based on selecting a random subset of the path and then shuffling the order of the cities in that subset.

After some tests, the best mutation method has been found to be the *inversion* method.
The mutation rate is reduced over time to allow the algorithm to converge to a better solution.

#### Other tweaks
In order to improve the performance of the genetic algorithm, some tweaks have been made to the algorithm. These tweaks include:

1. Replacement Rate: Steady-state, replacing part of population where offsprings and parents compete.
2. Diversity Threshold: Maintain population diversity.


#### Parameters

| Parameter | Value | Note |
| --- | --- | --- |
| Population Size | 200 | 500 for China*|
| Number of Generations | 50000 | |
| Number of Parents | 40 | |
| Initial Mutation Rate | 0.8 | |
| Replacement Rate | 0.5 | Steady-state |
| Diversity Threshold | 0.7 | Periodic check |

*China has a large number of cities (726) and requires a larger population size to explore the search space effectively.

---

## Results

| State | Number of Cities | Greedy Path Lenght | Genetic Path Lenght |
| --- | --- | --- | --- |
| China | 726 | 63962.92 km | 54559.40 km |
| Italy | 46 | 4436.03 km | 4245.04 km |
| Russia | 167 | 42334.16 km | 36044.49 km |
| USA | 326 | 48050.03 km | 40481.11 km |
| Vanuatu | 8 | 1475.53 km | 1345.54 km |


## Discussion

* Comparison of Algorithms: The Genetic Algorithm generally outperforms the Greedy Algorithm, especially in larger instances, due to its ability to explore the solution space more effectively. However, the Greedy Algorithm is faster and can provide a good approximation for smaller instances.
* Impact of Parameters: Adjusting parameters such as population size (notably for China), mutation rate, and diversity threshold can significantly influence the Genetic Algorithm's performance.
* Scalability: While the Genetic Algorithm performs well, scalability remains a challenge for very large TSP instances, suggesting the need for further optimization techniques or more powerful computational resources.
* Future Enhancements: Consider integrating Greedy Algorithm to initialize the Genetic Algorithm and exploring other crossover and mutation methods.


---
