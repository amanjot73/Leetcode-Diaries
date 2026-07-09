# 204. Count Primes

**Difficulty:** Medium
**Tags:** Array, Math, Enumeration, Number Theory
**LeetCode:** https://leetcode.com/problems/count-primes/

## Problem

Given an integer `n`, return *the number of prime numbers that are strictly less than* `n`.

**Example 1:**

```
Input: n = 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
```

**Example 2:**

```
Input: n = 0
Output: 0
```

**Example 3:**

```
Input: n = 1
Output: 0
```

**Constraints:**

	- `0 <= n <= 5 * 10^6`

## Solution (C++)

```cpp
class Solution {
public:
    int countPrimes(int n) {
        vector<int>check(n,true);
        int c=0;
        for(int i = 2;i<n;i++){
            if(check[i]==true){
                c++;
                for(int j = 2*i;j<n;j=j+i){
                    check[j] = false;
                }
            }
        }
        return c;

    }
};
```

---
*Solved on 2026-07-09*
