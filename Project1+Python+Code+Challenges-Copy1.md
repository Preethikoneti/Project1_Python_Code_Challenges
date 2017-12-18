
**Challenge 1: Largest Palindrome**
A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99. Find the largest palindrome made from the product of two 3-digit numbers



```python
def is_palindrome(n):
    condition = True
    while condition:
        if n[0:] == n[::-1]:
            print(n, ':Is largest palindrome made from the product of two 3-digit numbers.')
            condition = False
        else:
           # print(n, 'is not palindrome ')
            n = str(int(n) - 1)
 
 
is_palindrome(str(999*999))
is_palindrome(str(911*999))

```

    997799 :Is largest palindrome made from the product of two 3-digit numbers.
    910019 :Is largest palindrome made from the product of two 3-digit numbers.


**Challenge 2: Summation of primes**

The sum of the primes below 10 is 2 + 3 + 5 + 7 = 17. Find the sum of all the primes below two million.


```python
import math
def is_prime(n):
    status = True
    if n < 2:
        status = False
    else:
        #If the number greater than its square divides it, there's a number smaller than the square 
        for i in range(2,int(math.sqrt(n)+1)):
            if n % i == 0:
                status = False
    return status
 
p=[]
for n in range(1,2000000):
    if is_prime(n):
        p.append(n)
s = sum(p)
print(s,':sum of all the primes below two million')
```

    142913828922 :sum of all the primes below two million



```python
# Using the standard exponent operator without using functions
def is_prime(n):
    status = True
    if n < 2:
        status = False
    else:
        #If the number greater than its square divides it, there's a number smaller than the square 
        for i in range(2,int((n**0.5)+1)):
            if n % i == 0:
                status = False
    return status
 
p=[]
for n in range(1,2000000):
    if is_prime(n):
        p.append(n)
s = sum(p)
print(s,':sum of all the primes below two million')
```

    142913828922 :sum of all the primes below two million


**Challenge 3: Multiples of 3 and 5**

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23. Find the sum of all the multiples of 3 or 5 below 1000.


```python
sum = 0
for i in range(1,1000):
    if i%3 == 0 or i%5 == 0:
        sum +=i
print(sum)        
        
```

    233168


**Challenge 4: Fizz Buzz**
Write a program that prints all the numbers from 1 to 100. For multiples of 3, instead of the number, print "Fizz", for multiples of 5 print "Buzz". For numbers which are multiples of both 3 and 5, print "FizzBuzz". Bonus: If that's too easy, create three unique solutions. Sometimes you'll encounter unexpected constraints, so make sure you're able to think creatively!



```python
for i in range(1,101):
    if i%3 == 0 and i%5 == 0:
        print('Number',i,': FizzBuzz')
    elif i%3 == 0:
        print('Number',i,': Fizz')
    elif i%5 == 0:
        print('Number',i,': Buzz')
    else:
        print('Number',i)
    
              
```

    Number 1
    Number 2
    Number 3 : Fizz
    Number 4
    Number 5 : Buzz
    Number 6 : Fizz
    Number 7
    Number 8
    Number 9 : Fizz
    Number 10 : Buzz
    Number 11
    Number 12 : Fizz
    Number 13
    Number 14
    Number 15 : FizzBuzz
    Number 16
    Number 17
    Number 18 : Fizz
    Number 19
    Number 20 : Buzz
    Number 21 : Fizz
    Number 22
    Number 23
    Number 24 : Fizz
    Number 25 : Buzz
    Number 26
    Number 27 : Fizz
    Number 28
    Number 29
    Number 30 : FizzBuzz
    Number 31
    Number 32
    Number 33 : Fizz
    Number 34
    Number 35 : Buzz
    Number 36 : Fizz
    Number 37
    Number 38
    Number 39 : Fizz
    Number 40 : Buzz
    Number 41
    Number 42 : Fizz
    Number 43
    Number 44
    Number 45 : FizzBuzz
    Number 46
    Number 47
    Number 48 : Fizz
    Number 49
    Number 50 : Buzz
    Number 51 : Fizz
    Number 52
    Number 53
    Number 54 : Fizz
    Number 55 : Buzz
    Number 56
    Number 57 : Fizz
    Number 58
    Number 59
    Number 60 : FizzBuzz
    Number 61
    Number 62
    Number 63 : Fizz
    Number 64
    Number 65 : Buzz
    Number 66 : Fizz
    Number 67
    Number 68
    Number 69 : Fizz
    Number 70 : Buzz
    Number 71
    Number 72 : Fizz
    Number 73
    Number 74
    Number 75 : FizzBuzz
    Number 76
    Number 77
    Number 78 : Fizz
    Number 79
    Number 80 : Buzz
    Number 81 : Fizz
    Number 82
    Number 83
    Number 84 : Fizz
    Number 85 : Buzz
    Number 86
    Number 87 : Fizz
    Number 88
    Number 89
    Number 90 : FizzBuzz
    Number 91
    Number 92
    Number 93 : Fizz
    Number 94
    Number 95 : Buzz
    Number 96 : Fizz
    Number 97
    Number 98
    Number 99 : Fizz
    Number 100 : Buzz


**Challenge 5: String Compressor**

Implement a method to perform basic string compression using the counts of repeated characters. For example, the string 'aabcccccaaa' would become a2b1c5a3. If the “compressed” string would not become smaller than the original string, your method should return the original string. You can assume the string has only uppercase and lowercase letters (a-z). Specify whether your solution is case sensitive or insensitive, and what you would need to change to make it the other.


```python
def str_compress(input_string):
    new_string= ""
    count = 1
    new_string += input_string[0]
    for i in range(len(input_string)-1):
        if(input_string[i] == input_string[i+1]):
            count+=1
        else:
            if(count > 1):
                new_string += str(count)
            new_string += input_string[i+1]
            count = 1
    if(count > 1):
        new_string += str(count)
    if len(new_string) == len(input_string):
        return input_string
    else:
        return new_string 
print(str_compress('prEEthi'))
print(str_compress('aabcccccaaa'))
```

    prEEthi
    a2bc5a3

