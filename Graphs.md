# Notes on Graphs and Dynamic Programming

## Graphs

### What is a Graph?
- A **graph** is made of:
  - **Nodes (or vertices)**: Points in the graph.
  - **Edges**: Connections between nodes.
- Graphs represent relationships, like cities connected by roads or friends in a social network.

---

### Weighted vs Unweighted Graphs

#### Weighted Graphs
- **Definition**: Edges have weights or costs.
- **Examples**:
  - Roads where weights are distances.
  - Networks where weights are bandwidths or latencies.
- **Representation**:
  - **Matrix**: A table where numbers show edge weights. If no edge exists, use `Infinity` or `0`.
  - **List**: Each node lists its neighbors and edge weights.

#### Unweighted Graphs
- **Definition**: Edges show only connections, no weights.
- **Examples**:
  - Friend connections in social networks.
  - Maps with just paths, no distances.
- **Representation**:
  - **Matrix**: Use `1` for connections, `0` otherwise.
  - **List**: Each node lists its neighbors.

---

### Directed vs Undirected Graphs

#### Directed Graphs
- **Definition**: Edges have directions (arrows).
- **Example**: A one-way road, `(A → B)`.
- **Properties**:
  - Not all connections are bidirectional.

#### Undirected Graphs
- **Definition**: Edges are bidirectional `(A — B)`.
- **Example**: Two-way roads or mutual friendships.

---

## Dynamic Programming (DP)

### What is Dynamic Programming?
- **Definition**: A method to solve problems by breaking them into smaller overlapping subproblems and solving each only once.
- **Key Idea**: Avoid solving the same problem multiple times by storing results.

---

### Steps to Solve a DP Problem
1. **Break the Problem**:
   - Define how it splits into smaller problems.
   - Example: Fibonacci numbers split into smaller Fibonacci calculations.
2. **Base Cases**:
   - Smallest subproblems with direct solutions.
   - Example: `Fib(0) = 0`, `Fib(1) = 1`.
3. **Recurrence Relation**:
   - Formula to connect solutions of subproblems.
   - Example: `Fib(n) = Fib(n-1) + Fib(n-2)`.
4. **Store Results**:
   - Use an array or object to save subproblem results.

---

### Dynamic Programming Approaches

#### Top-Down (Memoization)
- Recursive with caching.
- Example:
  ```javascript
  function fib(n, memo = {}) {
      if (n <= 1) return n;
      if (memo[n] !== undefined) return memo[n];
      memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
      return memo[n];
  }
  console.log(fib(10)); // Output: 55
