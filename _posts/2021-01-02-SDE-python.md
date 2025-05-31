---
layout: post
title: Python - python
date: 2021-01-02 12:18 +0800
tags: [python]
toc:  true
---

<!-- Global site tag (gtag.js) - Google Analytics -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-TG0XJZG53F"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());

    gtag('config', 'G-TG0XJZG53F');
  </script>


#### Run a file

```pyhon
C:\Users\joy3l>cd "C:\Users\joy3l\Desktop\Exercise Files\Chap01"

C:\Users\joy3l\Desktop\Exercise Files\Chap01>dir
 Volume in drive C is OS
 Volume Serial Number is 2C95-528B

 Directory of C:\Users\joy3l\Desktop\Exercise Files\Chap01

2021/07/07  15:42    <DIR>          .
2021/07/07  15:42    <DIR>          ..
2021/07/07  15:42                21 01_03.py
               1 File(s)             21 bytes
               2 Dir(s)  856,122,343,424 bytes free

C:\Users\joy3l\Desktop\Exercise Files\Chap01>python 01_03.py
Hello world!
```

### HelloWorld
```python
def main():
    print("hello world!")
    name = input("What is your name? ")
    print("Nice to meet you,", name)

if __name__ == "__main__":
    main()
```
> hello world! <br />
  What is your name? ***joe*** <br />
  Nice to meet you, joe

### Variables and expressions

```python
# Declare a variable and initialize it
f = 0
print (f)
```
> 0

```python
# re-declaring the variable works
f = "abc"
print (f)
```
> abc

```python
# ERROR: variables of different types cannot be combined
#print ("string type " + 123)
print ("string type " + str(123))
```
> string type 123

```python
# Global vs. local variables in functions
def someFunction():
  #global f
  f = "def"
  print (f)

someFunction()
print (f)
```
> def <br />
  abc

```python
# Global vs. local variables in functions
def someFunction():
  global f
  f = "def"
  print (f)

someFunction()
print (f)
```
> def <br />
  def

```python
del f
print (f)
```
> NameError: name 'f' is not defined

---

### Format Strings in Python

String interpolation (f-strings)

Introduced in Python 3.6, f-strings are a new way to format strings in Python. They are prefixed with 'f' and use curly braces {} to enclose the variables that will be formatted. For example:

```python
name = "John"
age = 30
print(f"My name is {name} and I am {age} years old.")
```
> My name is John and I am 30 years old.

str.format()

This is another way to format strings in Python. It uses curly braces {} as placeholders for variables which are passed as arguments in the format() method. For example:

```python
name = "John"
age = 50
print("My name is {} and I am {} years old.".format(name, age))
```
> My name is John and I am 50 years old.

% Operator

This is one of the oldest ways to format strings in Python. It uses the % operator to replace variables in the string. For example:

```python
name = "Johnathan"
age = 30
print("My name is %s and I am %d years old." % (name, age))
```
> My name is Johnathan and I am 30 years old.

Additional capabilities

F-strings are also able to evaluate expressions inside the curly braces, which can be very handy. For example:

```python
x = 10
y = 20
print(f"The sum of x and y is {x+y}.")
```
> The sum of x and y is 30.

Raw String (r’’)

In Python, raw strings are a powerful tool for handling textual data, especially when dealing with escape characters. By prefixing a string literal with the letter ‘r’, Python treats the string as raw, meaning it interprets backslashes as literal characters rather than escape sequences.

Consider the following examples of regular string and raw string:

```python
regular_string = "C:\new_folder\file.txt"
print("Regular String:", regular_string)
```
> Regular String:  C:
  ew_folderile.txt

In the regular string regular_string variable, the backslashes (\n) are interpreted as escape sequences. Therefore, \n represents a newline character, which would lead to an incorrect file path representation.

Raw string:

```python
raw_string = r"C:\new_folder\file.txt"
print("Raw String:", raw_string)
```
> Raw String: C:\new_folder\file.txt

