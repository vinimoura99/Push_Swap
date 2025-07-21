# 📦 push_swap

The `push_swap` project is an algorithmic challenge from the 42 curriculum that focuses on **sorting a stack of integers with the fewest possible operations**, using only a limited set of instructions and **two stacks (A and B)**.

---

## 📚 Table of Contents

- [About](#about)
- [Objectives](#objectives)
- [Allowed Instructions](#allowed-instructions)
- [Usage](#usage)
- [Examples](#examples)
- [Algorithm Overview](#algorithm-overview)
- [Performance](#performance)
- [Bonus Features](#bonus-features)
- [Project Structure](#project-structure)
- [Resources](#resources)
- [Author](#author)

---

## 📌 About

> **"Sort data using two stacks and a limited set of operations, with as few moves as possible."**

This project tests your knowledge of:
- Data structures (linked lists or arrays)
- Sorting algorithms
- Time and space complexity
- Memory management in C
- Writing clean and modular code

---

## 🎯 Objectives

- Take a list of integers as input.
- Sort the numbers using a restricted set of operations.
- Minimize the number of operations.
- Handle edge cases (duplicates, invalid inputs, already sorted lists).

---

## ⚙️ Allowed Instructions

| Command | Description                                 |
|--------|---------------------------------------------|
| `sa`   | swap the first two elements of stack A       |
| `sb`   | swap the first two elements of stack B       |
| `ss`   | `sa` and `sb` at the same time               |
| `pa`   | push the top of stack B to stack A           |
| `pb`   | push the top of stack A to stack B           |
| `ra`   | rotate stack A up (first becomes last)       |
| `rb`   | rotate stack B up                            |
| `rr`   | `ra` and `rb` at the same time               |
| `rra`  | reverse rotate stack A (last becomes first)  |
| `rrb`  | reverse rotate stack B                       |
| `rrr`  | `rra` and `rrb` at the same time             |

---

## 🚀 Usage

### 🛠 Compilation

```bash
make

📥 Run the program

./push_swap [list of integers]

💡 Example

./push_swap 3 2 1

Output:

sa
rra

To check if the result is correct, you can use the provided checker program:

./checker 3 2 1

Paste the output from push_swap and press Enter:

sa
rra

Returns:

OK

📊 Examples
Input	Output Steps
2 1 3	sa
3 2 1	sa → rra
5 1 4 2 3	pb → pb → sa → ...
100 random nums	~700–900 steps (goal < 1500)
🧠 Algorithm Overview
For small stacks:

    2 elements: simple sa if needed.

    3 elements: hardcoded minimal cases (max 2 ops).

    5 elements: push two smallest to B, sort 3 in A, push back.

For large stacks:

    Indexing: convert all numbers to 0-based indexes for normalization.

    Radix sort: binary representation sorting using bitwise logic.

        Time complexity: O(n log n)

        Space complexity: O(n)

🏁 Performance
Size of Input	Target Max Operations
3	≤ 3
5	≤ 12
100	≤ 700
500	≤ 5500

My implementation reaches:

    ~500–700 ops for 100 elements

    ~4000–5200 ops for 500 elements (average)

You can validate using:

ARG=$(seq 1 100 | shuf); ./push_swap $ARG | wc -l

🧱 Project Structure

push_swap/
├── Makefile
├── push_swap.c        # Main sorting logic
├── checker.c          # (Optional) Checker program
├── parsing.c          # Input validation and parsing
├── stack_ops.c        # Swap, push, rotate functions
├── sort_small.c       # Sorting logic for <= 5 elements
├── radix_sort.c       # Radix algorithm for big numbers
├── utils.c            # Utility functions (indexing, printing)
├── libft/             # Custom C library (libft)
└── include/
    └── push_swap.h

📚 Resources

    42 Subject PDF

    Push_swap Visualizer

    Sorting algorithm reference

👤 Author

    Vinícius Moura
    🛠️ Developer @ 42 Porto
    🎨 Coder & Artist
    💻 Focused on low-level systems, performance, and clean code.
