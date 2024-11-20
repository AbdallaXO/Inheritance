Genetic Inheritance Simulation
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
How to Run
Compile the program using gcc:

bash
Copy code
gcc main.c -o inheritance
Run the compiled program:

bash
Copy code
./inheritance
The program will output the family tree of blood types.

Example Output
bash
Copy code
Child (Generation 0): blood type AB
    Parent (Generation 1): blood type AO
        Grandparent (Generation 2): blood type BO
        Grandparent (Generation 2): blood type AA
    Parent (Generation 1): blood type BO
        Grandparent (Generation 2): blood type AB
        Grandparent (Generation 2): blood type OO
Notes
The GENERATIONS constant is fixed at 3. To modify the number of generations, update this constant and adjust the logic accordingly.
The INDENT_LENGTH constant controls the number of spaces used for indentation.
Memory Management
The program dynamically allocates memory for each person using malloc. Ensure all memory is freed by calling free_family after printing the family tree.

Dependencies
C standard libraries: stdio.h, stdlib.h, stdbool.h, time.h.
Known Limitations
The number of generations is fixed at 3 and cannot be changed dynamically during execution.
The blood type simulation does not handle rare alleles or mutations beyond 'A', 'B', and 'O'.****