However, in the raw string raw_string, the backslashes are treated as literal characters. This means that \n is not interpreted as a newline character, but rather as two separate characters, \ and n. Consequently, the file path is represented exactly as it appears.

Consider the variable <code>g</code>, and find the first index of the sub-string <code>snow</code>:

```python
g = "Mary had a little lamb Little lamb, little lamb Mary had a little lamb \
Its fleece was white as snow And everywhere that Mary went Mary went, Mary went \
Everywhere that Mary went The lamb was sure to go"

g.find("snow")
```

In the variable <code>g</code>, replace the sub-string <code>Mary</code> with <code>Bob</code>:

```python
g.replace("Mary", "Bob")
```

In the variable <code>g</code>, replace the sub-string <code>,</code> with <code>.</code>:

```python
g.replace(',','.')
```

In the variable <code>g</code>, split the substring to list:

```python
g.split()
```

In the string <code>s3</code>, find whether the digit is present or not using the <code>\d</code> and <code>search() </code>function:

```python
s3 = "House number- 1105"

# Use the search() function to search for the "\d" in the string
result = re.search(r"\d", s3)

# Check if a match was found
if result:
    print("Digit found")
else:
    print("Digit not found.")
```

In the string <code>str1</code>, replace the sub-string <code>fox</code> with <code>bear</code> using <code>sub() </code>function:

```python
str1= "The quick brown fox jumps over the lazy dog."

# Use re.sub() to replace "fox" with "bear"
new_str1 = re.sub(r"fox", "bear", str1)

print(new_str1)
```

In the string <code>str2</code> find all the occurrences of <code>woo</code> using <code>findall()</code> function:

```python
str2= "How much wood would a woodchuck chuck, if a woodchuck could chuck wood?"

# Use re.findall() to find all occurrences of "woo"
matches = re.findall(r"woo", str2)

print(matches)
```
---

#### RegEx

In Python, RegEx (short for Regular Expression) is a tool for matching and handling strings.

This RegEx module provides several functions for working with regular expressions, including <code>search, split, findall,</code> and <code>sub</code>.


Python provides a built-in module called <code>re</code>, which allows you to work with regular expressions.
First, import the <code>re</code> module

```python
import re
```

The search() function searches for specified patterns within a string. Here is an example that explains how to use the search() function to search for the word "Body" in the string "The BodyGuard is the best".

```python
s1 = "The BodyGuard is the best album"

# Define the pattern to search for
pattern = r"Body"

# Use the search() function to search for the pattern in the string
result = re.search(pattern, s1)

# Check if a match was found
if result:
    print("Match found!")
else:
    print("Match not found.")
```
> Match found!

Regular expressions (RegEx) are patterns used to match and manipulate strings of text. There are several special sequences in RegEx that can be used to match specific characters or patterns

| Special Sequence | Meaning                 | 	Example             |
| -----------  | ----------------------- | ----------------------|
| \d|Matches any digit character (0-9)|"123" matches "\d\d\d"|
|\D|Matches any non-digit character|"hello" matches "\D\D\D\D\D"|
|\w|Matches any word character (a-z, A-Z, 0-9, and _)|"hello_world" matches "\w\w\w\w\w\w\w\w\w\w\w"|
|\W|Matches any non-word character|	"@#$%" matches "\W\W\W\W"|
|\s|Matches any whitespace character (space, tab, newline, etc.)|"hello world" matches "\w\w\w\w\w\s\w\w\w\w\w"|
|\S|Matches any non-whitespace character|"hello_world" matches "\S\S\S\S\S\S\S\S\S\S\S"|
|\b|Matches the boundary between a word character and a non-word character|"cat" matches "\bcat\b" in "The cat sat on the mat"|
|\B|Matches any position that is not a word boundary|"cat" matches "\Bcat\B" in "category" but not in "The cat sat on the mat"|

Special Sequence Examples:

A simple example of using the <code>\d</code> special sequence in a regular expression pattern with Python code:

