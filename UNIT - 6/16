#Develop a genetic algorithm for the Quadratic Assignment Problem
import random

# Define the size of the problem instance
n = 10

# Define the distance matrix and flow matrix
distances = [[random.randint(1, 10) for j in range(n)] for i in range(n)]
flows = [[random.randint(1, 10) for j in range(n)] for i in range(n)]

# Define the population size, number of generations, and mutation rate
population_size = 50
num_generations = 100
mutation_rate = 0.1

# Define the fitness function
def fitness(individual):
    total_cost = 0
    for i in range(n):
        for j in range(n):
            total_cost += distances[i][j] * flows[individual[i]][individual[j]]
    return total_cost

# Define the crossover operator
def crossover(parent1, parent2):
    # Choose a random crossover point
    crossover_point = random.randint(0, n-1)
    # Create the child by combining the parents
    child = parent1[:crossover_point] + [gene for gene in parent2 if gene not in parent1[:crossover_point]]
    return child

# Define the mutation operator
def mutation(individual):
    for i in range(n):
        if random.random() < mutation_rate:
            # Swap the gene with a random other gene
            j = random.randint(0, n-1)
            individual[i], individual[j] = individual[j], individual[i]

# Initialize the population randomly
population = [list(range(n)) for i in range(population_size)]
for individual in population:
    random.shuffle(individual)

# Run the genetic algorithm
for generation in range(num_generations):
    # Evaluate the fitness of each individual
    fitness_scores = [fitness(individual) for individual in population]
    # Select the parents for the next generation
    parent1, parent2 = random.choices(population, weights=fitness_scores, k=2)
    # Create the next generation
    new_population = [crossover(parent1, parent2) for i in range(population_size)]
    # Mutate the new population
    for individual in new_population:
        mutation(individual)
    # Replace the old population with the new population
    population = new_population

# Find the best individual and its fitness score
best_individual = min(population, key=fitness)
best_fitness = fitness(best_individual)

print("Best individual:", best_individual)
print("Best fitness:", best_fitness)

#Evaluate its performance on a set of large-scale instances.
"""
The Quadratic Assignment Problem (QAP) is a well-known optimization problem that involves 
assigning facilities to locations with the goal of minimizing the sum of pairwise distances between all facility 
pairs weighted by the product of their respective flows. The problem is known to be NP-hard, and exact methods become 
intractable for large problem instances. In this context, heuristic algorithms such as genetic algorithms have emerged as viable alternatives.

A genetic algorithm is a population-based optimization method inspired by the natural process of evolution. 
The algorithm starts by randomly generating an initial population of potential solutions, each represented as 
a permutation of facilities. The population is then iteratively improved by selecting the fittest individuals based on a fitness function, 
which measures the quality of each solution, and applying genetic operators such as crossover and mutation to create new offspring. 
The process continues until a stopping criterion is met, such as a maximum number of iterations or a desired fitness threshold.

To implement a genetic algorithm for the QAP, we first need to define the encoding scheme, fitness function, genetic operators, 
and parameter settings. One possible encoding scheme is to represent each solution as a permutation of facilities, 
where the position of each facility in the permutation corresponds to its location assignment. 
The fitness function can be defined as the sum of pairwise distances between all facility pairs weighted by their respective flows, 
which can be efficiently computed using matrix multiplication. The genetic operators can include two-point crossover, 
which exchanges segments of two parent solutions to create new offspring, and mutation, which randomly swaps two facilities in a solution. 
The parameter settings can be optimized through experimentation, such as the population size, crossover rate, mutation rate, and selection mechanism.

To evaluate the performance of the genetic algorithm, we can test it on a set of benchmark instances, such as those available from the QAPLIB repository.
We can compare the quality of the solutions obtained by the algorithm to those obtained by exact methods or other heuristic algorithms, 
as well as the running time and convergence properties of the algorithm. We can also explore different variations of the algorithm, 
such as hybrid approaches that combine genetic algorithms with local search or other techniques.
"""
