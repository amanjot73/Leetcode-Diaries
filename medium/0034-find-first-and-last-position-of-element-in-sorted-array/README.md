# 34. Find First and Last Position of Element in Sorted Array

**Difficulty:** Medium
**Tags:** Array, Binary Search
**LeetCode:** https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/

## Problem

Given an array of integers `nums` sorted in non-decreasing order, find the starting and ending position of a given `target` value.

If `target` is not found in the array, return `[-1, -1]`.

You must write an algorithm with `O(log n)` runtime complexity.

**Example 1:**

```
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```

**Example 2:**

```
Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]
```

**Example 3:**

```
Input: nums = [], target = 0
Output: [-1,-1]
```

**Constraints:**

	- `0 <= nums.length <= 10^5`

	- `-10^9 <= nums[i] <= 10^9`

	- `nums` is a non-decreasing array.

	- `-10^9 <= target <= 10^9`

## Solution (C++)

```cpp
class Solution {
public:
    int first(vector<int>&nums,int s,int e,int target ){
        int ans=-1;
        while(s<=e){
            int mid = s+ (e-s)/2;
            if(nums[mid]== target){
                ans = mid;
                e = mid-1;
            }
            else if(nums[mid]>target){
                e = mid-1;
            }
            else{
                s = mid+1;
            }
        }
        return ans;
    }
    int last(vector<int>&nums,int s,int e,int target ){
        int ans=-1;
        while(s<=e){
            int mid = s+ (e-s)/2;
            if(nums[mid]== target){
                ans = mid;
                s = mid+1;
            }
            else if(nums[mid]>target){
                e = mid-1;
            }
            else{
                s = mid+1;
            }
        }
        return ans;
    }
    vector<int> searchRange(vector<int>& nums, int target) {
        int f = first(nums,0,nums.size()-1,target);
        int e = last(nums,0,nums.size()-1,target);
        return {f,e};

        
    }
};
```

---
*Solved on 2026-07-16*
