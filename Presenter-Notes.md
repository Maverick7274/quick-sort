---
marp: true
title : "Quick Sort"
slideNumber: true
theme: uncover
class: invert
math: mathjax
author: "Neelanjan Mukherji"
style: |
    .text-left {
        text-align: left;
    }
---

# <!--fit-->Quick Sort

---

# Page 1 : Introduction

* Quick Sort is an "in-place" sorting algorithm, meaning it doesn't require additional memory proportional to the input size.

---

# Page 2 : Algorithm

* The choice of the pivot is crucial. It can be the first, last, or any element from the list.

---

# Page 3 : Algorithm(Contd.)

* Partitioning is the process of rearranging the list based on the pivot.
* Smaller elements go to the left, and larger elements go to the right.

---

# Page 4 : Algorithm(Contd.)

* Recursive calls are made on the subarrays until they become small enough to be considered sorted.

---

# Page 5 : Time Complexity

* The average and best-case time complexity of Quick Sort is $O(n log n)$, making it efficient for large datasets.
* However, in the worst-case scenario, the time complexity can degrade to $O(n^2)$ if the pivot selection is unfavorable.

