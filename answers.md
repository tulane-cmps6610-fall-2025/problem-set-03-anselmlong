# CMPS 6610 Problem Set 03
## Answers

**Name:** Anselm Long


Place all written answers from `problemset-03.md` here for easier grading.


- **1b.** Work and span of `isearch` using `iterate`:
  - **Work**: O(n) - We visit each element in the list exactly once
  - **Span**: O(n) - The iterate function processes elements sequentially, so the span is linear in the size of the input


- **1d.** Work and span of `rsearch` using `reduce`:
  - **Work**: O(n) - We need to examine each element once to determine if it equals x, plus the reduce operation which is O(n)
  - **Span**: O(log n) - The reduce function uses a divide-and-conquer approach, creating a binary tree of depth log n


- **1e.** Work and span using `ureduce`:
  - **Work**: O(n^(log₃2)) ≈ O(n^0.63) - The recurrence is T(n) = 2T(n/3) + O(1), which by the master theorem gives us this complexity
  - **Span**: O(log₃ n) - The depth of recursion is determined by dividing by 3 at each level


- **2a.** Deduplication algorithm:
  **SPARC specification for `dedup(A)`:**
  - **Specification**: Given a list A of n elements, return a list containing only the distinct elements of A in the order of their first appearance
  - **Algorithm**: Use a set to track seen elements and filter/map operations
    1. Initialize empty set S and empty result list R
    2. For each element e in A: if e not in S, add e to S and R
    3. Return R
  - **Work**: O(n) - Single pass through the list with O(1) set operations
  - **Span**: O(n) - Sequential processing required to preserve order


- **2b.** Multi-list deduplication:
  **SPARC specification for `multi-dedup(A₀, ..., Aₘ)`:**
  - **Specification**: Given m+1 lists each with n elements, return the set of all distinct elements across all lists
  - **Algorithm**: 
    1. Concatenate all lists: B = A₀ + A₁ + ... + Aₘ
    2. Apply dedup(B)
  - **Work**: O(mn) - Processing (m+1)n total elements
  - **Span**: O(mn) - Sequential processing for order preservation
  - **Comparison**: Same asymptotic complexity as single dedup applied to concatenated input


- **2c.** Sequence operations usefulness:
  - **Map**: Useful for transforming elements
  - **Filter**: Useful for removing duplicates once identified
  - **Reduce**: Less directly useful since we need to preserve order and intermediate state
  - **Scan**: Could be useful for maintaining running state of seen elements, but complex to implement efficiently for deduplication


- **3b.** Work and span of iterative parentheses matching:
  - **Work**: W(n) = O(n) - Single pass through the input list
  - **Span**: S(n) = O(n) - Sequential processing with iterate


- **3d.** Work and span of scan-based solution:
  - **Work**: W(n) = O(n) - Map operation is O(n), scan is O(n), reduce is O(n)
  - **Span**: S(n) = O(log n) - Efficient scan implementation has logarithmic span, map can be done in parallel O(1), reduce is O(log n)


- **3f.** Work and span of divide-and-conquer solution:
  - **Work**: W(n) = 2W(n/2) + O(1) = O(n) - Two recursive calls on half-sized problems plus constant merge time
  - **Span**: S(n) = S(n/2) + O(1) = O(log n) - Recursive calls can be done in parallel, merge takes constant time




