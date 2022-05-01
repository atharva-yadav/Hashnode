## 844. Backspace String Compare

Hey coders, today let's solve the **Backspace String Compare
** from the LeetCode problem section.  Let's understand what the problem is and how to find its solution.

* Problem link: [Backspace String Compare](https://leetcode.com/problems/backspace-string-compare/)

## Problem Statement
Given two strings s and t, return true if they are equal when both are typed into empty text editors. '#' means a backspace character.

Note that after backspacing an empty text, the text will continue empty.

## Examples
Here are some sample examples through which you can understand the problem clearly.

**Example 1:**
<pre>
Input: s = "ab#c", t = "ad#c"
Output: true
Explanation: Both s and t become "ac".
</pre>

**Example 2:**
<pre>
Input: s = "ab##", t = "c#d#"
Output: true
Explanation: Both s and t become "".
</pre>

**Example 3:**
<pre>
Input: s = "a#c", t = "b"
Output: false
Explanation: s becomes "c" while t becomes "b".
</pre>

## Constraints
* 1 <= s.length, t.length <= 200
* s and t only contain lowercase letters and '#' characters.

## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same.

1. Keep 2 stacks `st` and `tt` for storing characters of 2 given strings.
2. Traverse the first string and check for three conditions
	1. If the character is `#` and the stack is not empty, then remove the top character from the stack.
	2. If the character is `#` and the stack is empty, then don't do anything because the question says, **` after backspacing an empty text, the text will continue empty.`**
	3. If the character is not `#` simply push that character into the stack.
3. Now do a similar process for the second string by considering the second stack.
4. At last compare two stacks, if two stacks are equal then the strings are equal.

```
// C++ Solution
class Solution {
public:
    bool backspaceCompare(string s, string t) {
        
        stack<char> st;
        stack<char> tt;
        
        for(int i=0; i<s.length(); i++){
            
            if(s[i] == '#' && !st.empty())
                st.pop();
            else if(s[i] == '#' && st.empty()) 
                continue;
            else  
                st.push(s[i]);
        }
        
        for(int i=0; i<t.length(); i++){
           if(t[i] == '#' && !tt.empty())
                tt.pop();
            else if(t[i] == '#' && tt.empty()) 
                continue;
            else  
                tt.push(t[i]);
        }
        
        return (st==tt);
    }
};

```


## Conclusion
So, this was the solution for the **Backspace String Compare
** Leetcode Problem. Hopefully, you might understand this solution. If you found it useful, please follow me for more such articles and do share with your peers. And yes, don't forget to leave your suggestions, and thoughts in the comment box. 

Thank you!



