## 9. Palindrome Number LeetCode Solution

Hey, glad to see you here, Today we are going to see another LeetCode problem named, **Palindrome Number**. This question is based on simple Math and Loops concepts. Let's see what the problem is and how we can write code as a solution to this.

* Problem Link: [Palindrome Number](https://leetcode.com/problems/palindrome-number)


## Problem Statement

Given an integer `x`, return true if `x` is a palindrome integer.

An integer is a **palindrome** when it reads the same backward as forward. For example, `121` is a palindrome while `123` is not.

## Examples

Here are some sample examples through which you can understand the problem clearly.

**Example 1:**

<pre>
Input: x = 121
Output: true
Explanation: The reverse of 121 is 121. Which is the same as the original number
</pre>

**Example 2:**

<pre>
Input: -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
</pre>

**Example 3:**

<pre>
Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
</pre>


## Constraints

* -2<sup>31</sup> <= x <= 2<sup>31</sup> - 1


## Solution

So, we looked into all the problem details and constraints. Now let's dive into solutions for the same.


1. In this problem we will first find the reverse number of `x`.
2. If the reverse is equal to the original number then the number is Palindrome else not.
3. We will store our integer `x` into a temporary variable, for future use. And we will reverse the number `x`
4. The important point is that while finding a reverse integer, we need to take care that reversed integers should not overflow integer limits. So we inserted a check before multiplying `rev` with `10`. If reversed integer id exceeds the integer limits, then we will return `false`.
4. After reversing the integer `x`, we are storing it into the variable `rev`. So, if `rev` matches with our original number stored in `temp`, then we can say that number is a palindrome, else it is not.

```
// C++ Solution
class Solution {
public:
    bool isPalindrome(int x) {
        int temp = x;
        int rem = 0;
        int rev = 0;
        
        if(x < 0){
            return false;
        }
        
        while(x > 0){
            // Getting the last digit by taking modulas.
            int rem = x % 10;
            
            // Checking if the the rev is exceeding integer limit or not
            if ( (rev > INT_MAX/10) || (rev < INT_MIN/10)){
                return false;
            }
            // If rev is in integer limit, appending the last digit to reverse integer.
            rev = (rev*10) + rem;
            
            // Updating the value of the number so that we can get the second-last digit in the next iteration.
            x = x/10;
        }
        // If rev matches with, original integer stored in temp, return true.
        if(rev == temp){
            return true;
        }
        return false;
    }
};

```

## Conclusion

So, this is the solution to the Palindrome Number Leetcode Problem. Hopefully, you might understand this solution. If you liked it, please follow me for more such articles. You can also leave your suggestions, thoughts in the comment box. 

Thank you!
