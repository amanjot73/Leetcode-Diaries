# 33. Search in Rotated Sorted Array

**Difficulty:** Medium
**Tags:** Array, Binary Search
**LeetCode:** https://leetcode.com/problems/search-in-rotated-sorted-array/

## Problem

There is an integer array `nums` sorted in ascending order (with **distinct** values).

Prior to being passed to your function, `nums` is **possibly left rotated** at an unknown index `k` (`1 <= k < nums.length`) such that the resulting array is `[nums[k], nums[k+1], ..., nums[n-1], nums[0], nums[1], ..., nums[k-1]]` (**0-indexed**). For example, `[0,1,2,4,5,6,7]` might be left rotated by `3` indices and become `[4,5,6,7,0,1,2]`.

Given the array `nums` **after** the possible rotation and an integer `target`, return *the index of *`target`* if it is in *`nums`*, or *`-1`* if it is not in *`nums`.

You must write an algorithm with `O(log n)` runtime complexity.

**Example 1:**

```
Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
```

**Example 2:**

```
Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
```

**Example 3:**

```
Input: nums = [1], target = 0
Output: -1
```

**Constraints:**

	- `1 <= nums.length <= 5000`

	- `-10^4 <= nums[i] <= 10^4`

	- All values of `nums` are **unique**.

	- `nums` is an ascending array that is possibly rotated.

	- `-10^4 <= target <= 10^4`

## Solution (C++)

```cpp
class Solution {
public:
    int search(vector<int>& arr, int target) {
        int s = 0, e = arr.size()-1;
        while(s<=e){
            int mid = s + (e-s)/2;
            if(arr[mid] == target){
                return mid;
            }
            else if(arr[mid] <arr[e]){
                if(arr[mid]<target && arr[e] >=target){
                    s = mid+1;
                }
                else{
                    e = mid-1;
                }
            }
            else{
                if(arr[mid]>target && arr[s]<=target){
                    e = mid-1;
                }
                else{
                    s = mid+1;
                }
            }
        }
        return -1;

        
    }
};
```

---
*Solved on 2026-07-16*
