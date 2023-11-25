Given an integer x, return true if x is a palindrome, and false otherwise.

# Python Solution

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        temp = x
        y = 0
        while temp > 0:
            last_digit = temp % 10
            temp = temp // 10
            y = y * 10 + last_digit
        return y == x
```

# C++ Solution

```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }
        int rev = 0;
        while (x > rev) {
            rev = rev * 10 + x % 10;
            x /= 10;
        }
        return rev == x || rev / 10 == x;
        
    }
};
```