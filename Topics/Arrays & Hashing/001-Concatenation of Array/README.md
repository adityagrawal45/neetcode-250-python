# Concatenation of Array

## LeetCode

https://leetcode.com/problems/concatenation-of-array/

---

## Difficulty

Easy

---

## Pattern

Array

---

## Problem Statement

Given an integer array `nums` of length `n`, create an array `ans` of length `2n` such that:

- `ans[i] = nums[i]`
- `ans[i + n] = nums[i]`

for `0 <= i < n`.

Return the concatenated array.

---

## Intuition

The problem simply asks us to duplicate the original array.

We can create a new array of size `2n` and copy each element twice:

- Once in its original position.
- Once again after the first `n` elements.

Since we only traverse the array once, this approach is efficient.

---

## Algorithm

1. Find the length `n` of the input array.
2. Create a new array `ans` of size `2n`.
3. Traverse the original array.
4. For every index `i`:
   - Store `nums[i]` at `ans[i]`.
   - Store `nums[i]` again at `ans[i + n]`.
5. Return `ans`.

---

## Python Solution

```python
class Solution:
    def getConcatenation(self, nums):
        n = len(nums)
        ans = [0] * (2 * n)

        for i in range(n):
            ans[i] = nums[i]
            ans[i + n] = nums[i]

        return ans
```

---

## Dry Run

### Input

```text
nums = [1,2,1]
```

### Step-by-Step

```
n = 3

ans = [0,0,0,0,0,0]

i = 0
ans = [1,0,0,1,0,0]

i = 1
ans = [1,2,0,1,2,0]

i = 2
ans = [1,2,1,1,2,1]
```

### Output

```text
[1,2,1,1,2,1]
```

---

## Complexity Analysis

**Time Complexity:** `O(n)`

- We traverse the array exactly once.

**Space Complexity:** `O(n)`

- We create a new array of size `2n`.

---

## Alternative Solution

Python provides list multiplication.

```python
class Solution:
    def getConcatenation(self, nums):
        return nums * 2
```

### Complexity

- Time: `O(n)`
- Space: `O(n)`

Although this is shorter, understanding the manual approach is better for interviews.

---

## Key Takeaways

- Learn how to create and initialize arrays.
- Understand index manipulation.
- Practice copying elements into another array.
- Always analyze time and space complexity, even for simple problems.

---

## Tags

- Array
- Simulation