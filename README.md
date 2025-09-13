# Data-Structures
This document contains pseudocode (Pascal-style) for two problems:

1. **Sum of Distinct Elements from Two Sets**  
2. **Dot Product and Orthogonality Check**

Each section includes the algorithm, detailed comments, and an example.

---


## Problem 1: Sum of Distinct Elements from Two Sets

### Task
- Two sets are given.  
- Find elements that appear in only one of the sets.  
- Return their sum.

### Algorithm
```
ALGORITHM sum_distinct_elements
VAR
    set1, set2 : ARRAY OF INTEGER
    n1, n2 : INTEGER                // sizes of the two sets
    i, j : INTEGER
    found : BOOLEAN                 // flag to check membership in both sets
    sum : INTEGER                   // final result

BEGIN
    sum <- 0

    // Step 1: check elements in set1
    FOR i <- 1 TO n1 DO
        found <- FALSE
        FOR j <- 1 TO n2 DO
            IF set1[i] = set2[j] THEN
                found <- TRUE        // element exists in both sets
            END_IF
        END_FOR
        IF found = FALSE THEN
            sum <- sum + set1[i]     // add unique element
        END_IF
    END_FOR

    // Step 2: check elements in set2
    FOR i <- 1 TO n2 DO
        found <- FALSE
        FOR j <- 1 TO n1 DO
            IF set2[i] = set1[j] THEN
                found <- TRUE
            END_IF
        END_FOR
        IF found = FALSE THEN
            sum <- sum + set2[i]
        END_IF
    END_FOR

    // Step 3: display result
    Write("Sum of distinct elements = ", sum)
END
```

### Example
- Input: Set1 = [3, 1, 7, 9], Set2 = [2, 4, 1, 9, 3]  
- Distinct = {7, 2, 4}  
- Output: `Sum of distinct elements = 13`

---

## Problem 2: Dot Product and Orthogonality Check

### Task
- Read two vectors of equal size.  
- Compute their dot product.  
- Check if they are orthogonal.

### Algorithm
```
ALGORITHM dot_product_and_check
VAR
    v1, v2 : ARRAY OF REAL          // input vectors
    n : INTEGER                     // vector size
    ps : REAL                       // dot product result

FUNCTION dot_product(v1, v2 : ARRAY OF REAL; n : INTEGER) : REAL
VAR
    i : INTEGER
    result : REAL
BEGIN
    result <- 0
    FOR i <- 1 TO n DO
        result <- result + v1[i] * v2[i]   // element-wise multiply and sum
    END_FOR
    RETURN result
END_FUNCTION

BEGIN
    Read(n)                          // size of vectors
    Read(v1[1..n])                   // read first vector
    Read(v2[1..n])                   // read second vector

    ps <- dot_product(v1, v2, n)     // compute dot product

    IF ps = 0 THEN
        Write("Vectors are orthogonal")
    ELSE
        Write("Vectors are not orthogonal")
    END_IF
END
```

### Example
- Input: v1 = [1, 2, 3], v2 = [-3, 0, 1]  
- Dot product = -3 + 0 + 3 = 0  
- Output: `Vectors are orthogonal`

---

# Notes
- These algorithms follow a **Pascal-style pseudocode format** with `BEGIN`/`END` blocks and `FOR` loops.  
- Comments are added to explain **each major step** for clarity.  
