# Minimum-Length-of-String-After-Deleting-Similar-Ends
Given a string s consisting only of characters 'a', 'b', and 'c'. You are asked to apply the following algorithm on the string any number of times:  Pick a non-empty prefix from the string s where all the characters in the prefix are equal. Pick a non-empty suffix from the string s where all the characters in this suffix are equal. 

class Solution:
    def minimumLength(self, s: str) -> int:
        left, right = 0, len(s) - 1
        
        while left < right and s[left] == s[right]:
            char = s[left]
            while left <= right and s[left] == char:
                left += 1
            while right >= left and s[right] == char:
                right -= 1
        
        return right - left + 1
