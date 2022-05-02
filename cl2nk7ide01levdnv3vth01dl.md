## 240. Search a 2D Matrix II | Binary Search


Hey, today we are going to solve the **Search a 2D Matrix II** from the LeetCode problem section.  This question comes under 2D Arrays and Searching concepts. Let's understand what the problem is and how to find its solution.

* Problem link: [240. Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix/)
## Problem Statement

Write an efficient algorithm that searches for a value target in an m x n integer matrix `matrix`. This matrix has the following properties:

* Integers in each row are sorted from left to right.
* The first integer of each row is greater than the last integer of the previous row.

## Examples
Here are some sample examples through which you can understand the problem clearly.
**Example 1:**
[](https://assets.leetcode.com/uploads/2020/10/05/mat.jpg)
<pre>
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
Output: true
</pre>

**Example 2:**
[](https://assets.leetcode.com/uploads/2020/10/05/mat2.jpg)
<pre>
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Output: false
</pre>


## Constraints
* m == matrix.length
* n == matrix[i].length
* 1 <= m, n <= 100
* -10<sup>4</sup> <= matrix[i][j], target <= 10<sup>4</sup>

## Solution
So, we looked into all the problem details and constraints. Now let's dive into efficient solutions for the same.

```
// C++ Solution

class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int m = matrix.size();
        int n = matrix[0].size();
        
        int i=0; 
        int j = matrix[0].size()-1;
        
        while(i<m && j>=0) {
            
            if(matrix[i][j] == target)
                return true;
            
            else if(matrix[i][j] > target)
                j--;
            
            else if(matrix[i][j] < target)
                i++;
        }
        
        return false;
    }
};
```


## Conclusion
So, this was the solution for the **Search a 2D Matrix II** Leetcode Problem using **Binary Search**. Hopefully, you might understand this solution. If you found it useful, please follow me for more such articles and do share with your peers. And yes, don't forget to leave your suggestions, and thoughts in the comment box. 

Thank you!



