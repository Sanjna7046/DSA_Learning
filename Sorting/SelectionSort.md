# Selection Sort

## Definition

Selection Sort repeatedly finds the smallest element from the unsorted part of the array and places it at the beginning.

## Algorithm

1. Find the minimum element.
2. Swap it with the first unsorted element.
3. Move the sorted boundary one step forward.
4. Repeat until the array is sorted.

## Example

Input:

```text
[64, 25, 12, 22, 11]
```

Pass 1 → `[11, 25, 12, 22, 64]`

Pass 2 → `[11, 12, 25, 22, 64]`

Pass 3 → `[11, 12, 22, 25, 64]`

Pass 4 → `[11, 12, 22, 25, 64]`

## Complexity

| Case | Time |
|------|------|
| Best | O(n²) |
| Average | O(n²) |
| Worst | O(n²) |

**Space:** O(1)

## Properties

- In-place ✅
- Stable ❌

## Pros

- Simple to implement.
- Performs fewer swaps than Bubble Sort.

## Cons

- Slow for large datasets.
- Always performs O(n²) comparisons.
```cpp
void selectionSort(int arr[], int n)
{
int i, j, min_idx;
// Move boundary of unsorted subarray
for (i = 0; i < n- 1; i++)
{
// Find the minimum element in unsorted array
min_idx = i;
for (j = i + 1; j < n; j++)
{
if (arr[j] < arr[min_idx])
min_idx = j;
}
}
// Swap found minimum with first element
if (min_idx != i)
swap(&arr[min_idx], &arr[i]);
}
```
