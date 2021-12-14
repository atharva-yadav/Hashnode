## 704. Binary Search LeetCode Solution

The Binary Search is one of the LeetCode questions based on Arrays and Binary Search concepts. This is one of the best searching algorithms. Let's see what this problem is and how we can write code as a solution to this.

* Problem link: [Binary Search](https://leetcode.com/problems/binary-search/)

## Problem Statement

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search target in `nums`. If `target` exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

## Examples
Here are some sample examples through which you can understand the problem clearly.

**Example 1:**
<pre>
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4
</pre>


**Example 2:**
<pre>
Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
</pre>


## Constraints
* 1 <= nums.length <= 10<sup>4</sup>
*  -10<sup>4</sup> < nums[i], target < 10<sup>4</sup> 
* All the integers in `nums` are **unique**.
* `nums` is sorted in ascending order.

## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same. 

1. First of all, we will create two pointers, `start` and `end`.  The `start` will point to the first element of an array and the `end` will point to the last element of an array.
2. Then we will find the middle index of an array. While finding the middle element we will use `mid = start + (end - start) / 2` formula instead of `mid = start + end /2`. The reason is `start + end` might give an overflow error if numbers are large.
3. Now, if the element at the middle index is less than the `target` element, then we will ignore the left part of the middle element. Because the array is sorted and if the middle element is less than the target, then the target must be at the right part of the middle element. We will update the `start` pointer to `mid+1` to ignore the left part.
4. Similarly, if the element at the middle index is greater than the `target` element, then we will ignore the right part of the middle element. We will change the `end` pointer to `mid-1`.
5. The time complexity provided by this algorithm is O(long) as at each step array size gets reduced to half.



```
// C++ Solution
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int start = 0;
        int end = nums.size()-1;
        
        while(start <= end){
            int mid = start + (end - start) / 2;
            if(nums[mid] == target)
                return mid;
            
            else if(nums[mid] < target){
                // Ignore the left part of mid, because array is sorted and target might found in right part
                start = mid +1;
            }
                
             else{
                 // Ignore the right part of mid, because array is sorted and target might found in left part
                 end = mid-1;
             }   
        }
        return -1;
    }
};

```



## Conclusion
So, this is the solution to the Binary Search Leetcode Problem. Hopefully, you might understand this solution. If you liked it, please follow me for more such articles. You can also leave your suggestions, thoughts in the comment box. 

Thank you!
