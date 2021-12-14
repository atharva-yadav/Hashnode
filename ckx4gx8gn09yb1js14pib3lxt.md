## 1207. Unique Number of Occurrences LeetCode Solution

Hey, today we are going to solve the **Unique Number of Occurrences** from the LeetCode problem section.  This question comes under on Array and Hashtable concepts. Let's understand what the problem is and how to find its solution.

* Problem link: [Unique Number of Occurrences](https://leetcode.com/problems/unique-number-of-occurrences/)

## Problem Statement
Given an array of integers `arr`, return `true` if the number of occurrences of each value in the array is **unique**, or `false` otherwise.

## Examples
Here are some sample examples through which you can understand the problem clearly.

**Example 1:**
<pre>
Input: arr = [1,2,2,1,1,3]
Output: true
Explanation: The value 1 has 3 occurrences, 2 has 2 and 3 has 1. No two values have the same number of occurrences.
</pre>

**Example 2:**
<pre>
Input: arr = [1,2]
Output: false 
</pre>

**Example 3:**
<pre>
Input: arr = [-3,0,1,-3,1,1,1,-3,10,0]
Output: true
</pre>


## Constraints
* 1 <= arr.length <= 1000
* -1000 <= arr[i] <= 1000

## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same.

1. We will find the number of occurrences of each element in the array using a hash map.
2. So, we are creating an `unordered_map <int, int> m` and we are inserting the array elements in it. If an element appears multiple times, its corresponding value will be increased.
3. Now, we get the frequency of all array elements using unordered_map. But now we have to check that, Is all those frequency counts are unique?
4. For checking the frequency is unique or not, we will create another `unordered_map<int, int> mp` to store the frequency of array elements.
5. We will insert the frequency of array elements as the keys of unordered_map. And if the frequency same, we will increase its value by 1. 
6. So, if the frequency of two array elements is the same, the corresponding value in `mp` will be greater than 1. And if this happens, we will return `false`. Else return `true`.


```
// C++ Solution
class Solution {
public:
    bool uniqueOccurrences(vector<int>& arr) {
        unordered_map<int, int> m;

        // Insert array elements in a map as a key. There are no duplicate in unordered map, so for same elemts, corresponding value will be increased.
        for(int i=0; i<arr.size(); i++){
            m[arr[i]]++;
        }

         //Create another unordered map for storing the occurrences (freq) of array elemnts
        unordered_map<int, int> mp;
        
        for(auto it = m.begin(); it != m.end(); it++){
            // Adding the number of occurrences of array elements in new map (mp)
            mp[it->second]++;
        }
        
        for(auto x = mp.begin(); x != mp.end(); x++){
            // If two or more array elements have same frequency, return false
            if((x->second) > 1){
                return false;
            }
        }
        return true;
    }
};

// Runtime: 0 ms, faster than 100% of C++ online submissions
```


## Conclusion
So, this was the solution for the ** Unique Number of Occurrences ** Leetcode Problem. Hopefully, you might understand this solution. If you found it useful, please follow me for more such articles and do share with your peers. And yes, don't forget to leave your suggestions, thoughts in the comment box. 

Thank you!
