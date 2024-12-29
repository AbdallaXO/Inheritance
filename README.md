Certainly! Below is an example of how you can document your code using GitHub-flavored Markdown. This documentation will explain the purpose of the program, describe each function, and provide an overview of the code structure.

---

# Family Tree Simulation (Blood Type Inheritance)

This C program simulates the inheritance of blood type alleles over three generations. It uses a recursive approach to generate a family tree, where each person has two parents, and each parent has a random blood type allele (`A`, `B`, or `O`). The child inherits one allele from each parent.

## Overview

The program creates a family tree with three generations and prints the blood type of each person in the tree. It uses a recursive approach to generate family members and their respective alleles, where each generation is derived from the previous one.

### Features:
- Creates a family with three generations.
- Randomly assigns blood type alleles to individuals.
- Prints the family tree with appropriate indentation.
- Frees dynamically allocated memory for all family members.

## Table of Contents

- [Functions](#functions)
  - [create_family](#create_family)
  - [print_family](#print_family)
  - [free_family](#free_family)
  - [random_allele](#random_allele)
- [How to Compile](#how-to-compile)
- [Example Output](#example-output)
- [License](#license)

---

## Functions

### `create_family(int generations)`

Creates a new individual with a specified number of generations. Each individual has two parents, and the alleles are inherited from these parents. This function is called recursively until the base case is reached, where no more generations remain.

**Parameters:**
- `generations`: The number of generations to create. The function will stop when `generations` is equal to 1.

**Returns:**
- A pointer to a newly created `person` struct.

**Notes:**
- If the number of generations is greater than 1, the function recursively creates two parents for the individual.
- If there are no more generations, the function assigns random alleles to the individual.

### `print_family(person *p, int generation)`

Prints the family tree starting from the given person `p` and indents the output based on the generation level.

**Parameters:**
- `p`: A pointer to the `person` whose family tree needs to be printed.
- `generation`: The current generation level. This is used to format the output and determine the level of indentation.

**Returns:**
- None. The function prints information to the console.

**Notes:**
- Prints the person’s blood type along with the generation information.
- Recursively prints the family tree, starting with the person's parents.

### `free_family(person *p)`

Recursively frees the memory allocated for the person `p` and their ancestors (parents).

**Parameters:**
- `p`: A pointer to the `person` whose memory needs to be freed.

**Returns:**
- None.

**Notes:**
- The function ensures that all memory for the family tree is properly freed after use.

### `random_allele()`

Generates a random blood type allele (`A`, `B`, or `O`).

**Parameters:**
- None.

**Returns:**
- A randomly chosen character representing the blood type allele: `'A'`, `'B'`, or `'O'`.

**Notes:**
- This function is used to assign blood type alleles to individuals in the family tree.

---

## How to Compile

1. Save the code to a file, for example `family_tree.c`.
2. Open a terminal or command prompt.
3. Compile the code using the following command:

   ```bash
   gcc -o family_tree family_tree.c
   ```

4. Run the compiled program:

   ```bash
   ./family_tree
   ```

---

## Example Output

Here’s an example of what the output might look like when you run the program:

```bash
Child (Generation 0): blood type AO
    Parent (Generation 1): blood type AB
        Grandparent (Generation 2): blood type AB
            Great-Grandparent (Generation 3): blood type AA
            Great-Grandparent (Generation 3): blood type OO
        Grandparent (Generation 2): blood type OO
            Great-Grandparent (Generation 3): blood type AB
            Great-Grandparent (Generation 3): blood type BB
    Parent (Generation 1): blood type OO
        Grandparent (Generation 2): blood type AO
            Great-Grandparent (Generation 3): blood type AB
            Great-Grandparent (Generation 3): blood type OO
        Grandparent (Generation 2): blood type AB
            Great-Grandparent (Generation 3): blood type AB
            Great-Grandparent (Generation 3): blood type OO
```

Each generation is printed with an appropriate label (`Child`, `Parent`, `Grandparent`, etc.), and the blood types of each family member are shown.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

Feel free to adjust the sections or add more details to suit your needs. This documentation provides a clear, structured overview for anyone looking to understand or contribute to your project.
