# 60-DSA-Problems-in-C

<br>
Description:
<br>
🚀 Master Data Structures in C! This repository contains 60 essential problems covering Arrays, Linked Lists, and Stacks, each with detailed explanations, pseudocode, C implementations, and complexity analysis. Ideal for DSA preparation, coding interviews, and competitive programming.

📌 Content Outline:
✅ Introduction – Overview of Arrays, Linked Lists, and Stacks
✅ Arrays – 20 problems with solutions & optimizations
✅ Linked Lists – 20 problems with step-by-step explanations
✅ Stacks – 20 problems with real-world applications
✅ Conclusion – Summary and C-specific tips

💡 Why Use This Repo?
🔹 Strengthen your DSA fundamentals in C
🔹 Learn efficient problem-solving techniques
🔹 Get ready for technical interviews & coding contests


<br>
I decided to include *only pseudocode* to keep the focus on **problem-solving and algorithmic thinking** rather than just syntax. Pseudocode is **language-agnostic**, allowing anyone to *implement solutions in any programming language* while mastering **core logic, efficiency, and DSA concepts**.  

### 🔥 The Power of Pseudocode:  
✅ **Enhances problem-solving skills** by focusing on logic  
✅ **Easy to understand & adapt** to any programming language  
✅ **Interview-friendly**—helps break down problems efficiently  
✅ **Improves clarity** without syntax distractions  

By mastering pseudocode, you gain the ability to **think like a problem solver**, not just a coder! 🚀
<br>


# Comprehensive Notes on Array, Linked List, and Stack Problems in C

## Introduction

Data structures form the backbone of efficient algorithm design and problem-solving in computer science. Among the foundational data structures, Arrays, Linked Lists, and Stacks stand out due to their versatility and frequent use in both academic exercises and real-world applications. This document aims to provide a comprehensive guide to mastering these data structures through 60 essential problems—20 for each—implemented in the C programming language. Each problem is accompanied by a detailed description, a step-by-step approach, pseudocode, complexity analysis, and practical notes, making this a valuable resource for students, programmers, and enthusiasts preparing for coding interviews, competitive programming, or academic pursuits.

### Arrays: The Static Contiguous Workhorse

An Array is a fundamental data structure consisting of a fixed-size, contiguous block of memory that stores elements of the same type. Its simplicity belies its power: arrays offer O(1) random access via indices, making them ideal for scenarios where quick lookups are paramount. However, their static size and the O(n) cost of insertions or deletions due to shifting elements present challenges that many problems aim to address. From reversing an array in-place to finding maximum subarray sums with Kadane’s Algorithm, the problems in this section explore both basic manipulations and advanced optimization techniques. Arrays are ubiquitous—used in everything from image processing (pixel grids) to database indexing—making their mastery essential.

### Linked Lists: The Dynamic Chain

A Linked List is a dynamic data structure composed of nodes, each containing data and a pointer to the next node, forming a linear sequence that can grow or shrink as needed. Unlike arrays, linked lists excel at insertions and deletions (O(1) when the position is known), but their O(n) access time due to sequential traversal poses unique challenges. The problems here range from reversing a list iteratively to handling complex scenarios like cloning lists with random pointers or detecting cycles using Floyd’s algorithm. Linked lists are critical in applications requiring frequent reordering (e.g., memory allocation in operating systems) or where size unpredictability rules out arrays, such as in some graph representations.

### Stacks: The LIFO Specialist

A Stack is a linear data structure adhering to the Last In, First Out (LIFO) principle, where elements are added (pushed) and removed (popped) from the same end, known as the top. Stacks can be implemented using arrays or linked lists, offering O(1) push and pop operations in both cases, though array-based stacks have a fixed capacity while linked-list implementations are dynamic. This section’s problems leverage the stack’s natural fit for tasks involving order and reversal, such as checking balanced parentheses, evaluating postfix expressions, or solving the Tower of Hanoi puzzle. Stacks underpin many algorithms—think undo mechanisms in software, recursion management in compilers, or even browser history navigation.

### Purpose and Scope

This note serves as a practical cheat sheet and learning tool, bridging theory and implementation in C. Each data structure section contains 20 carefully selected problems that span a spectrum of difficulty—from foundational (e.g., reversing an array) to intermediate (e.g., trapping rain water) to conceptually rich (e.g., sorting a stack). The C language is chosen for its low-level control and proximity to hardware, which forces a deep understanding of memory management (e.g., pointers in linked lists) and efficiency trade-offs (e.g., array bounds). For each problem, we provide:

- **Description**: A clear explanation of the task and its significance.
- **Approach**: A detailed strategy to solve it efficiently.
- **Pseudocode**: A language-agnostic algorithm for clarity.
- **Complexity Analysis**: Time and space costs to evaluate trade-offs.
- **Notes**: Tips, edge cases, and C-specific considerations.

### How to Use This Document

Readers can approach this note linearly, studying each data structure in sequence, or selectively, diving into specific problems relevant to their needs. The pseudocode is designed to be easily translatable into C, and the notes highlight pitfalls like memory leaks or overflow—crucial in a language without automatic garbage collection. Beginners might start with simpler problems (e.g., “Find Maximum/Minimum” for arrays), while advanced learners can tackle challenges like “Largest Rectangle in Histogram” for stacks. Combined, these 60 problems offer a robust foundation for understanding and applying Arrays, Linked Lists, and Stacks in diverse contexts.

### Getting Started

The journey begins with Arrays, exploring their static yet powerful nature, followed by Linked Lists with their dynamic flexibility, and concludes with Stacks, showcasing LIFO’s unique strengths. Each section builds on core concepts while introducing techniques like two-pointer methods, recursion, and in-place operations—all tailored for C’s explicit memory model. Let’s dive in and unravel the intricacies of these data structures through hands-on problem-solving.

---

### Full Content Outline Recap

- **Introduction**: Done above (1-2 pages).
- **Array Section**: 20 problems (20-30 pages).
- **Linked List Section**: 20 problems (20-30 pages).
- **Stack Section**: 20 problems (20-30 pages).
- **Conclusion**: Summary and C tips (1-2 pages).

# Comprehensive Notes on Array, Linked List, and Stack Problems in C

## Array Section

This section explores 20 essential problems related to Arrays, a static, contiguous data structure offering O(1) access but O(n) for insertions/deletions. Each problem is presented with a detailed description, a step-by-step approach, pseudocode, complexity analysis, and practical notes tailored for C implementation. We begin with the first five problems, covering foundational operations and optimization techniques.

---

### 1. Reverse an Array

#### Description

The task is to reverse the order of elements in an array in-place, transforming an input like `[1, 2, 3, 4, 5]` into `[5, 4, 3, 2, 1]`. This problem tests basic array manipulation skills and is a building block for more complex algorithms, such as array rotations or palindrome checks. The reversal must occur without using additional array storage, emphasizing space efficiency—a common requirement in low-memory environments like embedded systems.

#### Approach

- Use two pointers: one starting at the beginning (`left`) and one at the end (`right`).
- Swap elements at `left` and `right`, then move `left` inward and `right` outward.
- Continue until the pointers meet or cross, ensuring all elements are reversed.
- This in-place method leverages the array’s existing memory, avoiding extra space.

#### Pseudocode

```
FUNCTION reverseArray(arr, n)
    SET left = 0
    SET right = n - 1

    WHILE left < right
        SWAP(arr[left], arr[right])
        INCREMENT left
        DECREMENT right
    END WHILE

    RETURN arr
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n/2) = O(n) – Each element is visited once during the swap process.
- **Space Complexity**: O(1) – Only two pointers and a temporary variable for swapping, no extra array.

#### Notes

- **Edge Cases**: Single element array (n=1) needs no change; empty array (n=0) is trivially reversed.
- **C-Specific Tip**: Use a temporary variable for swapping (e.g., `int temp = arr[left]; arr[left] = arr[right]; arr[right] = temp;`) since C lacks built-in swap.
- **Applications**: Useful in preprocessing for algorithms like string reversal or symmetry checks.

---

### 2. Find Maximum/Minimum

#### Description

Given an array of integers, identify both the maximum and minimum elements, e.g., for `[4, 2, 9, 7, 5, 6]`, return `9` (max) and `2` (min). This problem is fundamental for statistical analysis, range queries, or initializing bounds in other algorithms. The goal is to compute both values efficiently in a single pass, minimizing iterations—a practical concern in performance-sensitive applications.

#### Approach

- Initialize `max` and `min` with the first element of the array.
- Iterate through the array once, updating `max` if a larger element is found and `min` if a smaller one is encountered.
- Return the pair after the traversal, achieving efficiency by avoiding multiple passes.

#### Pseudocode

```
FUNCTION findMaxMin(arr, n)
    IF n == 0 THEN RETURN (NULL, NULL)  // Empty array

    SET max = arr[0]
    SET min = arr[0]

    FOR i = 1 TO n-1
        IF arr[i] > max THEN
            max = arr[i]
        END IF
        IF arr[i] < min THEN
            min = arr[i]
        END IF
    END FOR

    RETURN (max, min)
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the array.
- **Space Complexity**: O(1) – Only two variables, regardless of array size.

#### Notes

- **Edge Cases**: Empty array requires special handling (e.g., return sentinel values or error); single element makes max = min.
- **C-Specific Tip**: Use a struct or pair of pointers to return both values (e.g., `struct Result {int max; int min;};`).
- **Optimization**: Pairwise comparison (compare adjacent elements) can reduce comparisons to ~3n/2, though it complicates code.

---

### 3. Rotate Array

#### Description

