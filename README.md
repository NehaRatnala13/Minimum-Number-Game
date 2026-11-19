# 2974. Minimum Number Game

**Difficulty:** Easy | **Topics:** Array, Sorting, Heap, Simulation  
**LeetCode Link:** [2974. Minimum Number Game](https://leetcode.com/problems/minimum-number-game/)

## 📝 Problem Summary
You are given an even-length array `nums`. Alice and Bob take turns removing the minimum element from `nums` (Alice first, then Bob), and then appending them to a new array `arr` in reverse order (Bob's element first, then Alice's) until `nums` is empty. 

For full details, examples, and constraints, refer to the [LeetCode Problem Page](https://leetcode.com/problems/minimum-number-game/).

## 🚀 Approach & Intuition
1. **Sort the array:** Sorting `nums` in ascending order naturally aligns the elements such that Alice's picks land on even indices and Bob's land on odd indices.
2. **Swap pairs:** Because Bob appends his element before Alice in each round, swapping every adjacent pair `(nums[i], nums[i+1])` gives the required result.

* **Time Complexity:** \(\mathcal{O}(n \log n)\) for sorting.
* **Space Complexity:** \(\mathcal{O}(1)\) extra space if sorted in-place.

## 💻 Sample Code (Python)
```python
class Solution:
    def numberGame(self, nums: list[int]) -> list[int]:
        nums.sort()
        for i in range(0, len(nums), 2):
            nums[i], nums[i + 1] = nums[i + 1], nums[i]
        return nums
```
