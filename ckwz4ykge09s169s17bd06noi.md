## 7. Reverse Integer LeetCode Solution

Reverse Integer is one of the LeetCode questions based on simple Maths concepts. This is a very easy problem, let's see what the problem is and how we can write code as a solution to this.

* Problem Link: [Reverse Integer](https://leetcode.com/problems/reverse-integer/)

## Problem Statement
Given a signed 32-bit integer `x`, return `x` with its digits reversed. If reversing `x` causes the value to go outside the signed 32-bit integer range [-2<sup>31</sup>, 2<sup>31</sup> - 1], then return `0`.

**Assume the environment does not allow you to store 64-bit integers (signed or unsigned).**

## Examples
Here are some sample examples through which you can understand the problem clearly.

**Example 1:**
<pre>
Input: x = 123
Output: 321
</pre>

**Example 2:**
<pre>
Input: x = -123
Output: -321 
</pre>

**Example 3:**
<pre>
Input: x = 120
Output: 21
</pre>


## Constraints
*  -2<sup>31</sup> <= x <= 2<sup>31</sup>- 1 

## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same.
1. For finding the reverse, we first need to find the last digit of the number. We will find that by modulo operator `(%)`.
2. After getting that last digit, we need to append that digit to our new reversed integer. For this, we will multiply the reversed number by 10 and add the last digit. This will append to a digit.
3. The main part of this problem is handling the overflow.
4. So, at every step, we are checking if the reversed integer is exceeding the limit of the integer or not. If the limit is crossed, we are returning false.


```
// C++ Solution
class Solution {
public:
    int reverse(int x) {
        int rem = 0;
        int rev = 0;
        
        while(x != 0)
        {
            rem = x % 10;
            // Checking the overflow
            if ( (rev > INT_MAX/10) || (rev < INT_MIN/10)){
                return 0;
            }
            // Appending the last digit of given number to the reverse number
            rev= (rev* 10) + rem;
            // Updating the given number
            x = x/10;
        }
        return rev;
    }
};

```

## Conclusion
So, this is the solution to the Reverse Integer Leetcode Problem. Hopefully, you might understand this solution. If you liked it, please follow me for more such articles. You can also leave your suggestions, thoughts in the comment box. 

Thank you!

