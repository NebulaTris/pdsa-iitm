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
x = 1
while True:
    if x % 5 = = 0:
        break
    print(x, end = ' ')
    x + = 1
 ```
 What will be the output of the above code-snippet?
 </br></br>
A6) Syntax error
__________________________________________________________________________________________________________________________
