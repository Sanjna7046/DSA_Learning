# Binary Search

## Definition

Binary Search is an efficient searching algorithm that finds the position of a target element in a **sorted array** by repeatedly dividing the search space into two halves.

> **Prerequisite:** The array must be **sorted**.

## Algorithm

1. Set `low = 0` and `high = n - 1`.
2. Find the middle element.
3. If the middle element is the target, return its index.
4. If the target is smaller, search the left half.
5. If the target is larger, search the right half.
6. Repeat until the element is found or the search space becomes empty.

## Example

Input:

```text
Array: [2, 5, 8, 12, 16, 23, 38, 56]
Target: 16
```

- Middle = 12 → Target is larger → Search right half
- Middle = 23 → Target is smaller → Search left half
- Middle = 16 → Found ✅

## Complexity

| Case | Time |
|------|------|
| Best | O(1) |
| Average | O(log n) |
| Worst | O(log n) |

**Space:**
- Iterative: O(1)
- Recursive: O(log n)

## Properties

- Requires a sorted array ✅
- Divide and Conquer ✅

## Pros

- Very efficient for large sorted datasets.
- Much faster than Linear Search.

## Cons

- Works only on sorted data.
- Sorting the array first may be costly if the data is unsorted.
```cpp
int binarySearch(int arr[], int l, int r, int x)
{
if (r >= l) {
int mid = l + (r- l) / 2;
// Element present at middle
if (arr[mid] == x)
return mid;
}
// Search left subarray
if (arr[mid] > x)
return binarySearch(arr, l, mid- 1, x);
// Search right subarray
return binarySearch(arr, mid + 1, r, x);
)
return-1;
}
```
