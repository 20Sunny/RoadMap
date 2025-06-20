Alright Sunny, let’s break this down like you're learning it for real-world use — no fluff, just straight-up clarity.

---

## 🔍 **Binary Search Algorithm** — Explained

Binary Search is **fast and efficient**, but **only works on sorted arrays**.

### 🎥 Video Explanation

[![Binary Search Algorithm - Video Explanation](https://img.youtube.com/vi/TbbSJrY5GqQ/0.jpg)](https://www.youtube.com/watch?v=TbbSJrY5GqQ)
---
### 🧠 Concept:

Given a sorted array, Binary Search **divides the search space in half repeatedly** to find the target value.

Instead of scanning every element like **Linear Search (O(N))**, Binary Search cuts the problem in half every step. That’s why it's **O(log N)** — way faster for big datasets.

---

## ✅ **Conditions to Use Binary Search**

You can't just use it anywhere. These are **must-haves**:

1. The data **must be sorted** (ascending or descending order).
2. You need **random access** (i.e., constant-time access like in arrays, not linked lists).

---

## 🔧 **Algorithm Logic (Step-by-Step)**

1. Set `low = 0` and `high = len(arr) - 1`.
2. Find `mid = low + (high - low) // 2`.
3. Compare `arr[mid]` with the target `x`:

   * If equal → Return `mid`.
   * If `x < arr[mid]` → Move to the **left half** (`high = mid - 1`).
   * If `x > arr[mid]` → Move to the **right half** (`low = mid + 1`).
4. Repeat until `low > high`. If not found → Return `-1`.

---

## 🔁 **Iterative Implementation**


```C++ []
#include <bits/stdc++.h>
using namespace std;

int binarySearch(int arr[], int low, int high, int x) {
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == x)
            return mid;
        if (arr[mid] < x)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = { 2, 3, 4, 10, 40 };
    int x = 10;
    int n = sizeof(arr) / sizeof(arr[0]);
    int result = binarySearch(arr, 0, n - 1, x);
    if(result == -1)
        cout << "Element is not present in array";
    else
        cout << "Element is present at index " << result;
    return 0;
}
```

```C []
#include <stdio.h>

int binarySearch(int arr[], int low, int high, int x) {
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == x)
            return mid;
        if (arr[mid] < x)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = { 2, 3, 4, 10, 40 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int x = 10;
    int result = binarySearch(arr, 0, n - 1, x);
    if(result == -1)
        printf("Element is not present in array");
    else
        printf("Element is present at index %d", result);
}
```

```Java []
class BinarySearch {
    int binarySearch(int arr[], int x) {
        int low = 0, high = arr.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == x)
                return mid;
            if (arr[mid] < x)
                low = mid + 1;
            else
                high = mid - 1;
        }
        return -1;
    }

    public static void main(String args[]) {
        BinarySearch ob = new BinarySearch();
        int arr[] = { 2, 3, 4, 10, 40 };
        int x = 10;
        int result = ob.binarySearch(arr, x);
        if (result == -1)
            System.out.println("Element is not present in array");
        else
            System.out.println("Element is present at index " + result);
    }
}
```

```Python []
def binarySearch(arr, low, high, x):
    while low <= high:
        mid = low + (high - low) // 2
        if arr[mid] == x:
            return mid
        elif arr[mid] < x:
            low = mid + 1
        else:
            high = mid - 1
    return -1

if __name__ == '__main__':
    arr = [2, 3, 4, 10, 40]
    x = 10
    result = binarySearch(arr, 0, len(arr)-1, x)
    if result != -1:
        print("Element is present at index", result)
    else:
        print("Element is not present in array")
```

```C# []
using System;

class GFG {
    static int binarySearch(int[] arr, int x) {
        int low = 0, high = arr.Length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == x)
                return mid;
            if (arr[mid] < x)
                low = mid + 1;
            else
                high = mid - 1;
        }
        return -1;
    }

    public static void Main() {
        int[] arr = { 2, 3, 4, 10, 40 };
        int x = 10;
        int result = binarySearch(arr, x);
        if (result == -1)
            Console.WriteLine("Element is not present in array");
        else
            Console.WriteLine("Element is present at index " + result);
    }
}
```

```Javascript []
function binarySearch(arr, x) {
    let low = 0, high = arr.length - 1;
    while (low <= high) {
        let mid = low + Math.floor((high - low) / 2);
        if (arr[mid] === x)
            return mid;
        if (arr[mid] < x)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}

let arr = [2, 3, 4, 10, 40];
let x = 10;
let result = binarySearch(arr, x);
if (result === -1)
    console.log("Element is not present in array");
else
    console.log("Element is present at index " + result);
```

```php []
<?php
function binarySearch($arr, $low, $high, $x) {
    while ($low <= $high) {
        $mid = $low + ($high - $low) / 2;
        if ($arr[$mid] == $x)
            return floor($mid);
        if ($arr[$mid] < $x)
            $low = $mid + 1;
        else
            $high = $mid - 1;
    }
    return -1;
}

$arr = array(2, 3, 4, 10, 40);
$x = 10;
$result = binarySearch($arr, 0, count($arr) - 1, $x);
if ($result == -1)
    echo "Element is not present in array";
else
    echo "Element is present at index $result";
?>
```

🕒 **Time Complexity**: `O(log N)`
📦 **Space Complexity**: `O(1)`

---

## 🔁 **Recursive Implementation**

```python []
def binarySearch(arr, low, high, x):
    if high >= low:
        mid = low + (high - low) // 2

        if arr[mid] == x:
            return mid
        elif arr[mid] > x:
            return binarySearch(arr, low, mid - 1, x)
        else:
            return binarySearch(arr, mid + 1, high, x)
    else:
        return -1

# Driver Code
arr = [2, 3, 4, 10, 40]
x = 10
result = binarySearch(arr, 0, len(arr) - 1, x)

if result != -1:
    print("Element is present at index", result)
else:
    print("Element is not present in array")
```
```C++ []
#include <bits/stdc++.h>
using namespace std;

// A recursive binary search function. It returns
// location of x in given array arr[low..high] is present,
// otherwise -1
int binarySearch(int arr[], int low, int high, int x)
{
    if (high >= low) {
        int mid = low + (high - low) / 2;

        // If the element is present at the middle
        // itself
        if (arr[mid] == x)
            return mid;

        // If element is smaller than mid, then
        // it can only be present in left subarray
        if (arr[mid] > x)
            return binarySearch(arr, low, mid - 1, x);

        // Else the element can only be present
        // in right subarray
        return binarySearch(arr, mid + 1, high, x);
    }
  return -1;
}

// Driver code
int main()
{
    int arr[] = { 2, 3, 4, 10, 40 };
    int query = 10;
    int n = sizeof(arr) / sizeof(arr[0]);
    int result = binarySearch(arr, 0, n - 1, query);
    if (result == -1) cout << "Element is not present in array";
    else cout << "Element is present at index " << result;
    return 0;
}
```
```C []
// C program to implement recursive Binary Search
#include <stdio.h>

// A recursive binary search function. It returns
// location of x in given array arr[low..high] is present,
// otherwise -1
int binarySearch(int arr[], int low, int high, int x)
{
    if (high >= low) {
        int mid = low + (high - low) / 2;

        // If the element is present at the middle
        // itself
        if (arr[mid] == x)
            return mid;

        // If element is smaller than mid, then
        // it can only be present in left subarray
        if (arr[mid] > x)
            return binarySearch(arr, low, mid - 1, x);

        // Else the element can only be present
        // in right subarray
        return binarySearch(arr, mid + 1, high, x);
    }

    // We reach here when element is not
    // present in array
    return -1;
}

// Driver code
int main()
{
    int arr[] = { 2, 3, 4, 10, 40 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int x = 10;
    int result = binarySearch(arr, 0, n - 1, x);
    if (result == -1) printf("Element is not present in array");
    else printf("Element is present at index %d", result);
    return 0;
}
```
```Java []
// Java implementation of recursive Binary Search
class BinarySearch {

    // Returns index of x if it is present in arr[low..
    // high], else return -1
    int binarySearch(int arr[], int low, int high, int x)
    {
        if (high >= low) {
            int mid = low + (high - low) / 2;

            // If the element is present at the
            // middle itself
            if (arr[mid] == x)
                return mid;

            // If element is smaller than mid, then
            // it can only be present in left subarray
            if (arr[mid] > x)
                return binarySearch(arr, low, mid - 1, x);

            // Else the element can only be present
            // in right subarray
            return binarySearch(arr, mid + 1, high, x);
        }

        // We reach here when element is not present
        // in array
        return -1;
    }

    // Driver code
    public static void main(String args[])
    {
        BinarySearch ob = new BinarySearch();
        int arr[] = { 2, 3, 4, 10, 40 };
        int n = arr.length;
        int x = 10;
        int result = ob.binarySearch(arr, 0, n - 1, x);
        if (result == -1)
            System.out.println(
                "Element is not present in array");
        else
            System.out.println(
                "Element is present at index " + result);
    }
}
```
```C# []
// C# implementation of recursive Binary Search
using System;

class GFG {

    // Returns index of x if it is present in
    // arr[low..high], else return -1
    static int binarySearch(int[] arr, int low, int high, int x)
    {
        if (high >= low) {
            int mid = low + (high - low) / 2;

            // If the element is present at the
            // middle itself
            if (arr[mid] == x)
                return mid;

            // If element is smaller than mid, then
            // it can only be present in left subarray
            if (arr[mid] > x)
                return binarySearch(arr, low, mid - 1, x);

            // Else the element can only be present
            // in right subarray
            return binarySearch(arr, mid + 1, high, x);
        }

        // We reach here when element is not present
        // in array
        return -1;
    }

    // Driver code
    public static void Main()
    {

        int[] arr = { 2, 3, 4, 10, 40 };
        int n = arr.Length;
        int x = 10;

        int result = binarySearch(arr, 0, n - 1, x);

        if (result == -1)
            Console.WriteLine(
                "Element is not present in arrau");
        else
            Console.WriteLine("Element is present at index "
                              + result);
    }
}
```
```Javascript []
// JavaScript program to implement recursive Binary Search

// A recursive binary search function. It returns
// location of x in given array arr[low..high] is present,
// otherwise -1
function binarySearch(arr, low, high, x)
{
    if (high >= low) {
        let mid = low + Math.floor((high - low) / 2);

        // If the element is present at the middle
        // itself
        if (arr[mid] == x)
            return mid;

        // If element is smaller than mid, then
        // it can only be present in left subarray
        if (arr[mid] > x)
            return binarySearch(arr, low, mid - 1, x);

        // Else the element can only be present
        // in right subarray
        return binarySearch(arr, mid + 1, high, x);
    }

    // We reach here when element is not
    // present in array
    return -1;
}

let arr = [ 2, 3, 4, 10, 40 ];
let x = 10;
let n = arr.length
let result = binarySearch(arr, 0, n - 1, x);
if (result == -1)
    console.log("Element is not present in array");
else
    console.log("Element is present at index " + result);
```
```php []
<?php
// PHP program to implement
// recursive Binary Search

// A recursive binary search
// function. It returns location
// of x in given array arr[low..high] 
// is present, otherwise -1
function binarySearch($arr, $low, $high, $x)
{
if ($high >= $low)
{
        $mid = ceil($low + ($high - $low) / 2);

        // If the element is present 
        // at the middle itself
        if ($arr[$mid] == $x) 
            return floor($mid);

        // If element is smaller than 
        // mid, then it can only be 
        // present in left subarray
        if ($arr[$mid] > $x) 
            return binarySearch($arr, $low, 
                                $mid - 1, $x);

        // Else the element can only 
        // be present in right subarray
        return binarySearch($arr, $mid + 1, 
                            $high, $x);
}

// We reach here when element 
// is not present in array
return -1;
}

// Driver Code
$arr = array(2, 3, 4, 10, 40);
$n = count($arr);
$x = 10;
$result = binarySearch($arr, 0, $n - 1, $x);
if(($result == -1))
echo "Element is not present in array";
else
echo "Element is present at index ",
                            $result;
                          
?>
```
🕒 **Time Complexity**: `O(log N)`
📦 **Auxiliary Space**:

* Without recursion: `O(1)`
* With recursion: `O(log N)` due to the call stack.

---

## 👀 **Example Walkthrough**

Array: `[2, 5, 8, 12, 16, 23, 38, 56, 72, 91]`
Target: `23`

* First `mid = 4`, arr\[4] = 16 → too small → search right
* Next `mid = 7`, arr\[7] = 56 → too big → search left
* Then `mid = 5`, arr\[5] = 23 → found! ✅

---

## ⚙️ Applications of Binary Search

* Searching in **sorted databases**
* Optimizing values (e.g., **binary search on answer**)
* Finding **first/last occurrence** of a value
* Used in **lower\_bound / upper\_bound** problems
* In **machine learning**: tuning hyperparameters efficiently
* Used in **computer graphics**: ray tracing, etc.

---

## ⚡ Recap: Binary Search vs. Linear Search

| Feature          | Binary Search   | Linear Search |
| ---------------- | --------------- | ------------- |
| Requirement      | Sorted data     | Any data      |
| Time Complexity  | O(log N)        | O(N)          |
| Space Complexity | O(1) / O(log N) | O(1)          |
| Speed            | Way faster      | Slower        |

---
