Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

# Python Solution

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        def re_dup(nums):
            slow, fast = 0, 0
            while fast < len(nums):
                if nums[fast] != 0:
                    nums[slow] = nums[fast]
                    slow += 1
                fast += 1
            return slow
        
        p = re_dup(nums)
        for i in range(p, len(nums)):
            nums[i] = 0
```

# C++ Solution

```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int p = re_dup(nums);
        for (int i=p; i<nums.size(); i++) {
            nums[i] = 0;
        }
    }
    int re_dup(vector<int>& nums) {
        int slow=0, fast = 0;
        while (fast < nums.size()) {
            if (nums[fast] != 0) {
                nums[slow] = nums[fast];
                slow++;
            }
            fast++;
        }
        return slow;
    }
};
```