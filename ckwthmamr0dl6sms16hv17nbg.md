## 1. Two Sum LeetCode Solution

Hey there,
Today we are going to look into the **Two Sum** is the LeetCode question. This question is based on Array and Hash Table topics. These topics are under one of the most important topics in data structures and algorithms. Let's see what the problem is and how we can write code as a solution to this.

* Problem Link: [Two Sum](https://leetcode.com/problems/two-sum)

## Problem Statement

Given an array of integers `nums` and an integer `target`, you need to return indices of the two numbers such that they add up to the `target`.

You may assume that each input would have **exactly one solution**, and you may not use the same element twice.

You can return the answer in any order.
## Examples
Here are some sample examples through which you can understand the problem clearly.

**Example 1:**
<pre>
Input:nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
</pre>

**Example 2:**
<pre>
Input: nums = [3,2,4], target = 6
Output: [1,2]
Explanation: Because nums[1] + nums[2] == 6, we return [1, 2].
</pre>

**Example 3:**

<pre>
Input: nums = [3,3], target = 6
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 6, we return [0, 1].
</pre>



## Constraints

* 2 <= nums.length <= 10 <sup>4</sup>
* -10<sup>9</sup> <= nums[i] <= 10 <sup>9</sup>
* -10<sup>9</sup> <= target <= 10<sup>9</sup>
* **Only one valid answer exists.**

## Solution

So, we looked into all the problem details and constraints. Now let's dive into solutions for the same.

### Naive Solution 

1. This solution uses two `for` loops. 
2. For each element `num[i]`, we will check whether its succeeding elements `num[j]` give an addition equal to the target or not.
3. If element `num[i]` in addition to `num[j]` gives same value as target, then we will store that `i` & `j` indexes in C++ vector. And return that vector.
4. This solution will give the time complexity of O(n<sup>2</sup>). Because, for every element, we are checking the right part of the array.

```
// C++ Solution

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {        
        vector<int> v;
        for(int i = 0; i < nums.size(); i++)
        {            
            for(int j = i+1; j < nums.size(); j++)
            {  
                // If two numbers give sum equals to the target, add that pair into vector.                 
                if (nums[i] + nums[j] == target )
                {
                    v.push_back(i);
                    v.push_back(j);
                    return v;
                }
            }
        }
        return v;
     }
};
```



### Best Case Solution [O(n)]

1. For an optimised solution, we will use hash tables.
2. We will create an `unordered_map` of the integer datatype.
3. For an array element, we will find in the hash table whether there is any match which on addition with array element gives the `target`
4. If a match is found in a hash table, we will return those indexes.
5. Else, if a match is not found, we will store that array element in a hash table along with the index of that array element.
6. This solution will give the time complexity of `O(n)`. As we are traversing array once and `unordered_map` operations give `O(1)` on average.

```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> ans;
        unordered_map <int, int> m;
        
        for(int i = 0; i < nums.size(); i++)
        {
            if(m.find(target-nums[i]) != m.end())
            {   
                //Match is found in a hash table, we will return those indexes.
                ans.push_back(m[target-nums[i]]);
                ans.push_back(i);
                return ans;
            }
            
          // Match is not found, we will store that array element in a hash table along with the index of that array element.
            m[nums[i]] = i;
        }
        return ans;
    }
};
```

## Conclusion
So, these are the solutions to the Two Sum Leetcode Problem. Hopefully, you might understand these solutions. Please follow me for more such technical and development related content. You can also leave your suggestions, thoughts in the comment box. 

Thank you!