Rotate an array by k positions to the right (or left), e.g., for `[1, 2, 3, 4, 5]` and k=2, output `[4, 5, 1, 2, 3]`. This problem simulates cyclic shifts, common in scheduling, circular buffers, or data stream processing. The challenge is to perform the rotation efficiently in-place, avoiding the O(n\*k) naive approach of shifting one position k times.

#### Approach

- Use the reversal algorithm:
  1. Reverse the entire array.
  2. Reverse the first k elements.
  3. Reverse the remaining n-k elements.
- Normalize k (k %= n) to handle cases where k > n.
- This method cleverly reorders elements in-place using O(n) time.

#### Pseudocode

```
FUNCTION reverse(arr, start, end)
    WHILE start < end
        SWAP(arr[start], arr[end])
        INCREMENT start
        DECREMENT end
    END WHILE
END FUNCTION

FUNCTION rotateArray(arr, n, k)
    k = k % n  // Normalize k
    IF k < 0 THEN k = k + n  // Handle negative k

    reverse(arr, 0, n-1)      // Reverse all
    reverse(arr, 0, k-1)      // Reverse first k
    reverse(arr, k, n-1)      // Reverse remaining
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Three reversals, each O(n/2) or O(n), total O(n).
- **Space Complexity**: O(1) – In-place using only pointers.

#### Notes

- **Edge Cases**: k=0 or k=n leaves array unchanged; empty array needs no action.
- **C-Specific Tip**: Pass array by pointer (`int *arr`) and ensure bounds checking in reverse function.
- **Alternative**: Juggling algorithm or extra array, but reversal is simplest for in-place.

---

### 4. Two Sum

#### Description

Find two elements in an array that add up to a given target, e.g., for `[2, 7, 11, 15]` and target=9, return indices `[0, 1]` (2 + 7 = 9). This classic problem tests lookup efficiency and is foundational for hash table usage, appearing in coding interviews and pairing problems like resource allocation. Assume each input has exactly one solution.

#### Approach

- Use a hash table to store elements and their indices.
- For each element `arr[i]`, compute `complement = target - arr[i]`.
- If `complement` exists in the hash table, return its index and i.
- Otherwise, add `arr[i]` and its index to the hash table.
- This trades space for time, achieving O(n) efficiency.

#### Pseudocode

```
FUNCTION twoSum(arr, n, target)
    CREATE hashTable  // Key: value, Value: index

    FOR i = 0 TO n-1
        SET complement = target - arr[i]
        IF hashTable contains complement THEN
            RETURN (hashTable[complement], i)
        END IF
        hashTable[arr[i]] = i
    END FOR

    RETURN (-1, -1)  // No solution
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass with O(1) hash operations.
- **Space Complexity**: O(n) – Hash table stores up to n elements.

#### Notes

- **Edge Cases**: No solution (return invalid indices); target=0 with duplicates needs care.
- **C-Specific Tip**: Implement hash table with an array or linked list (e.g., `<stdlib.h>` malloc for dynamic allocation).
- **Alternative**: Sort and use two pointers (O(n log n)), but loses original indices.

---

### 5. Remove Duplicates

#### Description

Remove duplicates from a sorted array in-place and return the new length, e.g., `[1, 1, 2, 3, 3]` becomes `[1, 2, 3]` with length 3. This problem optimizes storage in sorted datasets, common in database preprocessing or deduplication tasks. The array must be modified such that unique elements appear at the start, and the rest can be ignored.

#### Approach

- Use two pointers: `write` (position for next unique element) and `read` (scans array).
- If `arr[read]` differs from `arr[write-1]`, copy it to `arr[write]` and increment `write`.
- Continue until `read` reaches the end, returning `write` as the new length.
- Since the array is sorted, duplicates are adjacent, simplifying the logic.

#### Pseudocode

```
FUNCTION removeDuplicates(arr, n)
    IF n <= 1 THEN RETURN n

    SET write = 1
    FOR read = 1 TO n-1
        IF arr[read] != arr[read-1] THEN
            arr[write] = arr[read]
            INCREMENT write
        END IF
    END FOR

    RETURN write
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the array.
- **Space Complexity**: O(1) – In-place, no extra space.

#### Notes

- **Edge Cases**: Empty or single-element array returns n; all duplicates (e.g., `[1, 1, 1]`) returns 1.
- **C-Specific Tip**: Array is passed by pointer, so modifications persist; ensure input is sorted.
- **Variation**: Unsorted array requires sorting first (O(n log n)) or hash table (O(n) space).

---

# Progress and Next Steps

### Current State

- **Introduction**: Completed (previous response, 1-2 pages).
- **Array Section**: First 5 of 20 problems detailed here (~5-7 pages when formatted).
- **Remaining**: 15 Array problems, 20 Linked List problems, 20 Stack problems, Conclusion.

#

### 6. Merge Two Sorted Arrays

#### Description

Given two sorted arrays, merge them into a single sorted array, e.g., merging `[1, 3, 5]` and `[2, 4, 6]` results in `[1, 2, 3, 4, 5, 6]`. This problem mirrors the merge step of merge sort and is vital in scenarios like combining sorted datasets (e.g., database query results) or preparing data for further processing. The challenge often includes constraints, such as merging into an existing array with sufficient space or creating a new one, but here we’ll assume a new array is allocated.

#### Approach

- Use two pointers, one for each array (`p1` for first, `p2` for second).
- Compare elements at `p1` and `p2`, adding the smaller to the result array and advancing the corresponding pointer.
- Once one array is exhausted, append the remaining elements from the other.
- This leverages the sorted property for a linear-time merge.

#### Pseudocode

```
FUNCTION mergeSortedArrays(arr1, n1, arr2, n2)
    CREATE result[n1 + n2]
    SET p1 = 0  // Pointer for arr1
    SET p2 = 0  // Pointer for arr2
    SET i = 0   // Index for result

    WHILE p1 < n1 AND p2 < n2
        IF arr1[p1] <= arr2[p2] THEN
            result[i] = arr1[p1]
            INCREMENT p1
        ELSE
            result[i] = arr2[p2]
            INCREMENT p2
        END IF
        INCREMENT i
    END WHILE

    WHILE p1 < n1
        result[i] = arr1[p1]
        INCREMENT p1
        INCREMENT i
    END WHILE

    WHILE p2 < n2
        result[i] = arr2[p2]
        INCREMENT p2
        INCREMENT i
    END WHILE

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n1 + n2) – Single pass through both arrays.
- **Space Complexity**: O(n1 + n2) – New array to store the result.

#### Notes

- **Edge Cases**: One or both arrays empty (append the non-empty one); arrays of different sizes handled naturally.
- **C-Specific Tip**: Dynamically allocate result array with `malloc((n1 + n2) * sizeof(int))` and free it later to avoid stack overflow.
- **Variation**: If merging into arr1 with extra space, adjust pointers to fill from the end (O(1) space).

---

### 7. Kadane’s Algorithm

#### Description

Find the maximum sum of a contiguous subarray within an array of integers, e.g., for `[-2, 1, -3, 4, -1, 2, 1, -5, 4]`, the maximum sum is `6` from `[4, -1, 2, 1]`. This dynamic programming problem is widely applicable in financial analysis (e.g., maximum profit sequences) and signal processing, requiring an efficient solution to avoid brute-force O(n²) enumeration of all subarrays.

#### Approach

- Track two variables: `curr_max` (max sum ending at current position) and `max_so_far` (global max sum).
- For each element, decide to start a new subarray (if `curr_max` is negative) or extend it by adding the element.
- Update `max_so_far` when `curr_max` exceeds it, completing the array in one pass.

#### Pseudocode

```
FUNCTION maxSubarraySum(arr, n)
    SET max_so_far = arr[0]
    SET curr_max = arr[0]

    FOR i = 1 TO n-1
        curr_max = MAX(arr[i], curr_max + arr[i])
        max_so_far = MAX(max_so_far, curr_max)
    END FOR

    RETURN max_so_far
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the array.
- **Space Complexity**: O(1) – Only two variables used.

#### Notes

- **Edge Cases**: All negative numbers (returns least negative); single element (returns itself).
- **C-Specific Tip**: Initialize with `arr[0]` not `INT_MIN` to handle all-negative cases correctly.
- **Extension**: Track start/end indices by storing them when updating `max_so_far`.

---

### 8. Find Missing Number

#### Description

Given an array of integers from 1 to n with one number missing, find the missing number, e.g., `[3, 1, 4, 5]` (n=5) returns `2`. This problem tests mathematical reasoning and is useful in error detection or sequence validation, often constrained to O(n) time and minimal space.

#### Approach

- Calculate the expected sum of numbers from 1 to n using the formula `n * (n + 1) / 2`.
- Compute the actual sum of the array.
- The difference between expected and actual sums is the missing number.
- Alternatively, XOR all numbers and indices to cancel pairs, leaving the missing value.

#### Pseudocode

```
FUNCTION findMissingNumber(arr, n)
    SET expected_sum = n * (n + 1) / 2
    SET actual_sum = 0

    FOR i = 0 TO n-1
        actual_sum = actual_sum + arr[i]
    END FOR

    RETURN expected_sum - actual_sum
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – One pass to compute the sum.
- **Space Complexity**: O(1) – Only two variables.

#### Notes

- **Edge Cases**: n=1 with [1] (no missing, handle explicitly); overflow risk with large n.
- **C-Specific Tip**: Use `long` for sums to avoid integer overflow (e.g., `long expected_sum`).
- **XOR Alternative**: XOR method avoids overflow but assumes array indices align with 0 to n-1.

---

### 9. Move Zeroes

#### Description

Move all zeros in an array to the end while maintaining the relative order of non-zero elements, e.g., `[0, 1, 0, 3, 12]` becomes `[1, 3, 12, 0, 0]`. This in-place problem is practical for data cleaning or formatting, such as preparing arrays for sparse matrix operations, requiring minimal extra space.

