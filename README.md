<img width="1600" height="534" alt="output_binary_search jpeg" src="https://github.com/user-attachments/assets/4f7c2723-12b1-425e-a894-704abee20152" /># Experiment No. 1

## Title
**Binary Search Techniques Using Array and Recursion**

### Analyse Time and Space Complexity

### Student Details
- **Email:** pranalihanamantbhopale1@gmail.com
- **GitHub:** https://github.com/pranalihanamantbhopale1-sudo/ExperimentNo1

---

## Aim

To implement Binary Search using **Recursion** and **Iteration** on a sorted array and analyze its time and space complexity.

---

## Algorithm

### Recursive Binary Search
1. Start with `low = 0` and `high = n-1`.
2. Find the middle element.
3. If the key equals the middle element, return its index.
4. If the key is smaller, search the left half recursively.
5. Otherwise, search the right half recursively.
6. If `low > high`, return `-1`.

### Iterative Binary Search
1. Initialize `low` and `high`.
2. Repeat until `low <= high`.
3. Find the middle element.
4. Compare the key with the middle element.
5. Update `low` or `high`.
6. Return index if found, otherwise `-1`.

---

## Program

```c
#include <stdio.h>

int BinSearch(int arr[], int key, int low, int high)
{
    if (low > high)
        return -1;

    int mid = (low + high) / 2;

    if (key == arr[mid])
        return mid;
    else if (key < arr[mid])
        return BinSearch(arr, key, low, mid - 1);
    else
        return BinSearch(arr, key, mid + 1, high);
}

int IterBinSearch(int arr[], int size, int key)
{
    int low = 0, high = size - 1;

    while (low <= high)
    {
        int mid = (low + high) / 2;

        if (arr[mid] == key)
            return mid;
        else if (key < arr[mid])
            high = mid - 1;
        else
            low = mid + 1;
    }

    return -1;
}

int main()
{
    int i, size, key, res;

    printf("Enter the size of the array: ");
    scanf("%d", &size);

    int arr[size];
    printf("Enter %d sorted numbers: ", size);
    for (i = 0; i < size; i++)
        scanf("%d", &arr[i]);

    printf("Enter the number to be found: ");
    scanf("%d", &key);

    res = BinSearch(arr, key, 0, size - 1);
    if (res == -1)
        printf("Using recursion: Element not found.\n");
    else
        printf("Using recursion: Element found at index %d\n", res);

    res = IterBinSearch(arr, size, key);
    if (res == -1)
        printf("Using iteration: Element not found.\n");
    else
        printf("Using iteration: Element found at index %d\n", res);

    return 0;
}
```

---

## Output

> Save the output image in your repository as **output_binary_search.jpeg**

![Output](![Uploading output_binary_search.jpeg.jpeg…]()
)

---

## Time and Space Complexity

| Method | Best Case | Average Case | Worst Case | Space |
|---------|-----------|--------------|------------|-------|
| Recursive Binary Search | O(1) | O(log n) | O(log n) | O(log n) |
| Iterative Binary Search | O(1) | O(log n) | O(log n) | O(1) |

---

## Applications

1. Used in searching elements within sorted databases and arrays.
2. Commonly employed in implementing dictionary lookups and symbol tables.
3. Forms the basis of binary search trees and balanced tree data structures.
4. Applied in numerical methods such as root-finding and threshold detection.
5. Used in system-level programming for locating addresses or keys efficiently.
6. Implemented in libraries, APIs, and compiler optimization routines for fast lookups.

---

## Conclusion

Binary Search is an efficient searching technique for sorted arrays. The iterative method requires **O(1)** extra space, while the recursive method requires **O(log n)** stack space.
