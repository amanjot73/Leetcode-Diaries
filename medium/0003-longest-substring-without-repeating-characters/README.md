# 3. Longest Substring Without Repeating Characters

**Difficulty:** Medium
**Tags:** Hash Table, String, Sliding Window
**LeetCode:** https://leetcode.com/problems/longest-substring-without-repeating-characters/

## Problem

Given a string `s`, find the length of the **longest** **substring** without duplicate characters.

**Example 1:**

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3. Note that "bca" and "cab" are also correct answers.
```

**Example 2:**

```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

**Example 3:**

```
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

**Constraints:**

	- `0 <= s.length <= 5 * 10^4`

	- `s` consists of English letters, digits, symbols and spaces.

## Solution (C++)

```cpp
#include<bits/stdc++.h>
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        if(s.length()==1){
            return 1;
        }
        int start=0;
        int left = 0;
        int sizee = INT_MIN;
        unordered_set<char> m;
        while(start<s.length()){
            char k = s[start++];
            if(m.count(k)){

                while(m.count(k)){
                    
                    m.erase(s[left++]);
                }
                m.insert(k);
            }
            else{
                m.insert(k);
                int size2 = (int)m.size();
                sizee = max(sizee,size2);
            }
        }
        if(sizee == INT_MIN){
            return 0;
        }
        
        return sizee;                                                                 
    }
};
```

---
*Solved on 2026-07-10*