#### Approach

- Use two pointers: `non_zero_pos` tracks the next position for a non-zero element.
- Iterate through the array, placing non-zero elements at `non_zero_pos` and incrementing it.
- After placing all non-zeros, fill remaining positions with zeros.
- This ensures stability (order preserved) and in-place operation.

#### Pseudocode

```
FUNCTION moveZeroes(arr, n)
    SET non_zero_pos = 0

    // Move non-zeros to front
    FOR i = 0 TO n-1
        IF arr[i] != 0 THEN
            arr[non_zero_pos] = arr[i]
            INCREMENT non_zero_pos
        END IF
    END FOR

    // Fill rest with zeros
    WHILE non_zero_pos < n
        arr[non_zero_pos] = 0
        INCREMENT non_zero_pos
    END WHILE

    RETURN arr
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Two passes (one implicit in the loop structure).
- **Space Complexity**: O(1) – In-place with a single pointer.

#### Notes

- **Edge Cases**: All zeros or no zeros (works naturally); empty array (no action).
- **C-Specific Tip**: Array modifications persist via pointer; no need for return in practice.
- **Alternative**: Swap non-zeros with zeros, but may disrupt order unless careful.

---

### 10. Search in Rotated Sorted Array

#### Description

Search for a target element in a sorted array that has been rotated at an unknown pivot, e.g., `[4, 5, 6, 7, 0, 1, 2]` (originally `[0, 1, 2, 4, 5, 6, 7]`) with target `0` returns index `4`. This problem tests binary search adaptation, common in rotated logs or circular data structures, requiring O(log n) time.

#### Approach

- Modify binary search to handle rotation:
  - Compute mid-point and check which half is sorted (left or right of mid).
  - If left is sorted (`arr[left] <= arr[mid]`), check if target lies in that range; adjust pointers.
  - Otherwise, right is sorted, check target there.
- Repeat until target is found or search space is exhausted.

#### Pseudocode

```
FUNCTION searchRotated(arr, n, target)
    SET left = 0
    SET right = n - 1

    WHILE left <= right
        SET mid = (left + right) / 2
        IF arr[mid] == target THEN
            RETURN mid
        END IF

        // Check if left half is sorted
        IF arr[left] <= arr[mid] THEN
            IF arr[left] <= target AND target < arr[mid] THEN
                right = mid - 1
            ELSE
                left = mid + 1
            END IF
        // Right half must be sorted
        ELSE
            IF arr[mid] < target AND target <= arr[right] THEN
                left = mid + 1
            ELSE
                right = mid - 1
            END IF
        END IF
    END WHILE

    RETURN -1  // Not found
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(log n) – Binary search halves the search space each step.
- **Space Complexity**: O(1) – Only three pointers.

#### Notes

- **Edge Cases**: Unrotated array (works as standard binary search); target not present (-1).
- **C-Specific Tip**: Avoid overflow in mid calculation with `mid = left + (right - left) / 2`.
- **Assumption**: No duplicates; with duplicates, O(n) worst case due to ambiguity.

---

# Progress and Next Steps

### Current State

- **Introduction**: Completed (1-2 pages).
- **Array Section**:
  - Problems 1-5: Done (previous response, ~5-7 pages).
  - Problems 6-10: Done here (~5-7 pages).
  - Remaining: 10 Array problems (11-20).
- **Next Sections**: Linked List (20), Stack (20), Conclusion.

### 11. Product Except Self

#### Description

Given an array of integers, compute a new array where each element is the product of all other elements in the original array, e.g., for `[1, 2, 3, 4]`, return `[24, 12, 8, 6]` (24 = 2*3*4, 12 = 1*3*4, etc.). This problem challenges you to avoid division and achieve O(n) time without using extra space beyond the output array, a constraint often seen in coding interviews or signal processing tasks.

#### Approach

- Compute the product of elements to the left of each index in one pass, storing in the result array.
- Compute the product of elements to the right in a second pass, multiplying into the result array.
- Use a single variable to track the running right product, avoiding a separate right array.
- This eliminates division and extra space beyond the output.

#### Pseudocode

```
FUNCTION productExceptSelf(arr, n)
    CREATE result[n]

    // Left products
    result[0] = 1
    FOR i = 1 TO n-1
        result[i] = result[i-1] * arr[i-1]
    END FOR

    // Multiply right products
    SET right_product = 1
    FOR i = n-1 DOWN TO 0
        result[i] = result[i] * right_product
        right_product = right_product * arr[i]
    END FOR

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Two passes through the array.
- **Space Complexity**: O(1) – Excluding the output array, only one variable used.

#### Notes

- **Edge Cases**: Array with zeros (works naturally, others get 0); single element (returns 1).
- **C-Specific Tip**: Use `long` or `long long` for products to handle large values (e.g., `long result[n]`).
- **Constraint**: No division ensures robustness with zeros; brute force O(n²) is impractical.

---

### 12. Trapping Rain Water

#### Description

Given an array representing bar heights, calculate the total water trapped between them after rain, e.g., `[0, 1, 0, 2, 1, 0, 1, 3, 2, 1, 2, 1]` traps 6 units. This problem models real-world scenarios like terrain water retention and tests spatial reasoning, requiring an efficient solution beyond brute-force O(n²) checks for each bar.

#### Approach

- For each bar, water trapped is the minimum of the maximum height to its left and right, minus its height.
- Precompute `left_max` and `right_max` arrays in two passes.
- Sum the water trapped at each position in a final pass.
- This avoids recomputing max heights repeatedly.

#### Pseudocode

```
FUNCTION trapRainWater(arr, n)
    CREATE left_max[n], right_max[n]
    SET water = 0

    // Left maximums
    left_max[0] = arr[0]
    FOR i = 1 TO n-1
        left_max[i] = MAX(left_max[i-1], arr[i])
    END FOR

    // Right maximums
    right_max[n-1] = arr[n-1]
    FOR i = n-2 DOWN TO 0
        right_max[i] = MAX(right_max[i+1], arr[i])
    END FOR

    // Compute water
    FOR i = 0 TO n-1
        water = water + (MIN(left_max[i], right_max[i]) - arr[i])
    END FOR

    RETURN water
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Three passes through the array.
- **Space Complexity**: O(n) – Two auxiliary arrays.

#### Notes

- **Edge Cases**: Single bar or all zeros trap nothing; negative heights invalid (assume non-negative).
- **C-Specific Tip**: Allocate `left_max` and `right_max` dynamically with `malloc` and free them.
- **Optimization**: Two-pointer method reduces space to O(1) but is trickier to implement.

---

### 13. Sort 0s, 1s, 2s

#### Description

Sort an array containing only 0s, 1s, and 2s in a single pass, e.g., `[2, 0, 1, 0, 2, 1]` becomes `[0, 0, 1, 1, 2, 2]`. Known as the Dutch National Flag problem, it’s useful in partitioning tasks or color sorting, requiring an in-place O(n) solution without counting sort’s extra space.

#### Approach

- Use three pointers: `low` (for 0s), `mid` (current element), `high` (for 2s).
- If `mid` is 0, swap with `low`, increment both; if 1, increment `mid`; if 2, swap with `high`, decrement `high`.
- Continue until `mid` exceeds `high`, partitioning the array into 0s, 1s, and 2s.
- This maintains stability within each group.

#### Pseudocode

```
FUNCTION sort012(arr, n)
    SET low = 0
    SET mid = 0
    SET high = n - 1

    WHILE mid <= high
        IF arr[mid] == 0 THEN
            SWAP(arr[low], arr[mid])
            INCREMENT low
            INCREMENT mid
        ELSE IF arr[mid] == 1 THEN
            INCREMENT mid
        ELSE  // arr[mid] == 2
            SWAP(arr[mid], arr[high])
            DECREMENT high
        END IF
    END WHILE

    RETURN arr
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass with constant-time swaps.
- **Space Complexity**: O(1) – In-place with three pointers.

#### Notes

- **Edge Cases**: All same value (e.g., all 1s) works naturally; empty array (no action).
- **C-Specific Tip**: Use explicit swap with temp variable; ensure `mid <= high` to avoid overrun.
- **Generalization**: Extends to k-way partitioning with more pointers.

---

### 14. Find Duplicates

#### Description

Identify all duplicate elements in an array of integers from 1 to n, e.g., `[4, 3, 2, 7, 8, 2, 3, 1]` returns `[2, 3]`. This problem is common in data validation or error checking, often constrained to O(n) time and O(1) space, assuming numbers are within a specific range.

#### Approach

- Use the array as a hash table by marking visited elements.
- For each element `arr[i]`, negate the value at index `abs(arr[i]) - 1`.
- If the value at that index is already negative, `abs(arr[i])` is a duplicate.
- Collect duplicates in a separate list during the process.

#### Pseudocode

```
FUNCTION findDuplicates(arr, n)
    CREATE duplicates  // Dynamic list or array
    FOR i = 0 TO n-1
        SET index = ABS(arr[i]) - 1
        IF arr[index] > 0 THEN
            arr[index] = -arr[index]
        ELSE
            ADD duplicates, ABS(arr[i])
        END IF
    END FOR

    RETURN duplicates
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the array.
- **Space Complexity**: O(1) – Excluding output, modifies input array.

#### Notes

- **Edge Cases**: No duplicates (empty result); assumes 1 to n range.
- **C-Specific Tip**: Restore array if needed by negating again; use `abs()` from `<stdlib.h>`.
- **Alternative**: Hash set (O(n) space) or sorting (O(n log n) time).

---

