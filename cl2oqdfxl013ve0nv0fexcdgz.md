## 53. Maximum Subarray | Kaden's Algorithm

Hey, today let's solve the **Maximum Subarray** question from the LeetCode problem section.  This question comes under the Array data structure. Let's understand what the problem is and how to find its solution.

* Problem link: []()
## Problem Statement
Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

A **subarray **is a **contiguous **part of an array.

## Examples
Here are some sample examples through which you can understand the problem clearly.
**Example 1:**
<pre>
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
</pre>

**Example 2:**
<pre>
Input: nums = [1]
Output: 1
</pre>

**Example 3:**
<pre>
Input: nums = [5,4,-1,7,8]
Output: 23
</pre>

## Constraints
* 1 <= nums.length <= 105
* -10<sup>4</sup> <= nums[i] <= 10<sup>4</sup>


## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same. We will directly look into the best available solution rather than a naive one.
1. Declare two variables `tillSum` and `maxa`. `tillSum` will store the maximum sum till the current index, and `maxa` will store the overall maximum sum subarray.
2. Traverse the given array and add each element in the `tillSum` variable.
3. If the `tillSum` is greater than `maxa`, Update the `maxa`
4. If `tillSum` is lesser than 0, make it zero because the negative number will decrease the subarray sum.
5 At last, return the `maxa` which is the Subarray with maximum sum.

```
// Efficient C++ Solution - By Kaden's Algorithm
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int tillSum = 0;
        int maxa = INT_MIN;
        
        for(int i=0; i<nums.size(); i++)
        {
            tillSum = tillSum + nums[i];
  
            maxa = max(maxa, tillSum);
            
            if(tillSum < 0)
                tillSum = 0;
            
        }
        return maxa;
    }
};

```

## Conclusion
So, this was the solution for the ** Maximum Subarray** Leetcode Problem using **Kaden's Algorithm**. Hopefully, you might understand this solution. If you found it useful, please follow me for more such articles and do share with your peers. And yes, don't forget to leave your suggestions, and thoughts in the comment box. 

Thank you!



