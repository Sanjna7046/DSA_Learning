# Insertion Sort

## Definition

Insertion Sort is a simple comparison-based sorting algorithm that builds the final sorted array one element at a time. It picks one element from the unsorted part and inserts it into its correct position in the sorted part.
Example "Insertion Sort works like sorting playing cards in your hand. Each new card is inserted into the correct position among the cards you've already sorted."

## Algorithm

1. Assume the first element is already sorted.
2. Pick the next element (called the key).
3. Compare the key with elements before it.
4. Shift all larger elements one position to the right.
5. Insert the key into its correct position.
6. Repeat until all elements are sorted.

## Dry Run

Input:

```text
[5, 2, 4, 6, 1, 3]
```

After Pass 1:

```text
[2, 5, 4, 6, 1, 3]
```

After Pass 2:

```text
[2, 4, 5, 6, 1, 3]
```

After Pass 3:

```text
[2, 4, 5, 6, 1, 3]
```

After Pass 4:

```text
[1, 2, 4, 5, 6, 3]
```

After Pass 5:

```text
[1, 2, 3, 4, 5, 6]
```

## Time Complexity

| Case | Complexity |
|------|------------|
| Best | O(n) |
| Average | O(n²) |
| Worst | O(n²) |

## Space Complexity

```text
O(1)
```

## Stable Sort?

✅ Yes

## In-place?

✅ Yes

## C++ Implementation

```cpp
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }

        arr[j + 1] = key;
    }
}
```

## Advantages

- Easy to implement.
- Efficient for small datasets.
- Stable sorting algorithm.
- In-place sorting.
- Performs well on nearly sorted arrays.

## Disadvantages

- Inefficient for large datasets.
- Time complexity becomes O(n²) in the average and worst cases.

## Applications

- Sorting small arrays.
- Nearly sorted data.
- Used as a subroutine in advanced sorting algorithms like TimSort.

## Summary

| Property | Value |
|----------|-------|
| Best Time | O(n) |
| Average Time | O(n²) |
| Worst Time | O(n²) |
| Space | O(1) |
| Stable | Yes |
| In-place | Yes |