### 15. Pair with Given Difference

#### Description

Find a pair of elements in an array with a given difference, e.g., for `[5, 20, 3, 2, 50, 80]` and difference `78`, return `[2, 80]`. This problem tests search efficiency and is applicable in matching tasks (e.g., time differences), aiming for O(n log n) or better.

#### Approach

- Sort the array to enable two-pointer search.
- Use `left` and `right` pointers: compute difference `arr[right] - arr[left]`.
- If difference equals target, return pair; if less, increment `right`; if more, increment `left`.
- Continue until a pair is found or pointers cross.

#### Pseudocode

```
FUNCTION pairWithDifference(arr, n, diff)
    SORT(arr, n)  // Ascending order
    SET left = 0
    SET right = 1

    WHILE right < n
        SET current_diff = arr[right] - arr[left]
        IF current_diff == diff THEN
            RETURN (arr[left], arr[right])
        ELSE IF current_diff < diff THEN
            INCREMENT right
        ELSE
            INCREMENT left
            IF left == right THEN
                INCREMENT right
            END IF
        END IF
    END WHILE

    RETURN (-1, -1)  // No pair found
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n log n) – Dominated by sorting.
- **Space Complexity**: O(1) – In-place if sorting modifies input.

#### Notes

- **Edge Cases**: No pair (return invalid); diff=0 needs duplicate check.
- **C-Specific Tip**: Use `qsort` from `<stdlib.h>` with custom comparator.
- **Alternative**: Hash set for O(n) time, O(n) space, checking `x + diff`.

---

### 16. Subarray with Given Sum

#### Description

Given an array of positive integers and a target sum, find a contiguous subarray whose elements sum to the target, e.g., for `[1, 4, 20, 3, 10, 5]` and sum `33`, return start and end indices of `[20, 3, 10]` (20 + 3 + 10 = 33). This problem is common in financial analysis or sequence matching, requiring an efficient solution for large arrays, ideally O(n) for positive numbers.

#### Approach

- Use a sliding window technique since all elements are positive.
- Maintain a window with `start` and `curr_sum`, expanding by incrementing `end` and adding `arr[end]`.
- If `curr_sum` exceeds the target, shrink the window by incrementing `start` and subtracting `arr[start-1]`.
- When `curr_sum` equals the target, return the window boundaries.

#### Pseudocode

```
FUNCTION subarrayWithSum(arr, n, target)
    SET curr_sum = 0
    SET start = 0

    FOR end = 0 TO n-1
        curr_sum = curr_sum + arr[end]

        WHILE curr_sum > target AND start <= end
            curr_sum = curr_sum - arr[start]
            INCREMENT start
        END WHILE

        IF curr_sum == target THEN
            RETURN (start, end)
        END IF
    END FOR

    RETURN (-1, -1)  // No subarray found
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass with `end`, `start` moves at most n times each.
- **Space Complexity**: O(1) – Only two pointers and a sum variable.

#### Notes

- **Edge Cases**: No solution (return invalid indices); target = 0 (check empty subarray).
- **C-Specific Tip**: Use `long` for `curr_sum` to avoid overflow with large sums.
- **Limitation**: Works for positive numbers; negatives require O(n²) or hash-based approach.

---

### 17. Next Greater Element

#### Description

For each element in an array, find the next greater element to its right, returning -1 if none exists, e.g., `[4, 5, 2, 25]` yields `[5, 25, 25, -1]`. This problem is useful in stock price analysis or pattern recognition, often solved efficiently with a stack to avoid O(n²) brute force.

#### Approach

- Use a stack to track elements awaiting their next greater element.
- Traverse the array; for each element, pop stack elements smaller than it, setting them to the current element.
- Push the current element’s index onto the stack.
- After traversal, remaining stack elements get -1.

#### Pseudocode

```
FUNCTION nextGreaterElement(arr, n)
    CREATE stack
    CREATE result[n] = {-1}

    FOR i = 0 TO n-1
        WHILE NOT isEmpty(stack) AND arr[i] > arr[top(stack)]
            SET index = POP(stack)
            result[index] = arr[i]
        END WHILE
        PUSH(stack, i)
    END FOR

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Each element pushed and popped at most once.
- **Space Complexity**: O(n) – Stack and result array.

#### Notes

- **Edge Cases**: Monotonic decreasing array (all -1); single element (-1).
- **C-Specific Tip**: Use array-based stack with index tracking; `malloc` for dynamic result.
- **Variation**: Circular array requires wrapping around (double array or modulo).

---

### 18. Intersection of Two Arrays

#### Description

Find all common elements between two arrays, e.g., `[1, 2, 2, 3]` and `[2, 2, 4]` return `[2, 2]`, preserving duplicates. This problem arises in set operations or database joins, aiming for efficiency beyond O(n\*m) pairwise comparison.

#### Approach

- Sort both arrays to align duplicates.
- Use two pointers to scan arrays, adding elements to the result when they match and advancing the pointer of the smaller value otherwise.
- Continue until one array is exhausted, collecting intersections.

#### Pseudocode

```
FUNCTION intersection(arr1, n1, arr2, n2)
    SORT(arr1, n1)
    SORT(arr2, n2)
    CREATE result  // Dynamic list

    SET i = 0  // Pointer for arr1
    SET j = 0  // Pointer for arr2

    WHILE i < n1 AND j < n2
        IF arr1[i] == arr2[j] THEN
            ADD result, arr1[i]
            INCREMENT i
            INCREMENT j
        ELSE IF arr1[i] < arr2[j] THEN
            INCREMENT i
        ELSE
            INCREMENT j
        END IF
    END WHILE

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n1 log n1 + n2 log n2) – Dominated by sorting.
- **Space Complexity**: O(min(n1, n2)) – Result size bounded by smaller array.

#### Notes

- **Edge Cases**: No common elements (empty result); one empty array (empty result).
- **C-Specific Tip**: Use `qsort` and dynamic array (`realloc`) for result.
- **Alternative**: Hash set (O(n1 + n2) time, O(n1) space) is faster but uses more memory.

---

### 19. Longest Consecutive Sequence

#### Description

Find the length of the longest consecutive sequence in an unsorted array, e.g., `[100, 4, 200, 1, 3, 2]` returns `4` (sequence `[1, 2, 3, 4]`). This problem tests set operations and is applicable in data analysis, aiming for O(n) time despite the need to identify sequences.

#### Approach

- Use a hash set to store all elements.
- For each element, check if it’s the start of a sequence (no `num-1` in set).
- If so, count consecutive numbers (`num+1`, `num+2`, etc.) in the set, tracking the longest.
- This avoids sorting and processes each element efficiently.

#### Pseudocode

```
FUNCTION longestConsecutive(arr, n)
    CREATE hash_set
    FOR i = 0 TO n-1
        INSERT hash_set, arr[i]
    END FOR

    SET max_length = 0
    FOR i = 0 TO n-1
        IF NOT hash_set contains (arr[i] - 1) THEN
            SET curr_num = arr[i]
            SET curr_length = 1
            WHILE hash_set contains (curr_num + 1)
                INCREMENT curr_length
                INCREMENT curr_num
            END WHILE
            max_length = MAX(max_length, curr_length)
        END IF
    END FOR

    RETURN max_length
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Each element inserted and checked once, inner while amortized.
- **Space Complexity**: O(n) – Hash set stores all elements.

#### Notes

- **Edge Cases**: Empty array (0); no sequence (1).
- **C-Specific Tip**: Implement hash set with array or linked list; `malloc` for dynamic allocation.
- **Optimization**: Sorting (O(n log n)) is simpler but slower.

---

### 20. Majority Element

#### Description

Find the element appearing more than n/2 times in an array, e.g., `[3, 2, 3]` returns `3`. Known as Boyer-Moore Voting Algorithm’s application, this problem is used in voting systems or data aggregation, assuming a majority exists, solvable in O(n) time and O(1) space.

#### Approach

- Use Boyer-Moore: maintain a candidate and count.
- Increment count when seeing the candidate, decrement when seeing others; reset candidate if count hits 0.
- The majority element always survives due to its frequency.
- Single pass identifies the candidate (verification optional if guaranteed).

#### Pseudocode

```
FUNCTION majorityElement(arr, n)
    SET candidate = arr[0]
    SET count = 1

    FOR i = 1 TO n-1
        IF count == 0 THEN
            candidate = arr[i]
        END IF
        IF arr[i] == candidate THEN
            INCREMENT count
        ELSE
            DECREMENT count
        END IF
    END FOR

    RETURN candidate
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the array.
- **Space Complexity**: O(1) – Two variables only.

#### Notes

- **Edge Cases**: Single element (itself); assumes majority exists.
- **C-Specific Tip**: No special memory handling; simple integer variables suffice.
- **Verification**: O(n) pass to confirm count > n/2 if majority not guaranteed.

---

# Comprehensive Notes on Array, Linked List, and Stack Problems in C

## Linked List Section

This section explores 20 essential problems related to Linked Lists, a dynamic data structure of nodes linked by pointers, offering O(1) insertions/deletions but O(n) access. Each problem is detailed with a description, approach, pseudocode, complexity, and C-specific notes. We begin with the first five problems, focusing on foundational manipulations and cycle detection.

---

### 1. Reverse a Linked List

#### Description

Reverse the order of nodes in a singly linked list, transforming `1 -> 2 -> 3 -> 4 -> NULL` into `4 -> 3 -> 2 -> 1 -> NULL`. This fundamental operation is a cornerstone for more complex linked list problems (e.g., palindrome checking) and is often required in-place to optimize space, testing pointer manipulation skills critical in memory-constrained environments.

#### Approach

