## 66. Plus One | Array

Hey, today we are going to solve the **Plus One** from the LeetCode problem section.  This question comes under Array concepts. Let's understand what the problem is and how to find its solution.

* Problem link: [Plus One](https://leetcode.com/problems/plus-one/)
## Problem Statement
You are given a **large integer** represented as an integer array `digits`, where each `digits[i]` is the `i`<sup>`th`</sup> digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading `0`'s.

Increment the large integer by one and return the *resulting array of digits*.

## Examples
Here are some sample examples through which you can understand the problem clearly.
**Example 1:**
<pre>
Input: digits = [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
Incrementing by one gives 123 + 1 = 124.
Thus, the result should be [1,2,4].
</pre>

**Example 2:**
<pre>
Input: digits = [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
Incrementing by one gives 4321 + 1 = 4322.
Thus, the result should be [4,3,2,2].
</pre>

**Example 3:**
<pre>
Input: digits = [9]
Output: [1,0]
Explanation: The array represents the integer 9.
Incrementing by one gives 9 + 1 = 10.
Thus, the result should be [1,0].
</pre>

## Constraints
* `1 <= digits.length <= 100`
* `0 <= digits[i] <= 9`
* `digits` does not contain any leading `0`'s.

## Solution
So, we looked into all the problem details and constraints. Now let's dive into the best available solution for the same.

1. Start traversing the given vector from the back.
2. If the digit is less than 9, increment it by one and return that vector.
3. If the digit is 9, then replace that digit with 0. (Its preceding digit will increment in further `for` loop iterations.
4. In the case of numbers like `99` we will change all `9` to `0` but we need to make the answer as `100` for such conditions, we will add one more `0` to the end of vector and change the first index to `1`.

```
// C++ Solution
class Solution {
public:
    vector<int> plusOne(vector<int>& d) {
        
        for(int i=d.size()-1; i>=0;i--){
            
            if(d[i]<9){
                d[i]++;
                return d;
            }
            else{
                d[i]=0;
            }
        }
        d.push_back(0);
        d[0]=1;
        return d;
    }
};
// Runtime: 0 ms, faster than 100% of C++ online submissions
```

## Conclusion
So, this was the solution for the ** Plus One** Leetcode Problem. Hopefully, you might understand this solution. If you found it useful, please follow me for more such articles and do share with your peers. And yes, don't forget to leave your suggestions, and thoughts in the comment box. 

Thank you!



