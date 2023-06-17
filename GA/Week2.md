# Graded Assignment 1

Q1)
```python
def fun(S):
  p=0
  S=S.lower()
  for i  in range(len(S)):
      if S[i] not in S[:i}:
          p+=1
  return p
 ```
 S is a non -empty string of English Letters without any space. What fun(S) will return after execution of the above code?
 </br></br>
A1) Total number of distinct letters in the string S.
__________________________________________________________________________________________________________________________
Q2) Which of the following is/are valid reason(s) for NameError exception?
- [ ] Variable is not defined.
- [ ] Calling a function before declaration.
- [ ] Misspelled bulit-in functions name
- [ ] Variables are defined globally in the program.
 </br></br>
 
 A2)
- [x] Variable is not defined.
- [x] Calling a function before declaration.
- [x] Misspelled bulit-in functions name.
__________________________________________________________________________________________________________________________
Q3)
```python
def f(n):
    s = 0
    for i in range(2,n):
        if n % i == 0 and i % 2 == 1:
            s = s + 1
    return(s)
 ```
What is f(60) - f(59), given the definition of f above?
</br></br>
A3) **3**</br>
Function f(n) returns the number of odd factors of n between 1 and n (1 and n are not included). Here f(60) return 3(3, 5, 15) and f(59) return 0 because it is a prime number. So the value of f(60) - f(59) is 3.
__________________________________________________________________________________________________________________________
Q4)
```python
x = 1
while True:
    if x % 5 = = 0:
        break
    print(x, end = ' ')
    x + = 1
 ```
 What will be the output of the above code-snippet?
 </br></br>
A4) Syntax error
__________________________________________________________________________________________________________________________
Q5)
```python
class Person:
    def __init__(self, name):
        self.name = name
    def say_hi(self):
        print('Hello, ', self.name)
 
p = Person('Good morning')
p.say_hi()
 ```
 What will be the output of the above code-snippet?
 </br></br>
A5) Hello, Good morning
__________________________________________________________________________________________________________________________
Q6)
```python
a = [1, 2, 3]
try:
    print ("Second element = %d" %(a[1))
    print ("Fourth element = %d" %(a[3))
except:
    print ("An error occurred")
 ```
 What will be the output of the above code-snippet?
 </br></br>
A6)

> Second element = 2</br>
> An error occurred
__________________________________________________________________________________________________________________________
Q7)
```python
def special3Bad(L):
  try:
      if L[0] % L[1] == 0 and L[1] != 0:
        if L[0] / (L[1] ** 2 - L[2]) == 0:
          return True
      return False
  except ZeroDivisionError:
    print('ZeroDivisionError')
  except:
    print('Some other exception occurred')
  else:
    print('No exception occurred')
special3Bad(L)
 ```
Given above is a function that checks whether a list satisfies some property. There is an error in this function. Select the list(s) L =[n1, n2, n3], where n1, n2 and n3 are all integers,for which special3Bad(L) produces a ZeroDivisonError exception. [MSQ]
 </br></br>
A7)
- [x] L =[4, 2, 4]
- [x] L =[8, 4, 16]
- [x] L =[48, 6, 36]
__________________________________________________________________________________________________________________________
Q8)
```python
def isSymmetricBad(L):
  try:
    while len(L) > 0:
      if L.pop(0) != L.pop(-1):
          return False
      return True
  except IndexError:
    print('IndexError')
  except:
    print('Some other exception occurred')
  else:
    print('No exception occurred')
isSymmetricBad(L)
 ```
Given above is a function that checks whether a list is a palindrome. There is an error in this function. Select the list(s) L =[n1,n2,....,n2,n1], for which isSymmetricBad(L) produces an IndexError exception.[MSQ]
 </br></br>
A8)
- [x] L =[1,2,3,4,3,2,1]
- [x] L =[1,1,1,1,1,1,1]
- [x] L =[8]
__________________________________________________________________________________________________________________________
Q9)
```python
def gcd(m,n):
    (a,b) = (max(m,n), min(m,n))
    if a % b == 0:
        return(b)
    else:
        return(gcd(b,a % b))
print(gcd(24,130))
 ```
How many times gcd() function will be called?</br>
**Note:** Ignore the first call given in the code.
</br></br>
A9) **3**</br>
After first call, gcd(24, 10) -> gcd(10, 4) -> gcd(4, 2) -> return(2). Hence, gcd function called itself 3 times recursively.
__________________________________________________________________________________________________________________________
Q10)
```python
class Enrollment:
    count = 0
    def __init__(self,n,c):
        self.name = n
        self.course = c
        Enrollment.count += 1
    def display(self):
        print(self.name)
        print(self.course)
 ```
Which of the following option(s) is /are correct about the given code? [MSQ]
 </br></br>
A10)
- [x] name and course are object variables, and count is a class variable.
- [x] count represents the number of objects created for class Enrollment.
__________________________________________________________________________________________________________________________
