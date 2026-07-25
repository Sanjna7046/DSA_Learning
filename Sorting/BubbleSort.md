# Bubble Sort

## Algorithm
1. Compare adjacent elements.
2. Swap if they are in the wrong order.
3. Repeat for all elements.
4. After each pass, the largest element reaches its correct position.

## Time Complexity

| Case | Complexity |
|------|------------|
| Best | O(n) |
| Average | O(n²) |
| Worst | O(n²) |

## Space Complexity

O(1)


## Advantages
- Easy to understand
- In-place sorting

## Disadvantages
- Slow for large datasets




```cpp
void bubbleSort(int arr[], int n) {
    int i, j;

    // Last i elements are already in place
    for (i = 0; i < n - 1; i++) {
        for (j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(&arr[j], &arr[j + 1]);
            }
        }
    }
}
```