```python
pattern = r"\d\d\d\d\d\d\d\d\d\d"  # Matches any ten consecutive digits
text = "My Phone number is 1234567890"
match = re.search(pattern, text)

if match:
    print("Phone number found:", match.group())
else:
    print("No match")
```
> Phone number found: 1234567890

The match.group() method is used in Python's re module to retrieve the part of the string where the regular expression pattern matched. Here's a detailed explanation:

**Purpose**
- Extract Matched Text: match.group() returns the exact substring that matched the pattern.

**Usage**
- When you use functions like re.search() or re.match(), they return a match object if the pattern is found. You can then use match.group() to get the matched text.

Here `match.group()` retrieves the substring 1234567890 from the text, which is the part that matched the pattern.

The regular expression pattern is defined as r"\d\d\d\d\d\d\d\d\d\d", which uses the \d special sequence to match any digit character (0-9), and the \d sequence is repeated ten times to match ten consecutive digits

A simple example of using the <code>\W</code> special sequence in a regular expression pattern with Python code:


```python
pattern = r"\W"  # Matches any non-word character
text = "Hello, world!"
matches = re.findall(pattern, text)

print("Matches:", matches)
```
> Matches: [',', ' ', '!']

The regular expression pattern is defined as r"\W", which uses the \W special sequence to match any character that is not a word character (a-z, A-Z, 0-9, or _). The string we're searching for matches in is "Hello, world!".

The <code>findall()</code> function finds all occurrences of a specified pattern within a string.

```python
s2 = "The BodyGuard is the best album of 'Whitney Houston'."

# Use the findall() function to find all occurrences of the "st" in the string
result = re.findall("st", s2)

# Print out the list of matched words
print(result)
```
> ['st', 'st']

A regular expression's <code>split()</code> function splits a string into an array of substrings based on a specified pattern.


```python
s2 = "The BodyGuard is the best album of 'Whitney Houston'."

# Use the split function to split the string by the "\s"
split_array = re.split(r"\s", s2)

# The split_array contains all the substrings, split by whitespace characters
print(split_array)
```
> ['The', 'BodyGuard', 'is', 'the', 'best', 'album', 'of', "'Whitney", "Houston'."]

Here's a detailed explanation:

<code>re.split("\s", s2)</code>:

**re.split**: This function splits a string by the occurrences of a pattern.
- **r"\s"**: This is a regular expression pattern that matches any whitespace character (spaces, tabs, newlines, etc.).
- **s2**: This is the string that you want to split.

The <code>sub</code> function of a regular expression in Python is used to replace all occurrences of a pattern in a string with a specified replacement.


```python
s2 = "The BodyGuard is the best album of 'Whitney Houston'."

# Define the regular expression pattern to search for
pattern = r"Whitney Houston"

# Define the replacement string
replacement = "legend"

# Use the sub function to replace the pattern with the replacement string
new_string = re.sub(pattern, replacement, s2, flags=re.IGNORECASE)

# The new_string contains the original string with the pattern replaced by the replacement string
print(new_string)
```
> The BodyGuard is the best album of 'legend'.

---

### Functions

```python
# define a basic function
def func1():
    print("I am a function")

func1()
print(func1())
print(func1)
```
> I am a function <br />
  I am a function <br />
  None

```python
# function that takes arguments
def func2(arg1, arg2):
    print(arg1, " ", arg2)

func2(10, 20)
print(func2(10, 20))
```
> 10   20 <br />
  10   20

```python
# function that returns a value
def cube(x):
    return x*x*x

print(cube(3))
```
> 27

```python
# function with default value for an argument
def power(num, x=1):
    result = 1
    for i in range(x):
        result = result * num
    return result

print(power(2))
print(power(2, 3))
print(power(x=3, num=2))
```
> 2 <br />
  8 <br />
  8 <br />

```python
# function with variable number of arguments
def multi_add(*args):
    result = 0
    for x in args:
        result = result + x
    return result

print(multi_add(4, 5, 10, 4))
```
> 23

### Conditional statements

