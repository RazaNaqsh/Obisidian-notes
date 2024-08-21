

## Count of Digits


```
class Solution:
    def evenlyDivides (self, N):
        count = 0
        original= N
        while N > 0 :
            digit = N % 10
            if digit != 0 and original % digit == 0:
                count += 1
            N = N // 10
        return count


```

### Last Digit and Reverse

If we have a number , suppose n=7789

if we want to get the last digit, we do 

```
 7789 % 10  gives 9 which is the last digit
```

And in order to goto the next digit place, we do

```

7789/10 == 778

// and so on, we do modulo by 10+ to get the last digit and do the division by 10 to get the number after the last digit is removed
```

```
//the complete code would be

while(n>0){
	digit = n%10;
	print(digit);
	n = n/10;
}
```

if we want count of digits, we can add a count var and increment it,

but theres another way of using log, when using log base 10 of 7783, we get a value around 3.8, and if we add 1, and make it an integer, int(4.8), we get 4, which is the count of the digit

```
#include<bits/stdc++.h>
int count(int n){
	int cnt = (int)(log10(n) +1 );
}
tc is O(log10 (n))
```


When we want to store the reverse of the number


```
rev = (rev*10) + digit
```


```
class Solution:

    def reverse(self, x: int) -> int:

        rev = 0

        sign = 1 if x >= 0 else -1

        x = abs(x)

        while x > 0:

            digit = x % 10

            rev = rev * 10 + digit

            x = x // 10

        rev *= sign

        if rev < -2**31 or rev > 2**31 - 1:

            return 0

        return rev
```


### Palindrome

when the number is same as its reverse

Solution is simple just, take out the reverse of the number and check with the original number, if its the same then its palindrome,
so in here take a temporary variable, dont do operations on n.


```
//my solution

class Solution:

    def isPalindrome(self, x: int) -> bool:

        rev = 0

  

        original = x

        while x>0:

            digit = x % 10

            rev = rev * 10 + digit

            x = x // 10

        return rev == original
```


```
best solution

class Solution:
    def isPalindrome(self, x: int) -> bool:
        return str(x) == str(x)[::-1]

```





### Armstrong number

```
# armstrong number is when you count the digit of numbers and their sum of power to the number of digit is same as the original number

def armstrong(x):

    arm = 0

    original = x

    num = len(str(x))

    while x>0:

        digit = x%10

        arm +=  digit ** num

        x //= 10

    print(arm)

    return original == arm

  

print(armstrong(153))
```