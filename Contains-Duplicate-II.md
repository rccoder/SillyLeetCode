Contains Duplicate II
===

Given an array of integers and an integer k, find out whether there are two distinct indices i and j in the array such that nums[i] = nums[j] and the difference between i and j is at most k.

## 解题思路

k大的集合，多了擦出，每次看里面有没有

hash 判断

## Cpp

```cpp
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
        if(nums.size() < 2 || k < 0) return false;
        set<int> s;
        for(int i = 0; i < nums.size(); i++) {
            if(s.size() > k) {
                s.erase(nums[i - k - 1]);
            }
            if(s.find(nums[i]) != s.end()) {
                return true;
            }
            s.insert(nums[i]);
        }
        return false;
    }
};
```

## Cpp

```cpp
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
        map<int, int> hash;
        for(int i = 0; i < nums.size(); i++) {
            if((hash.find(nums[i]) != hash.end()) && (i - hash[nums[i]] <= k)) return true;
            hash[nums[i]] = i;
        }
        return false;
    }
};
```

## Python

```python
class Solution:
    # @param {integer[]} nums
    # @param {integer} k
    # @return {boolean}
    def containsNearbyDuplicate(self, nums, k):
        dic = {}
        for i in range(0, len(nums)):
            if(nums[i] in dic and abs(i - dic[nums[i]] <= k)):
                return True
            dic[nums[i]] = i;
        return False
        
```