```python
def main():
    x, y = 10, 100

    # conditional flow uses if, elif, else
    if(x < y):
        st = "x is less than y"
    elif (x == y):
        st = "x is same as y"
    else:
        st = "x is greater than y"
    print(st)

    # conditional statements let you use "a if C else b"
    st = "x is less than y" if (x < y) else "x is greater than or equal to y"
    print(st)

    # Python does not have support for higher-order conditionals
    # like "switch-case" in other languages


if __name__ == "__main__":
    main()
```
> x is less than y <br />
  x is less than y

### Loops

```python
def main():
  x = 0

  # define a while loop
  while (x < 5):
     print (x)
     x = x + 1

if __name__ == "__main__":
  main()
```
> 0 <br />
  1 <br />
  2 <br />
  3 <br />
  4 <br />

```python
  # define a for loop
  for x in range(5,10):
    print (x)

if __name__ == "__main__":
  main()
```  
> 5 <br />
  6 <br />
  7 <br />
  8 <br />
  9 <br />

```python
  # use a for loop over a collection
  days = ["Mon","Tue","Wed","Thu","Fri","Sat","Sun"]
  for d in days:
    print (d)

if __name__ == "__main__":
  main()
```
> Mon <br />
  Tue <br />
  Wed <br />
  Thu <br />
  Fri <br />
  Sat <br />
  Sun <br />

```python
  # use the break and continue statements
  for x in range(5,10):
    if (x == 7): break
    print (x)

if __name__ == "__main__":
  main()
```
> 5 <br />
  6

```python
  # use the break and continue statements
  for x in range(5,10):
    if (x % 2 == 0): continue
    print (x)

if __name__ == "__main__":
  main()
```
> 5 <br />
  7 <br />
  9 <br />

```python
  #using the enumerate() function to get index
  days = ["Mon","Tue","Wed","Thu","Fri","Sat","Sun"]
  for i, d in enumerate(days):
    print (i, d)

if __name__ == "__main__":
  main()
```
> 0 Mon <br />
  1 Tue <br />
  2 Wed <br />
  3 Thu <br />
  4 Fri <br />
  5 Sat <br />
  6 Sun <br />

Q: Return the sum of the first item in the data list and every tenth item after?

A:
```python
def Sum10th(data):
  sum=0
  for i,d in enumerate(data):
    if (i % 10 == 0): sum=sum+d
  return sum
```

Q: Print the number of digits in the number variable? You can assume this number is always positive and always less than 10,000.

A:
```python
if (number>=1000):
  print(4)
elif (number>=100):
  print(3)
elif (number>=10):
  print(2)
else:
  print(1)
```
### Classes

```python
class myClass():
    def method1(self):
        print("myClass method1")

    def method2(self, someString):
        print("myClass method2: " + someString)

def main():
    c = myClass()
    c.method1()
    c.method2("This is a string")

if __name__ == "__main__":
    main()
```
> myClass method1 <br />
  myClass method2: This is a string


```python
class myClass():
    def method1(self):
        print("myClass method1")

    def method2(self, someString):
        print("myClass method2: " + someString)


class anotherClass(myClass):
   def method1(self):
        myClass.method1(self)
        print("myClass method1")

    def method2(self, someString):
        print("myClass method2 ")


def main():
    c = myClass()
    c.method1()
    c.method2("This is a string")

    c2 = anotherClass()
    c2.method1()
    c2.method2("This is a string")


if __name__ == "__main__":
    main()
```
> myClass method1 <br />
  myClass method2: This is a string <br />
  myClass method1 <br />
  anotherClass method1 <br />
  anotherClass method2

```python
class Advanced(Simple):
  def Inverse(self,x,y):
    return (1/Simple.Add(self,x,y))
```

Q: You have an existing class Simple() that returns the sum of two numbers using its Add(x,y) method. How can you leverage it to build another class that calculates the inverse of the sum of two numbers?

A:
```python
class Simple():
  def Add(self,x,y):
      return (x + y)

class Advanced(Simple):
  def Inverse(self,x,y):
      Simple.Add(self,x,y)
      print (1/Simple.Add(self,x,y))

def main():
    c = Advanced()
    c.Inverse(1,2)

if __name__ == "__main__":
    main()
```
> 0.3333333333333333

