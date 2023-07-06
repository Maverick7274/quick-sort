# Quick Sort

## Introduction

* Quick Sort is a widely used sorting algorithm in computer science that follows the divide-and-conquer strategy.
* It efficiently sorts a given list or array of elements by repeatedly partitioning it into two subarrays based on a chosen pivot element.


## Time Complexity

The time complexity of Quick Sort can be analyzed in different scenarios:

1. Average Case
2. Best Case
3. Worst Case


### Average Case

* In the average case, Quick Sort demonstrates excellent performance. The partitioning step divides the array into two roughly equal subarrays, resulting in balanced recursive calls.
* The time complexity of Quick Sort in the average case is O(n log n), where 'n' represents the number of elements in the array.
* This average time complexity arises due to the repeated partitioning of the array into halves.


### Best Case

* The best case occurs when the pivot selection consistently divides the array into two equal-sized subarrays.
* In the best case, the time complexity of Quick Sort is also O(n log n).


### Worst Case

* The worst case of Quick Sort occurs when the pivot selection is consistently unfavorable, resulting in highly imbalanced partitions.
* For example, if the pivot is always the smallest or largest element in the array, each partitioning step divides the array into one subarray with (n-1) elements and another with no elements.


### Worst Case(Contd.)

* In the worst case, Quick Sort's time complexity is O(n^2), which happens when the array is already sorted or contains many equal elements.
* However, the worst-case scenario is less likely to occur in practice, especially with randomized pivot selection techniques.

<!-- 
### Space Complexity

* Quick Sort has an in-place sorting nature, meaning it doesn't require additional memory proportional to the input size.
* The space complexity of Quick Sort is determined by the recursive calls made during the sorting process.
* In the average and best cases, the space complexity is O(log n) since the recursion depth is logarithmic to the input size.
* However, in the worst case, the space complexity can be O(n) due to the skewed partitioning, as the recursion depth reaches 'n'.

-->

## Algorithm


## Code

```cpp
#include <stdio.h>

// Function to swap two elements
void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

// Function to partition the array and return the pivot index
int partition(int arr[], int low, int high) {
    int pivot = arr[high];  // Choose the last element as the pivot
    int i = (low - 1);  // Index of smaller element

    for (int j = low; j <= high - 1; j++) {
        // If the current element is smaller than or equal to the pivot
        if (arr[j] <= pivot) {
            i++;
            swap(&arr[i], &arr[j]);  // Swap arr[i] and arr[j]
        }
    }

    swap(&arr[i + 1], &arr[high]);  // Swap arr[i+1] and arr[high]
    return (i + 1);
}
```


## Code(Contd.)

```cpp
// Recursive function to implement Quick Sort
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        // Find the pivot index
        int pivotIndex = partition(arr, low, high);

        // Recursive calls to sort the subarrays
        quickSort(arr, low, pivotIndex - 1);
        quickSort(arr, pivotIndex + 1, high);
    }
}
```


## Code(Contd.)

```cpp
// Function to print the array
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}
```


## Code(Contd.)

```cpp
// Test the algorithm
int main() {
    int arr[] = {9, 4, 7, 2, 1, 5, 3};
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("Original array: ");
    printArray(arr, size);

    quickSort(arr, 0, size - 1);

    printf("Sorted array: ");
    printArray(arr, size);

    return 0;
}
```


## Output

```bash
Original array: 9 4 7 2 1 5 3 
Sorted array: 1 2 3 4 5 7 9
```