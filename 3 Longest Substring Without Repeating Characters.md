Given a string s, find the length of the longest substring without repeating characters.

# Python Solution

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        left = 0
        right = 0
        window = {}
        ans = 0
        while (right < len(s)):
            c = s[right]
            right += 1
            window[c] = window.get(c, 0) + 1
            while window[c] > 1:
                d = s[left]
                window[d] -= 1
                left += 1
            ans = max(ans, right - left)
        return ans
```

# C++ Solution

```cpp
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int left = 0, right=0;
        int ans = 0;
        unordered_map<char, int> window;
        while (right < s.size()) {
            char c = s[right];
            right++;
            window[c]++;
            while (window[c] > 1) {
                char d = s[left];
                left++;
                window[d]--;
            }
            ans = max(ans, right - left);
        }
        return ans;
    }
};
```