- Use three pointers: `prev` (previous node), `current` (current node), and `next` (next node).
- Traverse the list, reversing each node’s link by pointing it to `prev`.
- Move `prev` and `current` forward, using `next` to preserve the link to the subsequent node.
- Update the head to `prev` after the loop completes.

#### Pseudocode

```
FUNCTION reverseList(list)
    SET prev = NULL
    SET current = list.head
    SET next = NULL

    WHILE current != NULL
        next = current.next        // Save next node
        current.next = prev        // Reverse link
        prev = current             // Move prev
        current = next             // Move current
    END WHILE

    list.head = prev
    RETURN list
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the list.
- **Space Complexity**: O(1) – Only three pointers, no extra nodes.

#### Notes

- **Edge Cases**: Empty list (`head = NULL`) returns NULL; single node (no change).
- **C-Specific Tip**: Use `struct Node*` pointers; check for NULL to avoid dereferencing errors.
- **Variation**: Recursive reversal uses O(n) stack space but is less memory-efficient.

---

### 2. Detect Loop

#### Description

Determine if a singly linked list contains a cycle, e.g., `1 -> 2 -> 3 -> 2` (loop back to 2) returns true. Known as Floyd’s Cycle Detection or “tortoise and hare,” this problem is critical for debugging infinite loops in list traversals or validating data structures, requiring an efficient O(n) solution with minimal space.

#### Approach

- Use two pointers: `slow` (moves one step) and `fast` (moves two steps).
- Traverse the list; if `slow` and `fast` meet, a cycle exists.
- If `fast` reaches NULL, no cycle exists.
- The meeting point confirms a loop due to the relative speed difference.

#### Pseudocode

```
FUNCTION detectLoop(list)
    SET slow = list.head
    SET fast = list.head

    WHILE fast != NULL AND fast.next != NULL
        slow = slow.next          // Move one step
        fast = fast.next.next     // Move two steps
        IF slow == fast THEN
            RETURN true           // Cycle detected
        END IF
    END WHILE

    RETURN false                 // No cycle
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Fast pointer reaches cycle or end in linear time.
- **Space Complexity**: O(1) – Only two pointers.

#### Notes

- **Edge Cases**: Empty list or single node (no cycle); cycle at head works naturally.
- **C-Specific Tip**: Check `fast.next` before `fast.next.next` to avoid segfaults.
- **Extension**: Find cycle start or length with additional logic.

---

### 3. Find Middle Node

#### Description

Locate the middle node of a singly linked list in one pass, e.g., for `1 -> 2 -> 3 -> 4 -> 5 -> NULL`, return node with value `3`. This problem is useful in divide-and-conquer algorithms (e.g., merge sort) and tests pointer traversal efficiency, aiming for O(n) time without counting nodes first.

#### Approach

- Use two pointers: `slow` (moves one step) and `fast` (moves two steps).
- When `fast` reaches the end, `slow` will be at the middle due to the speed ratio.
- Handle even-length lists by defining middle as the second of two central nodes (e.g., `1 -> 2 -> 3 -> 4` returns `3`).
- Single pass ensures efficiency.

#### Pseudocode

```
FUNCTION findMiddle(list)
    SET slow = list.head
    SET fast = list.head

    WHILE fast != NULL AND fast.next != NULL
        slow = slow.next
        fast = fast.next.next
    END WHILE

    RETURN slow  // Middle node
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Fast pointer traverses list in n/2 steps.
- **Space Complexity**: O(1) – Two pointers only.

#### Notes

- **Edge Cases**: Empty list (NULL); single node (itself).
- **C-Specific Tip**: Return `struct Node*` type; ensure NULL checks for robustness.
- **Variation**: For odd/even distinction, adjust logic or track previous node.

---

### 4. Merge Two Sorted Lists

#### Description

Merge two sorted singly linked lists into one sorted list, e.g., `1 -> 3 -> 5 -> NULL` and `2 -> 4 -> 6 -> NULL` become `1 -> 2 -> 3 -> 4 -> 5 -> 6 -> NULL`. This problem mirrors merge sort’s merge step and is key in list-based sorting or data aggregation, requiring O(n+m) time with minimal space.

#### Approach

- Use a dummy node to simplify merging and pointer management.
- Compare head nodes of both lists, linking the smaller to the result and advancing its pointer.
- Continue until one list is exhausted, then append the remaining nodes.
- Return the merged list starting from dummy’s next.

#### Pseudocode

```
FUNCTION mergeSortedLists(list1, list2)
    CREATE dummy = NEW_NODE(0)
    SET current = dummy

    WHILE list1.head != NULL AND list2.head != NULL
        IF list1.head.data <= list2.head.data THEN
            current.next = list1.head
            list1.head = list1.head.next
        ELSE
            current.next = list2.head
            list2.head = list2.head.next
        END IF
        current = current.next
    END WHILE

    IF list1.head != NULL THEN
        current.next = list1.head
    ELSE IF list2.head != NULL THEN
        current.next = list2.head
    END IF

    SET result = dummy.next
    FREE(dummy)
    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n + m) – Traverse both lists once, where n and m are lengths.
- **Space Complexity**: O(1) – Only dummy node and pointers, no extra list.

#### Notes

- **Edge Cases**: One or both lists empty (return non-empty or NULL).
- **C-Specific Tip**: Use `malloc` for dummy node; free it to prevent leaks.
- **Variation**: Recursive merge uses O(n+m) stack space.

---

### 5. Remove Nth Node from End

#### Description

Delete the nth node from the end of a singly linked list, e.g., for `1 -> 2 -> 3 -> 4 -> 5 -> NULL` and n=2, remove `4` to get `1 -> 2 -> 3 -> 5 -> NULL`. This problem tests two-pointer techniques and is common in list editing, requiring a single-pass O(n) solution.

#### Approach

- Use two pointers: `fast` and `slow`, with `fast` starting n nodes ahead.
- Move both pointers until `fast` reaches the end; `slow` will be at the node before the one to remove.
- Adjust `slow.next` to skip the nth node, freeing it.
- Handle edge cases like removing the head separately.

#### Pseudocode

```
FUNCTION removeNthFromEnd(list, n)
    CREATE dummy = NEW_NODE(0)
    dummy.next = list.head
    SET fast = dummy
    SET slow = dummy

    // Move fast n nodes ahead
    FOR i = 1 TO n
        fast = fast.next
    END FOR

    // Move both until fast reaches end
    WHILE fast.next != NULL
        fast = fast.next
        slow = slow.next
    END WHILE

    // Remove nth node
    SET temp = slow.next
    slow.next = temp.next
    FREE(temp)

    SET result = dummy.next
    FREE(dummy)
    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass after initial n steps.
- **Space Complexity**: O(1) – Only pointers and dummy node.

#### Notes

- **Edge Cases**: Remove head (n = list length); empty list or invalid n.
- **C-Specific Tip**: Dummy node simplifies head removal; use `free` to avoid leaks.
- **Assumption**: n is valid (1 ≤ n ≤ list length).

---

### 6. Add Two Numbers

#### Description

Given two singly linked lists representing numbers (digits in reverse order), add them and return the sum as a linked list, e.g., `2 -> 4 -> 3` (342) and `5 -> 6 -> 4` (465) yield `7 -> 0 -> 8` (807). This problem simulates digit-by-digit addition, common in arbitrary-precision arithmetic, requiring careful handling of carries and list construction.

#### Approach

- Traverse both lists simultaneously, adding corresponding digits and tracking a carry.
- Create a new node for each sum digit (sum % 10), updating carry (sum / 10).
- Use a dummy node to simplify list building, continuing until both lists and carry are exhausted.
- Return the new list starting from dummy’s next.

#### Pseudocode

```
FUNCTION addTwoNumbers(list1, list2)
    CREATE dummy = NEW_NODE(0)
    SET current = dummy
    SET carry = 0

    WHILE list1.head != NULL OR list2.head != NULL OR carry != 0
        SET x = (list1.head != NULL) ? list1.head.data : 0
        SET y = (list2.head != NULL) ? list2.head.data : 0
        SET sum = x + y + carry
        carry = sum / 10
        current.next = NEW_NODE(sum % 10)
        current = current.next

        IF list1.head != NULL THEN list1.head = list1.head.next
        IF list2.head != NULL THEN list2.head = list2.head.next
    END WHILE

    SET result = dummy.next
    FREE(dummy)
    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(max(n, m)) – Traverse longer list once, where n and m are list lengths.
- **Space Complexity**: O(max(n, m)) – New list for result.

#### Notes

- **Edge Cases**: One list empty (treat as 0); carry persists (e.g., 999 + 1).
- **C-Specific Tip**: Use `malloc` for new nodes; free dummy to avoid leaks.
- **Variation**: Forward order requires reversing lists first or stack usage.

---

### 7. Intersection Point

#### Description

Find the node where two singly linked lists intersect, e.g., `1 -> 2 -> 3 -> 4` and `5 -> 6 -> 3 -> 4` share `3 -> 4`, returning node `3`. This problem tests pointer alignment and is relevant in graph traversal or memory sharing detection, assuming intersection exists by node reference, not value.

#### Approach

- Compute lengths of both lists (len1, len2).
- Advance the longer list’s pointer by the difference in lengths.
- Move both pointers together until they meet at the intersection or NULL.
- The alignment ensures they hit the common node simultaneously.

#### Pseudocode

