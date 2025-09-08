Of course, here is a `readme.md` file based on the provided notebook.

-----

# Forward Chaining Inference Engine

This project provides a Python implementation of a **Forward Chaining algorithm** for propositional logic. It's designed to determine whether a given knowledge base (KB) entails a specific query. The engine can load logical clauses from a file, visualize the knowledge base as a dependency graph, and trace the step-by-step inference process.

-----

## 🚀 Features

  * **Knowledge Base Management**: Loads logical clauses from a simple text file.
  * **Forward Chaining Algorithm**: Implements an efficient forward chaining algorithm to derive new facts.
  * **Step-by-Step Tracing**: Prints a detailed log of the inference process, showing how new symbols are inferred.
  * **Graph Visualization**: Uses `Graphviz` to generate and display a directed graph of the knowledge base, illustrating relationships between premises and conclusions.

-----

## 🧩 Core Components

The project is structured into several key classes that model the components of a logical inference system.

  * `Literal`: Represents a single propositional symbol, which can be positive or negated (e.g., `A` or `-A`).
  * `Clause`: Represents a logical clause as a disjunction of literals, typically in Horn clause form (e.g., `A ∧ B → C`).
  * `KnowledgeBase`: A collection of clauses that represents the domain's facts and rules. It handles loading clauses from a file and building the dependency graph.
  * `State`: Tracks the current state of known symbols during the inference process.
  * `Problem`: Defines the overall problem, containing the knowledge base and the query to be proven.
  * `InferenceEngine`: The main engine that contains the `forward_chaining` method to solve the defined problem.

-----

## 🛠️ How to Use

### 1\. Prerequisites

Make sure you have Python installed, along with the `graphviz` library.

```bash
pip install graphviz
```

You may also need to install the Graphviz command-line tools depending on your operating system.

### 2\. Create a Knowledge Base File

Create a text file (e.g., `data.txt`) with your logical clauses. Each line represents one clause. Premises are negated literals, and the conclusion is a positive literal.

**Format:**

  * Facts are single positive literals (e.g., `D`).
  * Rules are space-separated literals (e.g., `-A -B C` which represents $A \\land B \\rightarrow C$).

**Example `data.txt`:**

```
-b -c a
-d b
-e -f c
-g -h d
-a e
d
```

### 3\. Run the Engine

Use the `main` function to load the knowledge base, define a query, and run the inference engine.


### 4\. Interpret the Output

The script will print:

1.  The rules and facts in the knowledge base.
2.  A visualization of the dependency graph.
3.  A step-by-step trace of the forward chaining process.
4.  The final result: `True` if the query can be entailed, otherwise `False`.
