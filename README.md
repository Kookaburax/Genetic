# Genetic Algorithm Solver Package

The Genetic Algorithm (GA) Solver is a python code that provides tools for solving optimization problems using genetic algorithms. This package includes classes and functions for defining genetic algorithm problems, initializing populations, evolving populations over generations, and analyzing the results.
## Usage
### 1. Define a Problem
To use the GA Solver, you need to define a problem by subclassing the GAProblem class. You should implement the following methods:

mutation(chromosome): Perform mutation operation on an individual's chromosome.
create(): Generate a new chromosome.
calculate_fitness(chromosome): Evaluate the fitness of an individual.
reproduction(parent1, parent2): Perform crossover operation between parents' chromosomes.

```python
from ga_solver import GAProblem

class MyProblem(GAProblem):
    def mutation(self, chromosome):
        # Your implementation
        pass

    def create(self):
        # Your implementation
        pass

    def calculate_fitness(self, chromosome):
        # Your implementation
        pass

    def reproduction(self, parent1, parent2):
        # Your implementation
        pass
```
        
## 2. Initialize and Evolve the Population
Once you've defined your problem, you can initialize the GA solver with your problem class and parameters. Then, you can reset the population and evolve it over generations.
from ga_solver import GASolver
```python

problem = MyProblem()
solver = GASolver(problem)
solver.reset_population()
solver.evolve_until()
```

## 3. Analyze the Results
After evolving the population, you can analyze the results to find the best individual and evaluate its fitness by calling the show_generation_summary of the GASolver.
```python
print(f"{solver.show_generation_summary()}")    # Print generation summary
```
## Examples
You can find example usage of the GA Solver Package in the examples directory.

(Don't forget to move the GASolver in the same folder)
## Configuration
There are some parameters that can be modify as you want.

 - Create an instance of the GASolver class, optionally specifying the selection rate and mutation rate parameters:
```python
solver = GASolver(selection_rate=0.5, mutation_rate=0.1)
```
selection_rate: The rate of selection for the genetic algorithm, ranging from 0 to 1.0. Default is 0.5.

mutation_rate: The rate of mutation for the genetic algorithm, ranging from 0 to 1.0. Default is 0.1.

-  Initialize the population using the reset_population method:
```python
solver.reset_population(pop_size=50)
```
pop_size: The size of the population to be initialized. Default is 50.

- Evolve the population until termination conditions are met using the evolve_until method:
```python
solver.evolve_until(max_nb_of_generations=500, threshold_fitness=None)
```
max_nb_of_generations: The maximum number of generations to evolve the population. Default is 500.

threshold_fitness: The threshold fitness value. If provided, the evolution process will stop when the best individual's fitness reaches or exceeds this value. Default is None.
