Here's a README-friendly explanation of the **Two Pointer Technique** with a simple diagram.

# Two Pointer Technique

The **Two Pointer** technique uses two indices (pointers) to traverse an array or string efficiently. It is commonly used to reduce time complexity from **O(n²)** to **O(n)**.

## When to Use

- Sorted arrays
- Finding pairs with a target sum
- Removing duplicates
- Reversing arrays or strings
- Sliding window problems

---

## Basic Idea

Instead of using nested loops, use two pointers that move based on certain conditions.

### Example: Find Two Numbers Whose Sum Equals Target

**Array:** `[1, 2, 3, 4, 6, 8, 9]`

**Target:** `10`

### Step 1

```text
Array:  [1, 2, 3, 4, 6, 8, 9]
          L                 R

L = 1
R = 9

Sum = 1 + 9 = 10
```

✅ Target found

---

### Pointer Movement Rules

```text
If sum < target
    Move Left Pointer Right

If sum > target
    Move Right Pointer Left

If sum == target
    Answer Found
```

---

## Visual Diagram

```text
Initial State

+---+---+---+---+---+---+---+
| 1 | 2 | 3 | 4 | 6 | 8 | 9 |
+---+---+---+---+---+---+---+
  ↑                       ↑
 Left                  Right


sum = 1 + 9 = 10
Target = 10

Answer Found ✔
```

---

## Another Example

**Array:** `[1, 2, 3, 4, 5, 8]`

**Target:** `9`

### Iteration 1

```text
+---+---+---+---+---+---+
| 1 | 2 | 3 | 4 | 5 | 8 |
+---+---+---+---+---+---+
  ↑                   ↑

1 + 8 = 9 ✔
```

---

## TypeScript Example

```ts
function twoSumSorted(arr: number[], target: number): number[] | null {
  let left = 0;
  let right = arr.length - 1;

  while (left < right) {
    const sum = arr[left] + arr[right];

    if (sum === target) {
      return [arr[left], arr[right]];
    }

    if (sum < target) {
      left++;
    } else {
      right--;
    }
  }

  return null;
}

console.log(twoSumSorted([1, 2, 3, 4, 6, 8, 9], 10));
// Output: [1, 9]
```

---

## Time & Space Complexity

| Complexity | Value |
| ---------- | ----- |
| Time       | O(n)  |
| Space      | O(1)  |

---

## Summary

```text
1. Start one pointer at the beginning.
2. Start another pointer at the end.
3. Calculate the result (sum, comparison, etc.).
4. Move pointers based on the condition.
5. Continue until pointers meet.
```

**Two Pointers = Less Nested Loops + Better Performance 🚀**
