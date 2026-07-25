# Quick Sort

## Definition

Quick Sort is a **Divide and Conquer** sorting algorithm that selects a **pivot** element, partitions the array around the pivot, and recursively sorts the left and right subarrays.

## Algorithm

1. Choose a pivot element.
2. Partition the array so that:
   - Elements smaller than the pivot are on the left.
   - Elements larger than the pivot are on the right.
3. Place the pivot in its correct position.
4. Recursively sort the left and right subarrays.

## Complexity

| Case | Time |
|------|------|
| Best | O(n log n) |
| Average | O(n log n) |
| Worst | O(n²) |

**Space:** O(log n)

## Properties

- In-place ✅
- Stable ❌

## Pros

- Fast in practice.
- In-place sorting.
- Efficient for large datasets.

## Cons

- Worst-case time complexity is O(n²).
- Not a stable sorting algorithm.
- Performance depends on pivot selection.
  <img width="595" height="397" alt="image" src="https://github.com/user-attachments/assets/7b99e6af-571d-4dd5-bbe5-03205595256c" />


##lomuto Partition
```cpp
int lomuto partition(int arr[], int low, int high) {
    int pivot = arr[high];   // pivot = last element
    int i = low - 1;

    for (int j = low; j < high; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(&arr[i], &arr[j]);
        }
    }

    swap(&arr[i + 1], &arr[high]);
    return i + 1;   // pivot index
}
```
##Hoarse Partition
```cpp
int hoarePartition(int arr[], int low, int high) {
    int pivot = arr[low];
    int i = low - 1;
    int j = high + 1;

    while (1) {
        do {
            i++;
        } while (arr[i] < pivot);

        do {
            j--;
        } while (arr[j] > pivot);

        if (i >= j)
            return j;  // return the pivot index

        swap(&arr[i], &arr[j]);
    }
}
```
##CODE
```cpp
void quickSort(int arr[], int low, int high)
{
    if (low < high)
    {
        int p = hoarePartition(arr, low, high);

        quickSort(arr, low, p);
        quickSort(arr, p + 1, high);
    }
}

```
