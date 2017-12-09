
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

```

    997799 :Is largest palindrome made from the product of two 3-digit numbers.


**Challenge 2: Summation of primes**

The sum of the primes below 10 is 2 + 3 + 5 + 7 = 17. Find the sum of all the primes below two million.


```python

def is_prime(n):
    status = True
    if n < 2:
        status = False
    else:
        for i in range(2,n):
            if n % i == 0:
                status = False
    return status
 
p=[]
for n in range(1,17):
    if is_prime(n):
        p.append(n)
s = sum(p)
print(s)
```


```python

def is_prime(n):
    status = True
    if n < 2:
        status = False
    else:
        for i in range(2,n):
            if n % i == 0:
                status = False
    return status
 
p=[]
for n in range(1,2000000):
    if is_prime(n):
        p.append(n)
s = sum(p)
print(s)
```

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
    
              
```

    Number 3 : Fizz
    Number 5 : Buzz
    Number 6 : Fizz
    Number 9 : Fizz
    Number 10 : Buzz
    Number 12 : Fizz
    Number 15 : FizzBuzz
    Number 18 : Fizz
    Number 20 : Buzz
    Number 21 : Fizz
    Number 24 : Fizz
    Number 25 : Buzz
    Number 27 : Fizz
    Number 30 : FizzBuzz
    Number 33 : Fizz
    Number 35 : Buzz
    Number 36 : Fizz
    Number 39 : Fizz
    Number 40 : Buzz
    Number 42 : Fizz
    Number 45 : FizzBuzz
    Number 48 : Fizz
    Number 50 : Buzz
    Number 51 : Fizz
    Number 54 : Fizz
    Number 55 : Buzz
    Number 57 : Fizz
    Number 60 : FizzBuzz
    Number 63 : Fizz
    Number 65 : Buzz
    Number 66 : Fizz
    Number 69 : Fizz
    Number 70 : Buzz
    Number 72 : Fizz
    Number 75 : FizzBuzz
    Number 78 : Fizz
    Number 80 : Buzz
    Number 81 : Fizz
    Number 84 : Fizz
    Number 85 : Buzz
    Number 87 : Fizz
    Number 90 : FizzBuzz
    Number 93 : Fizz
    Number 95 : Buzz
    Number 96 : Fizz
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
    return new_string
print(str_compress('prEEthi'))
print(str_compress('aabcccccaaa'))
```

    prE2thi
    a2bc5a3

