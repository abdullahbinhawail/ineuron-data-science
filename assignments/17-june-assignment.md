
## 17-June-Assignment

1. What is the role of try and exception block ?
Answer :

 Sure, here is the role of try and except block in Python:

- The try block is used to test a block of code for errors.
- The except block is used to handle the error if it occurs.
- The try and except blocks allow you to gracefully handle    errors in Python and prevent your program from crashing.

2. What is the syntax for a basic try-except block ?
 Answer :

- The try block contains the code that we want to try to run. If the code in the try block runs without any errors, then the except block will not be executed. However, if the code in the try block raises an exception, then the except block will be executed. The except block contains the code that we want to run if an exception is raised.

Sure, here is the syntax for a basic try-except block in Python:

```
try:
  print(10 / 0)
except ZeroDivisionError:
  print("You can't divide by zero!")
```

3. What happens if an exception occurs inside a try block and there is no matching except block ?
Answer :


- If an exception occurs inside a try block and there is no matching except block, the exception will be re-raised. This means that the exception will be passed to the next outer try block, or to the Python interpreter if there are no more try blocks.

4. What is the difference between using a bare except block and specifying a specific exception type ?

Answer :

The difference between using a bare except block and specifying a specific exception type :
- A bare except block catches all exceptions.
- Specifying a specific exception type catches only that specific exception type.
- It is generally a good practice to specify the specific exception type that you want to catch.
- Using a bare except block can make your code less readable and less robust.


5. Can you have nested try-except blocks in Python? If yes, then give an example.

Answer :


- Yes, you can have nested try-except blocks in Python. Nested try-except blocks are simply try-except blocks that are nested inside of other try-except blocks.

For example, the following code has two nested try-except blocks :
```
try:
    try:
        age = [1, 6, 8, 10]
        print(age[5])
    except IndexError:
        print('the index number are Not there')
    except:
        print('an unknown error occured')
except:
    print("problem occured !!")
```

6. Can we use multiple exception blocks, if yes then give an example.
Answer :

- Sure, you can use multiple exception blocks in Python. This can be useful if you want to handle multiple types of exceptions in the same try block.

For example, the following code uses multiple exception blocks to handle the ZeroDivisionError exception and the ValueError exception:
```
try:
  print(10 / 0)
except ZeroDivisionError:
  print("You can't divide by zero!")
except ValueError:
  print("The value is not a number!")
```

7. Write the reason due to which following errors are raised:
- a. EOFError
- b. FloatingPointError
- c. IndexError
- d. MemoryError
- e. OverflowError
- f. TabError
- g. ValueError

Answer :

- a. EOFError

The EOFError exception is raised when the input() or raw_input() function hits the end-of-file condition without actually reading any data. This can happen if the user presses Ctrl+D or Delete in the console, or if the file being read is empty.

- b. FloatingPointError

The FloatingPointError exception is raised when a floating point operation fails. This can happen if the operation is mathematically impossible, such as dividing by zero, or if the result of the operation is too large or too small to be represented as a floating point number.

- c. IndexError

The IndexError exception is raised when the index of a sequence is out of range. This can happen if you try to access an element of a list or string that does not exist, or if you try to slice a list or string with a start or end index that is out of range.

- d. MemoryError

The MemoryError exception is raised when an operation runs out of memory. This can happen if you are trying to allocate too much memory, or if you are running a program that is very memory-intensive.

- e. OverflowError

The OverflowError exception is raised when the result of an arithmetic operation is too large to be represented. This can happen if you try to add two very large numbers together, or if you try to divide a very small number by a very small number.

- f. TabError

The TabError exception is raised when the indentation of a Python program is inconsistent. This can happen if you mix tabs and spaces in your code, or if you use different numbers of tabs or spaces for different levels of indentation.

- g. ValueError

The ValueError exception is raised when a function gets an argument of correct type but improper value. This can happen if you try to pass a string to a function that expects an integer, or if you try to pass an integer to a function that expects a float.



8. Write code for the following given scenario and add try-exception block to it.
- a. Program to divide two numbers
- b. Program to convert a string to an integer
- c. Program to access an element in a list
- d. Program to handle a specific exception
- e. Program to handle any exception

Answer :

- a. Program to divide two numbers
```
def MyDivide(x, y):
    try:
        return x / y
    except ZeroDivisionError:
        print("the numerator cannot divide by zero")

print(MyDivide(15, 8))
print(MyDivide(5, 0))
```

- b. Program to convert a string to an integer
```
def convert_string_to_integer(string):
    try:
        return int(string)
    except ValueError:
        print('the string cannot convert to integer')
        
print(convert_string_to_integer("10"))
print(convert_string_to_integer("hello"))
```

- c. Program to access an element in a list
```
lst = [1, 3, 7, 9]
def access_element(lst, index):
    try:
        return lst[index]
    except IndexError:
        print('the index is out of the range')
        
print(access_element(lst, 2))
print(access_element(lst, 5))
```

- d. Program to handle a specific exception
```
def specific_exception(number):
    try:
        if number == 0:
            raise ValueError("the number cannot be zero")
        return number
    except ValueError:
        print("the ValueError exception was raised...")
        
        
print(specific_exception(70))
print(specific_exception(0))
```

- e. Program to handle any exception
```
def handle_any_exception(num):
    try:
        return num
    except Exception as e:
        print("An error occured:", e)
    
print(handle_any_exception(10))
print(handle_any_exception(0))
```
