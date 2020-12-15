## What's new in Python 3.9
## What's new in Python 3.8

- [Awesome New Features in Python 3.8](https://www.geeksforgeeks.org/awesome-new-features-in-python-3-8/)
- [What's new in Python 3.8](https://deepsource.io/blog/python-3-8-whats-new/)
- [Cool New Features in Python 3.8](https://realpython.com/python38-new-features/)
- [What’s New In Python 3.8](https://docs.python.org/3/whatsnew/3.8.html)

### f-string

```py
# old way
sen = 'welcome to python'
print(f'Guido says, {sen}')

# new way
print(f'Sum is: {(sum := (num := 10))}')
print(sum)  # 10 and it's exist somewhere
print(f'Sum + 2: {(sum := sum + 2)}')

# old way
number = 2020
print(f'number is: {number}')

# new way
# print(f'{number is = }')  SyntaxError [Invalid Syntax]
# print(f'{is number = }')  SyntaxError [Invalid Syntax]
print(f'{number = }')  # 2020
print(f'{(sum := 2 + 2) =}')  # only variable is allowed, otherwise SyntaxError
```

### Math module

```py
# math.prod(obj) [return the all numbers product]
print(math.prod(numbers := [1, 2, 3, 4, 5]))  # prod means 1 * 2 * 3 * 4 * 5 = 120

# math.isqrt() [return integer part of square root]
print(math.sqrt(x := 17))  # 4.123105625617661
import statistics
import math

print(math.isqrt(x := 17))  # 4

print(f'The_sqrt of {(num := 10)} is {math.sqrt(num := 10)}')

# math.dist() [return the Euclidean distance between two points]
# math.hypot() [Multidimensional Euclidean distance from the origin to a point.]

print(math.dist((p := (24, 50, 40)), (q := (12, 25, 30))))  # 29.478805945967352
print(math.hypot(3.0, 8.0))  # 8.54400374531753

# improved statistics function
# statistics.fmean() [convert data to float and return arithmetic mean]
# statistics.geometric_mean() [convert data to float and return geometric mean]
# statistics.multimode() [Return a list of the most frequently occurring values ]
# statistics.quantiles() []

data = [10, 8, 5, 3, 1, 2, 9, 10, 5, 8]
datas = 'aaaaaaaaaaabbbbbbbbccc'
print(statistics.multimode(datas))  # ['a'] [extra look]

print(statistics.fmean(data))  # 6.1
print(statistics.geometric_mean(data))
print(statistics.multimode(data))  # [10, 8, 5]
print(statistics.quantiles(data, n=3))

x = 'l h e e e l l o'.split()
print(statistics.multimode(x))  # ['l', 'e'] [extra look]
```

### Walrus Operator

- [The Walrus Operator](https://www.youtube.com/watch?v=6uAvHOKofws&feature=emb_logo)

```py
# old way []
a = 100
print(a)  # 100

# new way with walrus operator
print(b := 99)  # 99

# another example
for num in (numbers := [10, 20, 30, 40, 50]):
    print(num)
#  print(numbers) [variable is undefined]

print(x := 10 < 25)  # True

# avoiding inefficient comprehensions with walrus []

# old 
results = []
data = [1, 7, 8, 9]

for x in data:
    result = x * 2
    if result:
        results.append(result)
        
# list comprehension
results = [x * 2 for x in data if x]

# walrus 
results = [y for x in data if (y := x * 2)]

# unnecessary variable scope []
for number in (numbers := [4 , 5, 6]):
    print(number)

# processing streams in chunks []
# old way
chunk = file.read(8192)

while chunk:
    process(chunk)
    chunk = file.read(8192)

# new way

while chunk := file.read(8192):
    process(chunk)

# wrong way
x = y = z = 0
(z := (y := (x := 0))) # Error

self.rest = []
self.rest := [] # Error

total += tax # yes
total +:= tax # no
```

### positional-only parameters

```py
# old way
# the rules is if you want to use positional and keyword arguments both
# in fn call first positional and 2nd keyword

def sum__(x, y, z):
    print(x + y + z)

sum__(1, 2, z=3)  # 6

def sum_(x, y, z):
    print(x + y + z)

sum_(5, y=8, z=10)

# some function args can be used as parameter and not only keyword then separate with \
def output(a, /, b):
    return a * b

# print(output(a = 10, b = 20))  TypeError [only b can be keyword]
print(output(10, b=20))  # 200
```

## Snippets

```py
# Create list with default value in one line

# 1d list
my_grid = [0] * 6
print(my_grid) # [0,0,0,0,0,0]

# 2d list
# create 6 x 6 matrix
my2d_grid = [[0 for j in range(6)] for i in range(6)]
print(my2d_grid)
```

```py
# Find the Factors of a Number

f = 32
for i in range(1, f+1):
    if f % i == 0:
        print(i)  # 1 2 4 8 16 32
```

## Tips and Tricks

- [An A-Z of useful Python tricks](https://www.freecodecamp.org/news/an-a-z-of-useful-python-tricks-b467524ee747/)
- [To update a list in-place, use a slice-assignment](https://twitter.com/raymondh/status/1297244672759230464)
- [Top 10 Real Python Articles of 2019](https://talkpython.fm/episodes/show/244/top-10-real-python-articles-of-2019)
- [73 Examples to Help You Master Python's f-strings](https://miguendes.me/amp/73-examples-to-help-you-master-pythons-f-strings)
- [20 Useful Python Tips and Trick You Didn’t Know](https://www.blog.duomly.com/20-essential-python-tips-and-tricks-you-should-know/)
- [50+ Python 3 Tips & Tricks](https://medium.com/towards-artificial-intelligence/50-python-3-tips-tricks-e5dbe05212d7)
- [Interesting Python Tips and Tricks](https://medium.com/analytics-vidhya/interesting-python-tips-and-tricks-6d033967b5a5)
- [Python Tricks 101](https://hackernoon.com/python-tricks-101-2836251922e0)
- [10 helpful Python Tips and Tricks for Beginners](https://towardsdatascience.com/python-tips-and-tricks-for-beginners-62473d569d0a)
- [30 Magical Python Tricks to Write Better Code](https://towardsdatascience.com/30-magical-python-tricks-to-write-better-code-e54d1642c255)
- [100 Python Tips & Tricks](https://holypython.com/100-python-tips-tricks/)

```py
# don't use mutable arguments as a default parameter

def do_stuff(my_list = []):
    my_list.append('stuff!')
    return my_list
    
print(do_stuff()) # ['stuff!']
print(do_stuff()) # ['stuff!', 'stuff!']
print(do_stuff()) # ['stuff!', 'stuff!', 'stuff!']

# Do instead
def do_stuff(my_list = None):
    if my_list == None:
        my_list = []
        my_list.append('stuff!')
        
    return my_list
    
print(do_stuff()) # ['stuff!']
print(do_stuff()) # ['stuff!']
print(do_stuff()) # ['stuff!']
```

```py
# Reverse a list

list_1 = ['Shriya', 'Lavina', 'Sampreeti']
list_1.reverse() # reverse list in place
print(list_1)  # ['Sampreeti', 'Lavina','Shriya']
```

```py
# Print Elements in any Order

list_1 = [1, 2, 3]
x, y, z = list_1  # list unpacking
print(x, y, z)  # 1 2 3
print(y, z, x)  # 2 3 1
```

```py
# Generator Inside Function

result = sum(i*2 for i in range(1, 5))
print(result) # sum(2,4,6,8) == 20
```

```py
# Zip( ) function

# when we need to join many iterator objects to get a single iterator we can use zip()
Year = (1999, 2003, 2011, 2017)
Month = ["Mar", "Jun", "Jan", "Dec"]
Day = (11, 21, 13, 5)
print(list(zip(Year,Month,Day)))  # list of tuple [(1999, 'Mar', 11), ()]
```

```py
# unpacking zip()

# we can also unpack the zip file to get single iterator
Year = (1999, 2003, 2011, 2017)
Month = ["Mar", "Jun", "Jan", "Dec"]
Day = (11, 21, 13, 5)
# *zip(Year, Month, Day) [if i keep it in variable it will throw SyntaxError]
print(*zip(Year, Month, Day))  # return tuple()
new_year_2 = zip(Year, Month, Day)  # return zip object

y, m, d = zip(*new_year_2)
print(d, m, y)
```

```py
# Swap two numbers using a single line of code

x = 10
y = 20
x, y = y, x  # tuple unpacking
print(x, y)  # 20 10
```

```py
# Print a string N Times

str_1 = 'hello'
print(str_1) * 3  # hellohellohello
```

```py
# Transpose a Matrix

x = [[1, 2], [4, 5], [7, 8]]
print(list(zip(*x)))  # list of tuple [(1, 4, 7), (2, 5, 8)]
```

```py
# reverse list using slice

# it doesn't reverse the list in place, make another copy
x = [[1, 2], [4, 5], [7, 8]]
print(x[::-1]) # [[7, 8], [4, 5], [1, 2]]
```

```py
# Checking the Usage of Memory

import sys

a, b, c, d = 'wxyz'
print(sys.getsizeof(a))
print(sys.getsizeof(b))  # 26
print(sys.getsizeof(c))
print(sys.getsizeof(d))
```

## Topics need to cover in depth

Testing, Decorators, Generators, Regular Expression, Object-Oriented, Functional Programming, Debugging, Python Package, Standard Library, Data Structure, 
(sys, os, DateTime, time, numbers, math, string, collections, pprint, itertools, statistics, JSON, email) and more

## Conf Talks

- [Top 10 Must-Watch PyCon Talks](https://realpython.com/must-watch-pycon-talks/)

### Core Topics

- [Python Generators || James Powell](https://www.youtube.com/watch?v=XEn_99daJro)

### Clean Code

- [Anand Chitipothu - Writing Beautiful Code](https://www.youtube.com/watch?v=QIRyr6qvGrY)
- [Transforming Code into Beautiful, Idiomatic Python](https://www.youtube.com/watch?v=OSGv2VnC0go)
- [Beyond PEP 8 -- Best practices for beautiful intelligible code](https://www.youtube.com/watch?v=wf-BqAjZb8M)

## Framework

- [The Skills to Get a Job As a Django Developer](https://dev.to/steelwolf180/the-skills-to-get-a-job-as-a-django-developer-31ak)
