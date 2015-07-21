Two Sum
===
Given an array of integers, find two numbers such that they add up to a specific target number.

The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2. Please note that your returned answers (both index1 and index2) are not zero-based.

You may assume that each input would have exactly one solution.

Input: numbers={2, 7, 11, 15}, target=9

Output: index1=1, index2=2

## Cpp
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int sum;
        vector<int> results;
        for(int i = 0; i < nums.size()-1; i++) {
            for(int j = i+1; j < nums.size(); j++) {
                sum = nums[i] + nums[j];
                if(sum == target) {
                    results.push_back(i+1);
                    results.push_back(j+1);
                }
            }
        }
        return results;
    }
};
```

**Time Limit Exceeded**

## Cpp
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int sum;
        vector<int> results(2, -1);
        map<int, int> hash;
        for(int i = 0; i < nums.size(); i++) {
            if(hash.find(target-nums[i]) == hash.end()) {
                hash[nums[i]] = i;
            } else {
                results[0] = hash[target-nums[i]] + 1;
                results[1] = i+1;
            }
        }
        return results;
    }
};
```