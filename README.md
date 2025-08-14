# Binary Search Implementation in Python
This repository contains a Python implementation of the **binary search algorithm**, one of the most fundamental and efficient searching techniques in computer science.

# What is binary search?
Binary search is a method for quickly finding a target value in a **sorted** list or array.  
Instead of checking each element sequentially (like linear search), binary search repeatedly **divides the search range in half**, drastically reducing the number of comparisons needed.  
This efficiency makes it especially useful for large datasets, achieving a time complexity of O(log n).

# Purpose

-This code is designed for:

-Learning and understanding binary search mechanics

-Comparing iterative, recursive, and built-in module approaches

-Practicing Python coding and algorithm implementation

# Prerequistes 

- **Sorted Data**: The input list or array **must** be sorted for binary search to work correctly. If the data is unsorted, the algorithm will return incorrect results.

- **Random Access**: The data structure should support fast, direct access to elements. Arrays and lists are ideal, while linked lists are inefficient because accessing the middle element requires sequential traversal.

- **Recursive Implementation**: Binary search can be written recursively for cleaner, more readable code. However, be cautious with very large datasets in Python, as deep recursion can lead to stack overflow errors.
# Technologies Used

-**Python 3.x**

-**Visual Studio Code (for development)**

# How It Works

1. The algorithm begins by checking the **middle element** of the sorted list or array.  
2. If the middle element matches the target value, the search is complete.  
3. If the target value is **smaller** than the middle element, the algorithm searches the **left half** of the array.  
4. If the target value is **greater** than the middle element, the algorithm searches the **right half** of the array.  
5. This process of halving the search range continues until the element is found or the search range becomes empty.  

By reducing the search space by half with each step, binary search operates in **O(log n)** time complexity, making it much more efficient than linear search for large datasets.

# Conclusion

Binary search is one of the most efficient and widely used search algorithms for sorted data. Its simplicity, combined with its logarithmic performance. Whether implemented iteratively, recursively, or with built-in Python modules like `bisect`, understanding binary search is a crucial step in mastering algorithms and improving problem-solving skills.
