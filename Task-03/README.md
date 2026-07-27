# Easy question 1 (Concatenate with reverse)
<img width="1920" height="1080" alt="Screenshot From 2026-07-26 21-14-08" src="https://github.com/user-attachments/assets/38e79b20-b6ba-48da-a111-2c113a9005fb" />
This question,I used string reversing to reverse this string and then I concatenated it with my first string with '+' sign.

## Code:
```
class Solution(object):
def concatWithReverse(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        ans=nums+nums[::-1]
        return ans
  ```

# Easy question 2 (Two sum)
<img width="1920" height="1080" alt="Screenshot From 2026-07-26 21-17-52" src="https://github.com/user-attachments/assets/ad816ec9-27f6-4e74-8acf-25ff114c9281" />
For this question,I first tried changing the list to dictionary as it makes it easier to find the indices of the numbers constituting the sum.So,I created 
this dictionary using for loop.Then I again made a for loop to find the indices of the numbers which have sum equal to target.I used a nested loop for this as it allows
for doing the sum of all elements(excluding the sum of the element which we take with itself).For excluding the sum of the number which we took with itself,I made sure
that the indices of both the elements are not equal using if and then I found out the indices.

## Code:
```
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        dict1={}
        for i in range(len(nums)):
            dict1[i]=nums[i]
        for p in range(len(nums)):
            for k in range(len(nums)):
                if p==k:
                    continue
                elif dict1[p]+dict1[k]==target:
                    return [p,k]
```
# Easy question 3(Palindrome number)
<img width="1920" height="1080" alt="Screenshot From 2026-07-26 22-49-31" src="https://github.com/user-attachments/assets/ea219a25-2b48-4ebf-b7a6-873c5d4ef76f" />
For this question,I just made the integer to a string,reversed it and compared if both are equal.If it's equal,I thought it would make it palindrome and hence I used this.
If it's not equal,it will return False.

## Code:
```
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        
        s=str(x)
        if s==s[::-1]:
            return True
        else:
            return False
```
# Medium question 1(Password strength):
<img width="1920" height="1080" alt="Screenshot From 2026-07-26 21-43-45" src="https://github.com/user-attachments/assets/145eb379-cdb9-429e-badc-4bdcae4ae0e9" />
<img width="1920" height="1080" alt="Screenshot From 2026-07-26 21-43-52" src="https://github.com/user-attachments/assets/a2728036-cbd7-426a-92fa-122d13ebae5a" />
This question doesn't accept duplicate keys when counting the points for the password.So,I made an empty string and made it so that all elements already in the
string do not get added again.This eliminates the main issue.Then I used I traversed this string and checked which symbol,alphabet,etc each element of 
the string belongs to and consequently added up the points and returned it to the user.

## Code:
```
class Solution(object):
    def passwordStrength(self, password):
        """
        :type password: str
        :rtype: int
        """
        stri=" "
        for i in password:
            if i not in stri:
                stri=stri+i           
        p=0
        for i in stri:
            if i.isalpha() and i.isupper():
                p+=2
            elif i.isalpha() and i.islower():
                p+=1
            elif i.isdigit():
                p+=3
            elif i in "!@#$":
                p+=5
        return p
```
# Medium question 2(Reverse Integer)
<img width="1920" height="1080" alt="Screenshot From 2026-07-27 23-22-17" src="https://github.com/user-attachments/assets/03980b9f-bffa-4d9c-adf8-e9834cf289a7" />
<img width="1920" height="1080" alt="Screenshot From 2026-07-27 23-22-10" src="https://github.com/user-attachments/assets/ea4323bb-3d8e-4e6d-9d8b-bb769281c370" />
Here,I first got confused as to how to check the bit length.I later googled about this and found out about the int.bit_length() function.After that,I checked whether x 
was positive or negative(because if it's negative,it will have a - sign which when converted to string causes problems).Then,if it was positive,I made it into a string
reversed it,reconverted back into an integer and assigned it to a variable.Then,I first checked the bit size 
and if it was greater than or equal to 32,I returned 0 as the  question requested and if it was less than 32 bit size,I returned the reverse number.If the number was negative,
I first made it positive,then converted it to string,reversed it,made it back into an integer and made it negative again.Then,I checked the bit length 
and if it was greater than or equal to 32 bits,I returned 0 and if it was less than that,I returned the number which I got after reversing.

## Code:
```
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        if x>=0:
            s=str(x)
            sol=s[::-1]
            q=int(sol)
            if q.bit_length()>=32:
                return 0
            else:
                return q
        elif x<0:
            ps=-x
            qs=str(ps)
            sols=qs[::-1]
            solps=int(sols)
            psp=-solps
            if psp.bit_length()>=32:
                return 0
            else:
                return psp
```
    






                    

