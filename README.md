# Binary Search Implementation in Python
Binary Search Implementation in Pythonn

**Description:**
This project demonstrates the implementation of the binary search algorithm in Python. Binary search is a searching algorithm used to find the position of a target value within a sorted array. The algorithm works by repeatedly dividing the search interval in half. If the value of the search key is less than the item in the middle of the interval, the algorithm narrows the interval to the lower half. Otherwise, it narrows it to the upper half. The process continues until the value is found or the interval is empty.

**Key Features:**
1. **Iterative Binary Search:** A function that performs binary search using an iterative approach.
2. **Recursive Binary Search:** A function that performs binary search using a recursive approach.
3. **Binary Search using Bisect Module:** A function that uses Python's `bisect` module to perform binary search.
4. **User Input:** The script accepts user input for a sorted array and a target value to search for.

### Code Explanation

```python
# Binary Search is a searching algorithm for finding an element's position in a sorted array.

# Iterative Binary search function
# It returns index of x in given array arr if present, else return -1
def binary_search_iterative(arr, x):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        # If element is present at mid
        if arr[mid] == x:
            return mid
        # If x is greater, ignore left half
        elif arr[mid] < x:
            low = mid + 1
        # If x is smaller, ignore right half
        else:
            high = mid - 1
    return -1  # Element is not present in array

# Recursive Binary search function
def binary_search_recursive(arr, low, high, x):
    # Check base case
    if high >= low:
        mid = (low + high) // 2
        # If element is present at the middle itself
        if arr[mid] == x:
            return mid
        # If element is not at the middle, check if it is in the left subarray
        elif arr[mid] > x:
            return binary_search_recursive(arr, low, mid - 1, x)
        # Else the element can only be present in the right subarray
        else:
            return binary_search_recursive(arr, mid + 1, high, x)
    else:
        # Element is not present in the array
        return -1

# Binary search using bisect module
import bisect
def binary_search_bisect(arr, x):
    index = bisect.bisect_left(arr, x)
    if index != len(arr) and arr[index] == x:
        return index
    return -1

# Function to search for an element using iterative binary search
def search_element(arr, x):
    result = binary_search_iterative(arr, x)
    if result != -1:
        print("Element is present at index", str(result))
    else:
        print("Element is not present in array")

# Example usage
if __name__ == "__main__":
    # Accept user input for the array
    arr = input("Enter a sorted array of numbers (comma-separated): ")
    arr = list(map(int, arr.split(',')))

    # Accept user input for the target value
    x = int(input("Enter the number to search for: "))

    # Search for the target value in the array
    search_element(arr, x)
```

**Explanation:**
1. **Iterative Binary Search Function (`binary_search_iterative`):**
   - Takes a sorted array `arr` and a target value `x`.
   - Initializes two pointers, `low` and `high`, to the start and end of the array.
   - While `low` is less than or equal to `high`, calculates the middle index `mid`.
   - If the element at `mid` is equal to `x`, returns `mid`.
   - If the element at `mid` is less than `x`, updates `low` to `mid + 1`.
   - Otherwise, updates `high` to `mid - 1`.
   - If the target is not found, returns `-1`.

2. **Recursive Binary Search Function (`binary_search_recursive`):**
   - Similar to the iterative version but uses recursion to divide the search interval.

3. **Binary Search using Bisect Module (`binary_search_bisect`):**
   - Uses the `bisect_left` function from the `bisect` module to find the target value.

4. **Search Element Function (`search_element`):**
   - Calls the `binary_search_iterative` function and prints the result.

5. **Example Usage:**
   - Accepts user input for a sorted array and a target value.
   - Calls the `search_element` function to search for the target value in the array.