Q: In Python, what is the correct way to develop a class called Person that has parameters in the initialize function called name, age, and sex?

A:
```python
class Person:
  def __initialize__(self, name, age, sex):
    self.name = name
    self.age = age
    self.sex = sex   
```

Q: You need to set the annual payment in one function and print the respective monthly payment in a separate function. How would you fix the suggested code to work properly?

A:
```python
def SetAnnual():
  global annual
  annual=10000
def PrintMonthly():
  print("Your monthly payment is "+str(annual/12)+" USD.")
SetAnnual()
PrintMonthly()
```

### Modules
```python
# import the math module, which contains features for working with mathematics
import math

# the math module contains lots of pre-built functions
print("The square root of 16 is", math.sqrt(16))

# in addition to functions, some modules contain useful constants
print("Pi is:", math.pi)

# try some of the math functions for yourself here:
```
> The square root of 16 is 4.0 <br />
  Pi is: 3.141592653589793

### Date information

```python
from datetime import date
from datetime import time
from datetime import datetime

def main():
  ## DATE OBJECTS
  # Get today's date from the simple today() method from the date class
  today = date.today()
  print ("Today's date is ", today)

  # print out the date's individual components
  print ("Date Components: ", today.day, today.month, today.year)

  # retrieve today's weekday (0=Monday, 6=Sunday)
  print ("Today's Weekday #: ", today.weekday())
  days = ["monday","tuesday","wednesday","thursday","friday","saturday","sunday"]
  print ("Which is a " + days[today.weekday()])

  ## DATETIME OBJECTS
  # Get today's date from the datetime class
  today = datetime.now()
  print  ("The current date and time is ", today)

  # Get the current time
  t = datetime.time(datetime.now())
  print ("The current time is ", t)


if __name__ == "__main__":
  main();
```
> Today's date is  2021-07-09 <br />
  Date Components:  9 7 2021 <br />
  Today's Weekday #:  4 <br />
  Which is a friday <br />
  The current date and time is  2021-07-09 14:15:32.017705 <br />
  The current time is  14:15:32.017705 <br />

### Date output

```python
from datetime import datetime

def main():
  # Times and dates can be formatted using a set of predefined string
  # control codes
  now = datetime.now() # get the current date and time

  #### Date Formatting ####

  # %y/%Y - Year, %a/%A - weekday, %b/%B - month, %d - day of month
  print (now.strftime("The current year is: %Y")) # full year with century
  print (now.strftime("%a, %d %B, %y")) # abbreviated day, num, full month, abbreviated year

  # %c - locale's date and time, %x - locale's date, %X - locale's time
  print (now.strftime("Locale date and time: %c"))
  print (now.strftime("Locale date: %x"))
  print (now.strftime("Locale time: %X"))

  #### Time Formatting ####

  # %I/%H - 12/24 Hour, %M - minute, %S - second, %p - locale's AM/PM
  print (now.strftime("Current time: %I:%M:%S %p")) # 12-Hour:Minute:Second:AM
  print (now.strftime("24-hour time: %H:%M")) # 24-Hour:Minute


if __name__ == "__main__":
  main();
```
> The current year is: 2021 <br />
  Fri, 09 July, 21 <br />
  Locale date and time: Fri Jul  9 14:20:47 2021 <br />
  Locale date: 07/09/21 <br />
  Locale time: 14:20:47 <br />
  Current time: 02:20:47 PM <br />
  24-hour time: 14:20 <br />

