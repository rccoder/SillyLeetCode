Contains Duplicate
===

Given an array of integers, find if the array contains any duplicates. Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

## 解题思路

建立hash,没有加入，有return true

排序和旁边比

## Cpp

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        map<int, int> hash;
        for(int i = 0; i < nums.size(); i++) {
            if(hash.find(nums[i]) != hash.end()) return true;
            hash[nums[i]] ++;
        }
        return false;
    }
};
```

## Cpp

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for(int i = 1; i < nums.size(); i++) {
            if(nums[i] == nums[i-1]) return true;
        }
        return false;
    }
};
```

## Python

```python
class Solution:
    # @param {integer[]} nums
    # @return {boolean}
    def containsDuplicate(self, nums):
        nums = sorted(nums)
        for i in range(0, len(nums)-1):
            if(nums[i] == nums[i+1]):
                return True
        return False
```