```
FUNCTION getLength(list)
    SET len = 0
    SET temp = list.head
    WHILE temp != NULL
        INCREMENT len
        temp = temp.next
    END WHILE
    RETURN len
END FUNCTION

FUNCTION intersectionPoint(list1, list2)
    SET len1 = getLength(list1)
    SET len2 = getLength(list2)
    SET ptr1 = list1.head
    SET ptr2 = list2.head

    // Advance longer list
    IF len1 > len2 THEN
        FOR i = 1 TO (len1 - len2)
            ptr1 = ptr1.next
        END FOR
    ELSE IF len2 > len1 THEN
        FOR i = 1 TO (len2 - len1)
            ptr2 = ptr2.next
        END FOR
    END IF

    // Find intersection
    WHILE ptr1 != ptr2
        ptr1 = ptr1.next
        ptr2 = ptr2.next
    END WHILE

    RETURN ptr1  // Intersection node or NULL
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n + m) – Length calculation and traversal.
- **Space Complexity**: O(1) – Only pointers, no extra space.

#### Notes

- **Edge Cases**: No intersection (NULL); lists of equal length (immediate traversal).
- **C-Specific Tip**: Compare node pointers (`==`), not values, for intersection.
- **Alternative**: Concatenate traversal (ptr1 to list2, ptr2 to list1) also O(1) space.

---

### 8. Palindrome Check

#### Description

Check if a singly linked list is a palindrome, e.g., `1 -> 2 -> 2 -> 1 -> NULL` returns true, while `1 -> 2 -> 3 -> NULL` returns false. This problem combines list traversal and reversal, applicable in string validation or symmetry checks, aiming for O(n) time and minimal space.

#### Approach

- Find the middle node using slow and fast pointers.
- Reverse the second half of the list.
- Compare the first half (from head) with the reversed second half.
- Restore the list (optional) by reversing the second half again.

#### Pseudocode

```
FUNCTION reverse(head)
    SET prev = NULL
    SET current = head
    WHILE current != NULL
        SET next = current.next
        current.next = prev
        prev = current
        current = next
    END WHILE
    RETURN prev
END FUNCTION

FUNCTION isPalindrome(list)
    IF list.head == NULL OR list.head.next == NULL THEN RETURN true

    SET slow = list.head
    SET fast = list.head
    WHILE fast != NULL AND fast.next != NULL
        slow = slow.next
        fast = fast.next.next
    END WHILE

    SET second_half = reverse(slow)
    SET first_half = list.head
    SET temp = second_half

    WHILE temp != NULL
        IF first_half.data != temp.data THEN
            reverse(second_half)  // Restore (optional)
            RETURN false
        END IF
        first_half = first_half.next
        temp = temp.next
    END WHILE

    reverse(second_half)  // Restore (optional)
    RETURN true
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Middle find, reverse, compare all linear.
- **Space Complexity**: O(1) – In-place reversal and pointers.

#### Notes

- **Edge Cases**: Single node (true); empty list (true).
- **C-Specific Tip**: Optional restoration preserves original list; use temp pointers.
- **Alternative**: Stack-based (O(n) space) copies first half for comparison.

---

### 9. Swap Nodes

#### Description

Swap adjacent nodes pairwise in a linked list without swapping data, e.g., `1 -> 2 -> 3 -> 4 -> NULL` becomes `2 -> 1 -> 4 -> 3 -> NULL`. This problem tests pointer manipulation and is useful in list reordering, requiring an in-place O(n) solution.

#### Approach

- Use a dummy node to handle head swapping easily.
- For each pair, adjust pointers: `prev.next` to second, first.next to second.next, second.next to first.
- Move to the next pair by updating `prev` to the first node of the swapped pair.
- Continue until fewer than two nodes remain.

#### Pseudocode

```
FUNCTION swapNodes(list)
    CREATE dummy = NEW_NODE(0)
    dummy.next = list.head
    SET prev = dummy

    WHILE prev.next != NULL AND prev.next.next != NULL
        SET first = prev.next
        SET second = first.next
        SET temp = second.next

        prev.next = second
        second.next = first
        first.next = temp

        prev = first
    END WHILE

    SET result = dummy.next
    FREE(dummy)
    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass, processing pairs.
- **Space Complexity**: O(1) – Pointers only.

#### Notes

- **Edge Cases**: Odd length (last node unchanged); empty or single node (no swap).
- **C-Specific Tip**: Dummy simplifies edge cases; free it to avoid leaks.
- **Variation**: Swap data instead (simpler but less elegant).

---

### 10. Sort Linked List

#### Description

Sort a singly linked list in ascending order, e.g., `4 -> 2 -> 1 -> 3 -> NULL` becomes `1 -> 2 -> 3 -> 4 -> NULL`. This problem applies merge sort to linked lists, ideal for its divide-and-conquer nature, targeting O(n log n) time and O(1) space (excluding recursion stack).

#### Approach

- Use merge sort:
  - Find middle with slow/fast pointers.
  - Recursively split into two halves.
  - Merge sorted halves using the merge function from problem 4.
- Bottom-up merging ensures sorted order without extra space beyond recursion.

#### Pseudocode

```
FUNCTION merge(list1, list2)
    CREATE dummy = NEW_NODE(0)
    SET current = dummy
    WHILE list1 != NULL AND list2 != NULL
        IF list1.data <= list2.data THEN
            current.next = list1
            list1 = list1.next
        ELSE
            current.next = list2
            list2 = list2.next
        END IF
        current = current.next
    END WHILE
    current.next = (list1 != NULL) ? list1 : list2
    SET result = dummy.next
    FREE(dummy)
    RETURN result
END FUNCTION

FUNCTION sortList(head)
    IF head == NULL OR head.next == NULL THEN RETURN head

    SET slow = head
    SET fast = head
    SET prev = NULL
    WHILE fast != NULL AND fast.next != NULL
        prev = slow
        slow = slow.next
        fast = fast.next.next
    END WHILE
    prev.next = NULL  // Split list

    SET left = sortList(head)
    SET right = sortList(slow)

    RETURN merge(left, right)
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n log n) – Merge sort’s divide and merge.
- **Space Complexity**: O(log n) – Recursion stack; O(1) auxiliary space.

#### Notes

- **Edge Cases**: Single node or empty (already sorted).
- **C-Specific Tip**: Recursive calls need stack space; iterative bottom-up possible but complex.
- **Alternative**: Insertion sort (O(n²)) simpler but slower.

---

### 11. Rotate List

#### Description

Rotate a singly linked list to the right by k positions, e.g., for `1 -> 2 -> 3 -> 4 -> 5 -> NULL` and k=2, return `4 -> 5 -> 1 -> 2 -> 3 -> NULL`. This problem simulates circular shifts, useful in scheduling or cyclic data processing, requiring an O(n) solution with minimal space.

#### Approach

- Compute the list length and normalize k (k %= length) to handle k > length.
- Connect the last node to the head, forming a circular list.
- Find the new tail (length - k - 1 steps from head), set its next to NULL, and update head.
- Break the cycle at the new tail to complete the rotation.

#### Pseudocode

```
FUNCTION rotateList(list, k)
    IF list.head == NULL OR k == 0 THEN RETURN list

    // Get length and last node
    SET len = 1
    SET last = list.head
    WHILE last.next != NULL
        INCREMENT len
        last = last.next
    END WHILE

    k = k % len  // Normalize k
    IF k == 0 THEN RETURN list

    // Make circular
    last.next = list.head

    // Find new tail
    SET steps_to_new_tail = len - k - 1
    SET new_tail = list.head
    FOR i = 0 TO steps_to_new_tail
        new_tail = new_tail.next
    END FOR

    // Break cycle
    SET new_head = new_tail.next
    new_tail.next = NULL
    list.head = new_head

    RETURN list
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Two passes: length and rotation point.
- **Space Complexity**: O(1) – Only pointers, no extra space.

#### Notes

- **Edge Cases**: k=0 or k=length (no change); single node (unchanged).
- **C-Specific Tip**: Ensure pointer updates avoid losing nodes; handle k < 0 if needed.
- **Alternative**: Two-pointer method adjusts pointers without circular step.

---

### 12. Delete Duplicates

#### Description

Remove all duplicates from a sorted singly linked list, e.g., `1 -> 1 -> 2 -> 3 -> 3 -> NULL` becomes `1 -> 2 -> 3 -> NULL`. This problem optimizes sorted list storage, common in data preprocessing, requiring an in-place O(n) solution leveraging the sorted property.

#### Approach

- Traverse the list with a pointer, comparing adjacent nodes.
- If current and next nodes are equal, skip the next node by updating the pointer.
- Continue until the end, preserving unique elements in order.
- Use a dummy node if head might change (not needed here due to sorted nature).

#### Pseudocode

```
FUNCTION deleteDuplicates(list)
    IF list.head == NULL OR list.head.next == NULL THEN RETURN list

    SET current = list.head
    WHILE current != NULL AND current.next != NULL
        IF current.data == current.next.data THEN
            SET temp = current.next
            current.next = temp.next
            FREE(temp)
        ELSE
            current = current.next
        END IF
    END WHILE

    RETURN list
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the list.
- **Space Complexity**: O(1) – In-place with pointers.

#### Notes

- **Edge Cases**: All duplicates (e.g., `1 -> 1 -> 1` to `1`); no duplicates (unchanged).
- **C-Specific Tip**: Free skipped nodes to prevent memory leaks.
- **Variation**: Unsorted list requires hash set or O(n²) comparison.

---

### 13. Flatten a Multilevel List

#### Description

Flatten a multilevel singly linked list into a single-level list, e.g., `1 -> 2 -> 3 -> NULL` with `2 -> 4 -> 5 -> NULL` as a child becomes `1 -> 2 -> 4 -> 5 -> 3 -> NULL`. This problem transforms hierarchical structures, useful in DOM traversal or nested list processing, assuming each node has next and child pointers.

#### Approach