### Timedelta objects
```python
from datetime import date
from datetime import time
from datetime import datetime
from datetime import timedelta

# construct a basic timedelta and print it
print (timedelta(days=365, hours=5, minutes=1))

# print today's date
now = datetime.now()
print ("today is: " + str(now))

# print today's date one year from now
print ("one year from now it will be: " + str(now + timedelta(days=365)))

# create a timedelta that uses more than one argument
print ("in two weeks and 3 days it will be: " + str(now + timedelta(weeks=2, days=3)))

# calculate the date 1 week ago, formatted as a string
t = datetime.now() - timedelta(weeks=1)
s = t.strftime("%A %B %d, %Y")
print ("one week ago it was " + s)

### How many days until April Fools' Day?

today = date.today()  # get today's date
afd = date(today.year, 4, 1)  # get April Fool's for the same year
# use date comparison to see if April Fool's has already gone for this year
# if it has, use the replace() function to get the date for next year
if afd < today:
  print ("April Fool's day already went by %d days ago" % ((today-afd).days))
  afd = afd.replace(year=today.year + 1)  # if so, get the date for next year

# Now calculate the amount of time until April Fool's Day  
time_to_afd = afd - today
print ("It's just", time_to_afd.days, "days until next April Fools' Day!")
```
> 365 days, 5:01:00 <br />
  today is: 2021-07-09 14:48:10.070308 <br />
  one year from now it will be: 2022-07-09 14:48:10.070308 <br />
  in two weeks and 3 days it will be: 2021-07-26 14:48:10.070308 <br />
  one week ago it was Friday July 02, 2021 <br />
  April Fool's day already went by 99 days ago <br />
  It's just 266 days until next April Fools' Day! <br />

### Calendars
```python
import calendar

# create a plain text calendar
c = calendar.TextCalendar(calendar.SUNDAY)
str = c.formatmonth(2017, 1, 0, 0)
print (str)

# create an HTML formatted calendar
hc = calendar.HTMLCalendar(calendar.SUNDAY)
str = hc.formatmonth(2017, 1)
print (str)

# loop over the days of a month
# zeroes mean that the day of the week is in an overlapping month
for i in c.itermonthdays(2017, 8):
  print (i)

# The Calendar module provides useful utilities for the given locale,
# such as the names of days and months in both full and abbreviated forms
for name in calendar.month_name:
  print (name)

for day in calendar.day_name:
  print (day)

# Calculate days based on a rule: For example, consider
# a team meeting on the first Friday of every month.
# To figure out what days that would be for each month,
# we can use this script:
print ("Team meetings will be on:")
for m in range(1,13):
  # returns an array of weeks that represent the month
  cal = calendar.monthcalendar(2017, m)
  # The first Friday has to be within the first two weeks
  weekone = cal[0]
  weektwo = cal[1]

  if weekone[calendar.FRIDAY] != 0:
    meetday = weekone[calendar.FRIDAY]
  else:
    # if the first friday isn't in the first week, it must be in the second
    meetday = weektwo[calendar.FRIDAY]

  print ("%10s %2d" % (calendar.month_name[m], meetday))

```
> January 2017 <br />
  Su Mo Tu We Th Fr Sa <br />
  1  2  3  4  5  6  7 <br />
  8  9 10 11 12 13 14 <br />
  15 16 17 18 19 20 21 <br />
  22 23 24 25 26 27 28 <br />
  29 30 31 <br />
  Team meetings will be on: <br />
     January  6 <br />
    February  3 <br />
       March  3 <br />
       April  7 <br />
         May  5 <br />
        June  2 <br />
        July  7 <br />
      August  4 <br />
   September  1 <br />
     October  6 <br />
    November  3 <br />
    December  1 <br />

### Built-in Python file methods

```python
def main():  
  # Open a file for writing and create it if it doesn't exist
  f = open("textfile.txt","w+")

  # Open the file for appending text to the end
  # f = open("textfile.txt","a+")

  # write some lines of data to the file
  for i in range(10):
    f.write("This is line %d\r\n" % (i+1))

  # close the file when done
  f.close()

  # Open the file back up and read the contents
  f = open("textfile.txt","r")
  if f.mode == 'r': # check to make sure that the file was opened
    # use the read() function to read the entire file
    # contents = f.read()
    # print (contents)

    fl = f.readlines() # readlines reads the individual lines into a list
    for x in fl:
      print (x)

if __name__ == "__main__":
  main()

```
