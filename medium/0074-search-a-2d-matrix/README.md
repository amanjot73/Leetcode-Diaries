# 74. Search a 2D Matrix

**Difficulty:** Medium
**Tags:** Array, Binary Search, Matrix
**LeetCode:** https://leetcode.com/problems/search-a-2d-matrix/

## Problem

You are given an `m x n` integer matrix `matrix` with the following two properties:

	- Each row is sorted in non-decreasing order.

	- The first integer of each row is greater than the last integer of the previous row.

Given an integer `target`, return `true` *if* `target` *is in* `matrix` *or* `false` *otherwise*.

You must write a solution in `O(log(m * n))` time complexity.

**Example 1:**

![image](https://assets.leetcode.com/uploads/2020/10/05/mat.jpg)

```
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
Output: true
```

**Example 2:**

![image](https://assets.leetcode.com/uploads/2020/10/05/mat2.jpg)

```
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Output: false
```

**Constraints:**

	- `m == matrix.length`

	- `n == matrix[i].length`

	- `1 <= m, n <= 100`

	- `-10^4 <= matrix[i][j], target <= 10^4`

## Solution (C++)

```cpp
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int s = matrix[0].size();
        int row = matrix.size();
        // cout<<s<<" "<<row;
        int r=0;
        for(int i=0;i<row;i++){
            if(matrix[i][0] <=target && matrix[i][s-1]>=target){
                r = i;
                break;
            }
        }
        for(int i=0;i<s;i++){
            if(matrix[r][i] == target){
                return true;
            }
        }
        return false;
        
    }
};
```

---
*Solved on 2026-07-16*
