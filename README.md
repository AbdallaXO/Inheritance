## Genetic Inheritance Simulation
Overview
This program simulates the genetic inheritance of blood types across three generations of a family. It uses random allele assignment and recursive structures to model parent-child relationships. The resulting family tree includes details of each member's blood type and generational relationships.

Features
Simulates a family tree with 3 generations.
Each person has two blood type alleles (A, B, or O).
Parent-child relationships are represented using pointers.
Alleles are inherited randomly from parents or generated randomly for the first generation.
Memory management ensures all dynamically allocated memory is freed.
How It Works
Person Structure:

Each person has:
An array of two parent pointers (parents[2]).
An array of two alleles (alleles[2]).
Generation Creation:

The create_family function recursively generates a family tree:
For non-root generations, it assigns alleles from parents randomly.
For the root generation, it assigns random alleles directly using the random_allele function.
Printing the Family Tree:

The print_family function displays the family tree with indentation representing generations:
Root generation: "Child (Generation 0)"
1st generation: "Parent (Generation 1)"
Older generations: "Grandparent" or "Great-Grandparent".
Memory Management:

The free_family function recursively frees memory allocated for each person and their parents.
Functions
person *create_family(int generations)
Recursively generates a family tree.
Allocates memory for each person and assigns alleles based on parental alleles or randomly.
void print_family(person *p, int generation)
Recursively prints the family tree with proper formatting and generational labels.
void free_family(person *p)
Recursively frees memory allocated for the family tree.
char random_allele()
Randomly selects a blood type allele ('A', 'B', or 'O').
File Structure
main.c: Contains all code for creating, printing, and freeing the family tree.
