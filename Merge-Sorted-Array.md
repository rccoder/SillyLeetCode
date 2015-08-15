Merge Sorted Array 
===

Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

**Note:**
You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2. The number of elements initialized in nums1 and nums2 are m and n respectively.

## 解题思路

从大的开始，谁大放谁

注意最后，没有返回值

## Cpp

```cpp
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        if(m == 0) nums1 = nums2;
        int p = m + n;
        vector<int> M(p);
        while(m > 0 && n > 0) {
            if(nums1[m-1] > nums2[n-1]) {
                M[--p] = nums1[--m];
            } else {
                M[--p] = nums2[--n];
            }
        }
        while(m > 0) {
            M[--p] = nums1[--m];
        }
        while(n > 0) {
            M[--p] = nums2[--n];
        }
        nums1 = M;
    }
};
```

## Python

```python
class Solution:
    # @param {integer[]} nums1
    # @param {integer} m
    # @param {integer[]} nums2
    # @param {integer} n
    # @return {void} Do not return anything, modify nums1 in-place instead.
    def merge(self, nums1, m, nums2, n):
        if(n == 0):
            nums1 = nums2
            
        nums1 += [0] * (n + m - len(nums1))
        
        p = m + n
        
        while (m > 0 and n > 0):
            if(nums1[m-1] > nums2[n-1]):
                p -= 1
                m -= 1
                nums1[p] = nums1[m]
            else:
                p -= 1
                n -= 1
                nums1[p] = nums2[n]
                
        while(n > 0):
            p -= 1
            n -= 1
            nums1[p] = nums2[n]
```
