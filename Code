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
