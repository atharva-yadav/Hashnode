## 344. Reverse String LeetCode Solution

You might have reversed the integer while doing a Palindrome Problem. But here, you asked to Reverse the string. This question is based on the basic String concepts. Let's see what the problem is and how we can write code as a solution to this.

* Problem link: [Reverse String](https://leetcode.com/problems/reverse-string/)

## Problem Statement
Write a function that reverses a string. The input string is given as an array of characters `s`.

You must do this by modifying the input array in-place with `O(1)` extra memory.

## Examples
Here are some sample examples through which you can understand the problem clearly.

**Example 1:**
<pre>
Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"] 
</pre>

**Example 2:**
<pre>
Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
</pre>



## Constraints
*  1 <= s.length <= 10<sup>5</sup>
* ` s[i]`  is a [printable ascii character](https://en.wikipedia.org/wiki/ASCII#Printable_characters).

## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same. The entire logic for reversing a string is based on using the opposite directional two-pointer approach!

1. We maintain two pointers. `start` and `end`, start point to first string character and end to the last character.
2. We swapped those two characters. I.e. the first character will go to last and the last character will come to the first position.
3. After doing this, we will increment the `start` pointer by 1 and decrement the `end` by 1.
4. We will keep doing this until `start` is less than equal to the `end` pointer.
5. This approach is often called as **Two Pointer Approach**



```
// C++ Solution

class Solution {
public:
    void reverseString(vector<char>& s) {

        // Initialise the two pointers
        int start = 0;
        int end = s.size()-1;
        
        while(start <= end){

            // Swap the characters; just like numbers
            char temp = s[start];
            s[start] = s[end];
            s[end] = temp;

            //update both the pointers
            start++;
            end--;
        }
        
    }
};

```



## Conclusion
So, this is the solution to the Reverse String Leetcode Problem. Hopefully, you might understand this solution. If you find it useful, please follow me for more such articles. You can also leave your suggestions, thoughts in the comment box. 

Thank you!

