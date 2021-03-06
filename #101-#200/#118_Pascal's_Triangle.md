# Problem Definition of Pascal's_Triangle

Given a non-negative integer numRows, generate the first numRows of Pascal's triangle.

![gif](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif "In Pascal's triangle, each number is the sum of the two numbers directly above it.")

**Example 1**:

    Input: 5
    Output:
    [
         [1],
        [1,1],
       [1,2,1],
      [1,3,3,1],
     [1,4,6,4,1]
    ]

## Method

    Nothing spacial

## Python Code

```python
class Solution:
    def generate(self, numRows):
        """
        :type numRows: int
        :rtype: List[List[int]]
        """
        # construct a new empty 2-dimension array
        result = [[] for i in range(numRows)]
        for i in range(0,numRows):
            if i == 0:
                result[0].append(1)
            else:
                for j in range(0, i+1):
                    if j == 0 or j == i:
                        result[i].append(1)
                    elif i > 1:
                        result[i].append(result[i-1][j-1] + result[i-1][j])
        return result
```

## Java Code

```java

```