- Traverse the list; if a node has a child, merge the child list between the node and its next.
- Find the child list’s tail, connect it to the original next, and set child to NULL.
- Continue until all nodes are processed, flattening level by level.
- Handle recursively or iteratively for simplicity.

#### Pseudocode

```
FUNCTION flattenList(list)
    SET current = list.head
    WHILE current != NULL
        IF current.child == NULL THEN
            current = current.next
        ELSE
            SET child = current.child
            SET tail = child
            WHILE tail.next != NULL
                tail = tail.next
            END WHILE

            tail.next = current.next
            current.next = child
            current.child = NULL
            current = current.next
        END IF
    END WHILE

    RETURN list
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Visit each node once, where n is total nodes across levels.
- **Space Complexity**: O(1) – In-place with pointers.

#### Notes

- **Edge Cases**: No children (unchanged); all nodes have children (linear merge).
- **C-Specific Tip**: Define node with `struct Node {int data; Node* next; Node* child;};`.
- **Variation**: Recursive flattening uses O(n) stack space.

---

### 14. Clone with Random Pointers

#### Description

Clone a linked list where each node has a random pointer in addition to next, e.g., copy `1 -> 2 -> 3` with random links intact. This problem is complex due to random pointers, applicable in deep copying complex structures like graphs, aiming for O(n) time and minimal space.

#### Approach

- Interleave original and cloned nodes (e.g., `1 -> 1' -> 2 -> 2' -> 3 -> 3'`).
- Set cloned nodes’ random pointers using original’s random.next.
- Separate the cloned list by adjusting next pointers.
- This avoids extra space beyond the output list.

#### Pseudocode

```
FUNCTION cloneList(list)
    IF list.head == NULL THEN RETURN list

    // Step 1: Interleave
    SET current = list.head
    WHILE current != NULL
        SET cloned = NEW_NODE(current.data)
        cloned.next = current.next
        current.next = cloned
        current = cloned.next
    END WHILE

    // Step 2: Set random pointers
    current = list.head
    WHILE current != NULL
        IF current.random != NULL THEN
            current.next.random = current.random.next
        END IF
        current = current.next.next
    END WHILE

    // Step 3: Separate
    CREATE dummy = NEW_NODE(0)
    SET cloned_curr = dummy
    current = list.head
    WHILE current != NULL
        cloned_curr.next = current.next
        cloned_curr = cloned_curr.next
        current.next = cloned_curr.next
        current = current.next
    END WHILE

    SET result = dummy.next
    FREE(dummy)
    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Three linear passes.
- **Space Complexity**: O(1) – Excluding output list, only pointers.

#### Notes

- **Edge Cases**: No random pointers (simple clone); single node.
- **C-Specific Tip**: Define `struct Node {int data; Node* next; Node* random;};`.
- **Alternative**: Hash map (O(n) space) maps original to cloned nodes.

---

### 15. Reverse in Groups

#### Description

Reverse a linked list in groups of k nodes, e.g., for `1 -> 2 -> 3 -> 4 -> 5 -> NULL` and k=2, return `2 -> 1 -> 4 -> 3 -> 5 -> NULL`. This problem generalizes reversal, useful in batch processing, requiring O(n) time and handling partial groups.

#### Approach

- For each group of k nodes, reverse them using pointer adjustments.
- Track the previous group’s end to connect to the current group’s new head.
- Recursively or iteratively process groups, leaving the last < k nodes unchanged.
- Return the new head after all groups are reversed.

#### Pseudocode

```
FUNCTION reverseGroup(head, k)
    IF head == NULL THEN RETURN head

    SET current = head
    SET count = 0
    WHILE current != NULL AND count < k
        current = current.next
        INCREMENT count
    END WHILE

    IF count < k THEN RETURN head  // Less than k nodes

    SET prev = NULL
    SET current = head
    SET next = NULL
    FOR i = 0 TO k-1
        next = current.next
        current.next = prev
        prev = current
        current = next
    END FOR

    SET new_head = prev
    head.next = reverseGroup(current, k)

    RETURN new_head
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Each node processed once.
- **Space Complexity**: O(n/k) – Recursion stack depth.

#### Notes

- **Edge Cases**: k=1 (no change); k > length (full reverse).
- **C-Specific Tip**: Iterative version uses O(1) space but is more complex.
- **Variation**: Specify handling of partial groups (e.g., reverse or leave).

---

### 16. Find Loop Start

#### Description

Given a singly linked list with a cycle, identify the starting node of the loop, e.g., `1 -> 2 -> 3 -> 4 -> 2` (loop at 2) returns node `2`. This problem extends cycle detection (Floyd’s algorithm) to pinpoint the entry, useful in debugging or graph analysis, requiring O(n) time and O(1) space.

#### Approach

- Use Floyd’s cycle detection to find a meeting point (slow and fast pointers).
- Reset slow to head and move both pointers one step at a time; they meet at the loop start.
- The mathematics ensures the second meeting identifies the cycle’s entry due to cycle length properties.
- Return the meeting node as the loop start.

#### Pseudocode

```
FUNCTION findLoopStart(list)
    SET slow = list.head
    SET fast = list.head

    // Find meeting point
    WHILE fast != NULL AND fast.next != NULL
        slow = slow.next
        fast = fast.next.next
        IF slow == fast THEN BREAK
    END WHILE

    IF fast == NULL OR fast.next == NULL THEN RETURN NULL  // No loop

    // Find loop start
    slow = list.head
    WHILE slow != fast
        slow = slow.next
        fast = fast.next
    END WHILE

    RETURN slow  // Loop start node
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Linear time to detect cycle and find start.
- **Space Complexity**: O(1) – Only two pointers.

#### Notes

- **Edge Cases**: No cycle (return NULL); cycle starts at head.
- **C-Specific Tip**: Check `fast.next` before `fast.next.next` to avoid segfaults.
- **Proof**: Distance from head to loop start plus meeting point equals cycle length multiple.

---

### 17. Partition List

#### Description

Partition a singly linked list around a value x, such that all nodes less than x come before those greater than or equal to x, e.g., `1 -> 4 -> 3 -> 2 -> 5 -> 2` with x=3 becomes `1 -> 2 -> 2 -> 4 -> 3 -> 5`. This problem tests list splitting and merging, useful in sorting or data categorization, requiring O(n) time and O(1) space.

#### Approach

- Create two dummy lists: one for nodes < x (`before`), one for nodes >= x (`after`).
- Traverse the original list, appending nodes to the appropriate dummy list based on comparison with x.
- Connect the `before` list’s tail to the `after` list’s head, skipping dummies.
- Return the new head, ensuring in-place operation.

#### Pseudocode

```
FUNCTION partitionList(list, x)
    CREATE before_dummy = NEW_NODE(0)
    CREATE after_dummy = NEW_NODE(0)
    SET before = before_dummy
    SET after = after_dummy
    SET current = list.head

    WHILE current != NULL
        IF current.data < x THEN
            before.next = current
            before = before.next
        ELSE
            after.next = current
            after = after.next
        END IF
        current = current.next
    END WHILE

    after.next = NULL  // End the list
    before.next = after_dummy.next
    SET result = before_dummy.next
    FREE(before_dummy)
    FREE(after_dummy)

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the list.
- **Space Complexity**: O(1) – Two dummy nodes, no extra list.

#### Notes

- **Edge Cases**: All nodes < x or >= x (one list empty); empty list.
- **C-Specific Tip**: Free dummy nodes; ensure `after.next = NULL` to terminate properly.
- **Variation**: Preserve relative order within partitions (inherent here).

---

### 18. Odd-Even List

#### Description

Rearrange a singly linked list so odd-positioned nodes (1st, 3rd, etc.) come before even-positioned nodes (2nd, 4th, etc.), e.g., `1 -> 2 -> 3 -> 4 -> 5 -> NULL` becomes `1 -> 3 -> 5 -> 2 -> 4 -> NULL`. This problem tests pointer rearrangement, useful in list formatting, aiming for O(n) time and O(1) space.

#### Approach

- Split the list into odd and even lists using two pointers.
- Track odd and even heads, connecting odd.next to the next even node and vice versa.
- After separating, connect the odd list’s tail to the even list’s head.
- Return the rearranged list’s head.

#### Pseudocode

```
FUNCTION oddEvenList(list)
    IF list.head == NULL OR list.head.next == NULL THEN RETURN list

    SET odd = list.head
    SET even_head = list.head.next
    SET even = even_head

    WHILE even != NULL AND even.next != NULL
        odd.next = even.next
        odd = odd.next
        even.next = odd.next
        even = even.next
    END WHILE

    odd.next = even_head
    RETURN list
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the list.
- **Space Complexity**: O(1) – Pointers only, in-place.

#### Notes

- **Edge Cases**: Single node (unchanged); two nodes (simple swap).
- **C-Specific Tip**: No memory allocation; careful pointer updates prevent cycles.
- **Variation**: Index-based (here) vs. value-based odd/even.

---

### 19. Split into Two Lists

#### Description

Split a singly linked list into two separate lists, e.g., `1 -> 2 -> 3 -> 4 -> NULL` into `1 -> 3 -> NULL` and `2 -> 4 -> NULL` (alternating nodes). This problem is useful in parallel processing or data distribution, requiring O(n) time and O(1) space, with nodes reassigned in-place.

#### Approach

- Use two pointers to build separate lists: one for first, one for second.
- Alternate nodes by updating next pointers, tracking heads of both lists.
- Set the next of the last node in each list to NULL.
- Return both list heads (e.g., via struct or array).

#### Pseudocode

```
FUNCTION splitIntoTwo(list)
    IF list.head == NULL THEN RETURN (NULL, NULL)
    IF list.head.next == NULL THEN RETURN (list.head, NULL)

    SET first = list.head
    SET second = list.head.next
    SET first_head = first
    SET second_head = second

    WHILE first != NULL AND second != NULL
        first.next = (second.next != NULL) ? second.next : NULL
        first = first.next
        IF first != NULL THEN
            second.next = first.next
            second = second.next
        END IF
    END WHILE

    RETURN (first_head, second_head)
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the list.
- **Space Complexity**: O(1) – Pointers only, no new nodes.

