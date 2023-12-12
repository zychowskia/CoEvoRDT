# Coevolutionary Algorithm for Building Robust Decision Trees under Minimax Regret


## Adam Żychowski, Andrew Perrault, Jacek Mańdziuk

### AAAI 2024


## Introduction

This Python script implements a coevolutionary algorithm (CoEvoRDT) designed to create robust Decision Trees (DTs) capable of handling noisy high-dimensional data in adversarial contexts. Motivated by the limitations of traditional DT algorithms, we leverage adaptive coevolution to allow DTs to evolve and learn from interactions with perturbed input data. CoEvoRDT alternately evolves competing populations of DTs and perturbed features, enabling construction of DTs with desired properties. CoEvoRDT is easily adaptable to various target metrics, allowing the use of tailored robustness criteria such as minimax regret. Furthermore, CoEvoRDT has potential to improve the results of other state-of-the-art methods by incorporating their outcomes (DTs they produce) into the initial population and optimize them in the process of coevolution. Inspired by the game theory, CoEvoRDT utilizes mixed Nash equilibrium to enhance convergence. The method is tested on 20 popular datasets and shows superior performance compared to 4 state-of-the-art algorithms. It outperformed all competing methods on 13 datasets with adversarial accuracy metrics, and on all 20 considered datasets with minimax regret. Strong experimental results and flexibility in choosing the error measure make CoEvoRDT a promising approach for constructing robust DTs in real-world applications.

## Requirements

Make sure you have the following libraries installed:

- numpy
- sklearn
- nashpy
- genetic\_tree
- perturbation

You can install them using:

```bash
pip install numpy sklearn nashpy genetic_tree
```

## Usage
```bash
python coevolutionary_algorithm.py
```

The script initializes populations of decision trees and perturbations, evolving them over several generations. The coevolutionary process consists of crossover, mutation, and selection operations. Fitness is evaluated based on accuracy and regret metrics.

### Note

The script uses the Fashion-MNIST dataset by default. You can modify the dataset by uncommenting and using one of the other available datasets.

## Parameters

Adjust the following parameters in the script according to your needs:

* TREES\_POPULATION\_SIZE: Number of decision trees in the population.
* PERTURBATIONS\_POPULATION\_SIZE: Number of perturbations in the population.
* TOP\_N\_TREES: Top N decision trees considered during perturbation fitness evaluation.
* TREES\_MUTATION\_RATE: Probability of mutation for decision trees.
* PERTURBATIONS\_MUTATION\_RATE: Probability of mutation for perturbations.
* MUTATION\_REPEATS: Number of mutation iterations.
* TREES\_CROSSOVER\_RATE: Probability of crossover for decision trees.
* PERTURBATIONS\_CROSSOVER\_RATE: Probability of crossover for perturbations.
* GENERATIONS: Total number of generations.
* GENERATIONS\_NO\_IMPROVEMENT\_LIMIT: Number of generations without improvement to stop the algorithm.
* GENERATIONS\_BETWEEN\_SWITCH: Number of generations before switching between decision tree and perturbation evolution.
* OPTIMIZATION\_METRIC: Metric used for optimization (e.g., 'MAX\_REGRET' or 'PERTURBED\_ACCURACY').


## Results

The script outputs the best decision tree's fitness value on the training and testing sets for each iteration. Additionally, it appends the fitness value and runtime for each iteration to a txt file.


