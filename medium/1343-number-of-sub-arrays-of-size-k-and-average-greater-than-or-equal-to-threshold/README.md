# 1343. Number of Sub-arrays of Size K and Average Greater than or Equal to Threshold

**Difficulty:** Medium
**Tags:** Array, Sliding Window
**LeetCode:** https://leetcode.com/problems/number-of-sub-arrays-of-size-k-and-average-greater-than-or-equal-to-threshold/

## Problem

Given an array of integers `arr` and two integers `k` and `threshold`, return *the number of sub-arrays of size *`k`* and average greater than or equal to *`threshold`.

**Example 1:**

```
Input: arr = [2,2,2,2,5,5,5,8], k = 3, threshold = 4
Output: 3
Explanation: Sub-arrays [2,5,5],[5,5,5] and [5,5,8] have averages 4, 5 and 6 respectively. All other sub-arrays of size 3 have averages less than 4 (the threshold).
```

**Example 2:**

```
Input: arr = [11,13,17,23,29,31,7,5,2,3], k = 3, threshold = 5
Output: 6
Explanation: The first 6 sub-arrays of size 3 have averages greater than 5. Note that averages are not integers.
```

**Constraints:**

	- `1 <= arr.length <= 10^5`

	- `1 <= arr[i] <= 10^4`

	- `1 <= k <= arr.length`

	- `0 <= threshold <= 10^4`

## Solution (C++)

```cpp
        for(int i=0;i<k;i++){
            sum+=arr[i];
        }
        if(sum/k >=threshold){
        int ans=0;
            ans++;
        }
        int start = 0, s2=k;
        while(s2!=arr.size()){
        }
            sum-=arr[start++];
    }
            sum+=arr[s2++];
        return ans;
            }
            if(sum/k >=threshold){
                ans++;
};
        int sum = 0;
    int numOfSubarrays(vector<int>& arr, int k, int threshold) {
public:
class Solution {

```

---
*Solved on 2026-07-08*
