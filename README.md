# question-no-3337
Solution to the question no 3337 on leet code 


https://leetcode.com/problems/total-characters-in-string-after-transformations-ii/

3337. Total Characters in String After Transformations II
You are given a string s consisting of lowercase English letters, an integer t representing the number of transformations to perform, and an array nums of size 26. In one transformation, every character in s is replaced according to the following rules:
Replace s[i] with the next nums[s[i] - 'a'] consecutive characters in the alphabet. For example, if s[i] = 'a' and nums[0] = 3, the character 'a' transforms into the next 3 consecutive characters ahead of it, which results in "bcd".
The transformation wraps around the alphabet if it exceeds 'z'. For example, if s[i] = 'y' and nums[24] = 3, the character 'y' transforms into the next 3 consecutive characters ahead of it, which results in "zab".
Return the length of the resulting string after exactly t transformations.
Since the answer may be very large, return it modulo 109 + 7.

Code Explanation:
🧠 Goal:
Given:
A string s of lowercase letters,
An integer t (number of transformation steps),
A list nums of size 26, where nums[i] tells how many positions forward letter 'a' + i can transform,
The task is to find the total number of characters after t transformations.

🔄 How It Works:
Matrix Representation (Mat class):
Represents how each character can transform into others.
T.a[i][j] means how many ways character j can become i.
Transition Matrix (T):
Built from the nums list.
Each letter can move forward by 1 to nums[i] steps (circularly within 'a'–'z').
Matrix Exponentiation (quickmul):
Raises the matrix T to the power t efficiently using exponentiation by squaring.
Simulates t transformation steps.
Frequency Array (f):
Stores the count of each character in the original string s.
Final Computation:
Multiplies the result matrix with the character counts to get the total characters after t steps.

🧾 Result:
The function lengthAfterTransformations returns the final total count modulo 1e9 + 7.
