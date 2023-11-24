Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

# Python Solution

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        mp = {}
        for idx, num in enumerate(nums):
            if target - num in mp:
                return [mp[target-num], idx]
            else:
                mp[num] = idx
        return [-1, -1]
```

# C++ Solution

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp;
        for (int i = 0; i < nums.size(); i++) {
            if (mp.count(target-nums[i])) {
                return vector<int>{mp[target-nums[i]], i};
            }
            else {
                mp[nums[i]] = i;
            }
        }
        return vector<int>{};
    }
};
```