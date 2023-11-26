Given a string s, return the longest palindromic substring in s.

# Python Solution

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        def palindrome(s, l, r):
            while l >=0 and r < len(s) and s[l] == s[r]:
                l -= 1
                r += 1
            return s[l+1: r]
        ans = ""
        for i in range(len(s)):
            odd_p = palindrome(s, i, i)
            even_p = palindrome(s, i, i + 1)
            ans = odd_p if len(odd_p) > len(ans) else ans
            ans = even_p if len(even_p) > len(ans) else ans
        return ans
```

# C++ Solution

```cpp
class Solution {
public:
    string longestPalindrome(string s) {
        string ans = "";
        for (int i = 0; i < s.length(); i++) {
            string s1 = palindrome(s, i, i);
            string s2 = palindrome(s, i, i+1);
            ans = ans.length() > s1.length() ? ans : s1;
            ans = ans.length() > s2.length() ? ans : s2;
        }
        return ans;
    }
    string palindrome(string s, int l, int r) {
        while (l >= 0 && r < s.length() && s[l] == s[r]) {
            l--;
            r++;
        }
        return s.substr(l+1, r-l-1);
    }
};
```