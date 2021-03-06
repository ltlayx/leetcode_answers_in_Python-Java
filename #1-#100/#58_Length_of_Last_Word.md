# Problem Description of Length_of_Last_Word

Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word in the string.

If the last word does not exist, return 0.

**Note**: A word is defined as a character sequence consists of non-space characters only.

**Example**:

Input: "Hello World"

Output: 5

## Method

Key Method: Counting from back

Time complexity : less than $O(N)$, depends on length of last word. The worst time complexity is $O(N)$, which means the entire string is a word

## Python Code

```python
class Solution:
    def lengthOfLastWord(self, s):
        """
        :type s: str
        :rtype: int
        """
        #because we won't go through the entire string, time complexity will be less than O(N), and depends on the length of last word.
        num = 0 #Length of Last Word
        for i in range(-1,-len(s)-1,-1):#Counting from back of String s backwards
            if s[i] == ' ' and num == 0:
                continue #Ignore the spaces at the end of s
            elif s[i] == ' ':
                return num # Find the first space and return
            else:
                num = num + 1 #Count the length
        return num
```

## Java Code

```java
class Solution {
    public int lengthOfLastWord(String s) {
        // Length of last word
        int count = 0;
        // Find from the rear of the string
        for(int i = s.length() - 1; i >= 0; i--){
            // If there is not a space then record the length
            if(s.charAt(i) != ' '){
                for(int j = i; j >= 0; j--){
                    // Record the length of word
                    if(s.charAt(j) != ' ')
                        count++;
                    else
                        break;
                }
            }
            if(count != 0)
                return count;
        }
        return count;
    }
}
```