#### Notes

- **Edge Cases**: Single node (second list NULL); empty list (both NULL).
- **C-Specific Tip**: Return via struct (e.g., `struct Result {Node* first; Node* second;};`).
- **Variation**: Split by length (e.g., halves) requires counting first.

---

### 20. Josephus Problem

#### Description

In a circular linked list of n nodes, eliminate every kth node until one remains, e.g., `1 -> 2 -> 3 -> 4 -> 5` (circular) with k=2 returns `3` (last remaining). This classic problem models elimination games, requiring O(n\*k) time or optimization to O(n) with careful pointer management.

#### Approach

- Convert the list to circular by connecting the last node to head.
- Use two pointers: current and previous, moving k steps to eliminate each node.
- Update pointers after deletion, reducing list size until one node remains.
- Return the data of the last node.

#### Pseudocode

```
FUNCTION josephus(list, k)
    IF list.head == NULL THEN RETURN -1

    // Make circular
    SET last = list.head
    WHILE last.next != NULL
        last = last.next
    END WHILE
    last.next = list.head

    SET current = list.head
    SET prev = last
    SET count = 1  // Assume list length computed or passed

    WHILE current.next != current  // Until one node left
        FOR i = 1 TO k-1
            prev = current
            current = current.next
        END FOR
        prev.next = current.next
        SET temp = current
        current = current.next
        FREE(temp)
        DECREMENT count
    END WHILE

    SET result = current.data
    FREE(current)
    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n\*k) – k steps per node elimination.
- **Space Complexity**: O(1) – Pointers only.

#### Notes

- **Edge Cases**: n=1 (return sole node); k=1 (last node).
- **C-Specific Tip**: Free nodes to avoid leaks; assume length known or compute first.
- **Optimization**: O(n) solution uses mathematical formula but less illustrative.

---

## Stack Section

This section explores 20 essential problems related to Stacks, a LIFO (Last In, First Out) data structure offering O(1) push and pop operations, implementable via arrays or linked lists. Each problem is detailed with a description, approach, pseudocode, complexity, and C-specific notes. We begin with the first five problems, focusing on foundational stack applications.

---

### 1. Balanced Parentheses

#### Description

Given a string of parentheses, determine if it is balanced, e.g., `"()(()())"` returns true, while `"(()"` returns false. This problem is fundamental in syntax validation (e.g., compilers) and expression parsing, requiring an O(n) solution using a stack to track matching pairs efficiently.

#### Approach

- Use a stack to store opening parentheses (`(`).
- For each character, push `(` onto the stack; for `)`, pop if the stack isn’t empty, otherwise return false.
- After processing, the stack must be empty for balance.
- This leverages LIFO to match the most recent opening with the current closing.

#### Pseudocode

```
FUNCTION isBalanced(str)
    CREATE stack
    FOR each char c in str
        IF c == '(' THEN
            PUSH(stack, c)
        ELSE IF c == ')' THEN
            IF isEmpty(stack) THEN
                RETURN false
            END IF
            POP(stack)
        END IF
    END FOR

    RETURN isEmpty(stack)
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass through the string.
- **Space Complexity**: O(n) – Stack may store up to n/2 characters.

#### Notes

- **Edge Cases**: Empty string (true); only closings (false).
- **C-Specific Tip**: Use char array or linked list stack; `malloc` for dynamic sizing.
- **Extension**: Handle multiple bracket types (e.g., `{}`, `[]`) with pair matching.

---

### 2. Reverse a String

#### Description

Reverse a string using a stack, e.g., `"hello"` becomes `"olleh"`. This problem demonstrates stack’s LIFO property for order reversal, applicable in text processing or undo operations, aiming for O(n) time with stack operations.

#### Approach

- Push all characters of the string onto a stack.
- Pop characters one by one, building the reversed string.
- The last character pushed becomes the first popped, reversing the order.
- Use a new string or overwrite the original for the result.

#### Pseudocode

```
FUNCTION reverseString(str)
    CREATE stack
    SET n = length(str)

    FOR i = 0 TO n-1
        PUSH(stack, str[i])
    END FOR

    FOR i = 0 TO n-1
        str[i] = POP(stack)
    END FOR

    RETURN str
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Push and pop each character once.
- **Space Complexity**: O(n) – Stack stores all characters.

#### Notes

- **Edge Cases**: Empty string (unchanged); single character (unchanged).
- **C-Specific Tip**: Pass `char*` and modify in-place; allocate stack with `malloc`.
- **Alternative**: Two-pointer swap (O(1) space) avoids stack but less illustrative.

---

### 3. Next Greater Element

#### Description

For each element in an array, find the next greater element to its right, returning -1 if none exists, e.g., `[4, 5, 2, 25]` yields `[5, 25, 25, -1]`. This problem uses stacks for monotonic tracking, common in stock price analysis, requiring O(n) time instead of O(n²) brute force.

#### Approach

- Use a stack to store indices of elements awaiting their next greater.
- Traverse the array; if current element is greater than stack top, pop and set it as next greater.
- Push current index onto stack; after traversal, remaining stack elements get -1.
- This processes each element efficiently with LIFO.

#### Pseudocode

```
FUNCTION nextGreaterElement(arr, n)
    CREATE stack
    CREATE result[n] = {-1}

    FOR i = 0 TO n-1
        WHILE NOT isEmpty(stack) AND arr[i] > arr[top(stack)]
            SET index = POP(stack)
            result[index] = arr[i]
        END WHILE
        PUSH(stack, i)
    END FOR

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Each element pushed/popped once.
- **Space Complexity**: O(n) – Stack and result array.

#### Notes

- **Edge Cases**: All decreasing (all -1); single element (-1).
- **C-Specific Tip**: Use array-based stack with indices; `malloc` for result.
- **Variation**: Circular array doubles input or uses modulo.

---

### 4. Infix to Postfix

#### Description

Convert an infix expression to postfix notation, e.g., `"A + B * C"` becomes `"A B C * +"`. This problem is key in expression evaluation (e.g., calculators), using a stack to manage operator precedence, aiming for O(n) time with proper precedence rules.

#### Approach

- Use a stack to store operators.
- Scan the infix string:
  - Output operands directly.
  - Push operators, popping higher/equal precedence operators to output first.
  - Handle parentheses by pushing `(` and popping to `)` on `)`.
- Pop remaining operators after scanning.

#### Pseudocode

```
FUNCTION precedence(op)
    IF op == '+' OR op == '-' THEN RETURN 1
    IF op == '*' OR op == '/' THEN RETURN 2
    RETURN 0
END FUNCTION

FUNCTION infixToPostfix(infix)
    CREATE stack
    CREATE result  // String or dynamic array

    FOR each char c in infix
        IF c is operand THEN
            APPEND(result, c)
        ELSE IF c == '(' THEN
            PUSH(stack, c)
        ELSE IF c == ')' THEN
            WHILE NOT isEmpty(stack) AND top(stack) != '('
                APPEND(result, POP(stack))
            END WHILE
            POP(stack)  // Remove '('
        ELSE  // Operator
            WHILE NOT isEmpty(stack) AND precedence(top(stack)) >= precedence(c)
                APPEND(result, POP(stack))
            END WHILE
            PUSH(stack, c)
        END IF
    END FOR

    WHILE NOT isEmpty(stack)
        APPEND(result, POP(stack))
    END WHILE

    RETURN result
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass with constant-time stack ops.
- **Space Complexity**: O(n) – Stack and output string.

#### Notes

- **Edge Cases**: Single operand (unchanged); unbalanced parentheses (error).
- **C-Specific Tip**: Use char stack; `malloc` for result with dynamic resizing.
- **Extension**: Handle multi-character operands with tokenization.

---

### 5. Evaluate Postfix

#### Description

Evaluate the value of a postfix expression, e.g., `"2 3 + 5 *"` returns `25` ((2 + 3) \* 5). This problem follows infix-to-postfix conversion, used in stack-based calculators, requiring O(n) time to process operands and operators.

#### Approach

- Use a stack to store operands.
- Scan the postfix string:
  - Push numbers onto the stack.
  - For operators, pop two operands, apply the operation, and push the result.
- The final stack value is the result after processing all tokens.

#### Pseudocode

```
FUNCTION evaluatePostfix(postfix)
    CREATE stack

    FOR each token t in postfix
        IF t is operand THEN
            PUSH(stack, t)  // Convert to integer
        ELSE  // Operator
            SET b = POP(stack)
            SET a = POP(stack)
            IF t == '+' THEN PUSH(stack, a + b)
            ELSE IF t == '-' THEN PUSH(stack, a - b)
            ELSE IF t == '*' THEN PUSH(stack, a * b)
            ELSE IF t == '/' THEN PUSH(stack, a / b)
            END IF
        END IF
    END FOR

    RETURN POP(stack)
END FUNCTION
```

#### Complexity Analysis

- **Time Complexity**: O(n) – Single pass with constant-time stack ops.
- **Space Complexity**: O(n) – Stack stores operands.

#### Notes

- **Edge Cases**: Single operand (itself); invalid expression (stack underflow).
- **C-Specific Tip**: Parse string to int (e.g., `atoi`); handle multi-digit numbers.
- **Assumption**: Well-formed postfix with no division by zero.

---
