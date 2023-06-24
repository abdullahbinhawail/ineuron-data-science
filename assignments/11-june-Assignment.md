
## 11-june-Assignment

1. What is a lambda function in Python, and how does it differ from a regular function ?

Answer :
- A lambda function is a small, anonymous function that is defined using the lambda keyword. Lambda functions are often used in conjunction with higher-order functions, such as map() and filter().

Here is an example of a lambda function:
```
square = lambda x: x * x

print(square(2))
```
- The main difference between a lambda function and a regular function is that a lambda function is defined using the lambda keyword, while a regular function is defined using the def keyword. Lambda functions are also limited in that they can only contain a single expression.


2. Can a lambda function in Python have multiple arguments? If yes, how can you define and use
them ?

Answer :
- 
Yes, a lambda function in Python can have multiple arguments. The syntax for defining a lambda function with multiple arguments is as follows:
```
lambda arg1, arg2, ...: expression
```
The following code defines a lambda function with two arguments:
```
add_two_numbers = lambda x, y: x + y

print(add_two_numbers(10, 20))
```

3. How are lambda functions typically used in Python? Provide an example use case.

Answer :

- Lambda functions are typically used in Python in conjunction with higher-order functions, such as map(), filter(), and reduce(). These functions take a function as an argument, and lambda functions are a convenient way to create short, anonymous functions that can be used as arguments to these higher-order functions.

For example, the following code uses a lambda function to map the square() function to a list of numbers:
```
numbers = [1, 2, 3, 4, 5]

squared_numbers = map(lambda x: x * x, numbers)

print(list(squared_numbers))
```

4. What are the advantages and limitations of lambda functions compared to regular functions in
Python ?

Answer :

- Here are the advantages and limitations of lambda functions compared to regular functions in Python:
Advantages:

- Conciseness: Lambda functions are very concise, which makes them easy to read and write.
- Anonymous: Lambda functions are anonymous, which means that they do not have a name. This can be useful when you need to create a function that is only used once.
- Flexibility: Lambda functions can be used as arguments to other functions, such as map() and filter(). This makes them very flexible and can be used in a variety of situations.

Limitations:

- Single expression: Lambda functions can only contain a single expression. This means that they cannot be used to create functions that are more complex than a single expression.
- No docstring: Lambda functions cannot have a docstring. This means that you cannot document the purpose of the lambda function.
- No name: Lambda functions do not have a name. This can make it difficult to debug code that uses lambda functions.

Overall, lambda functions are a powerful tool that can be used to simplify code and make it more concise. However, they do have some limitations, so it is important to be aware of these limitations when using them.


5. Are lambda functions in Python able to access variables defined outside of their own scope ?. Explain with an example.

Answer :

- Yes, lambda functions in Python can access variables defined outside of their own scope. This is because lambda functions are not actually functions in the traditional sense. They are anonymous functions that are created using the lambda keyword. Lambda functions are not objects, so they do not have their own namespace. Instead, they inherit the namespace of the scope in which they are created.

Here is an example of a lambda function that accesses a variable defined outside of its own scope:
```
x = 10

square = lambda n: n * n

print(square(x))
```

6. Write a lambda function to calculate the square of a given number.

Answer :

```
number = lambda x: x * x

print(number(5))
```
OR
```
def square_lambda(x):

  return x * x

print(square_lambda(25))
  ```

7. Create a lambda function to find the maximum value in a list of integers.

Answer :
```
def max_lambda(list_nums):

  max_value = max(list_nums, key=lambda x: x)
  return max_value
```
8. Implement a lambda function to filter out all the even numbers from a list of integers.

Answer :

Here is a lambda function to filter out all the even numbers from a list of integers:
```
def filter_even_numbers(list_nums):

  odd_numbers = list(filter(lambda x: x % 2 != 0, list_nums))
  return odd_numbers
```

9. Write a lambda function to sort a list of strings in ascending order based on the length of each
string.

Answer :

Here's a lambda function that sorts a list of strings in ascending order based on the length of each string:
```
strings = ["apple", "banana", "cat", "dog", "elephant"]

sorted_strings = sorted(strings, key=lambda x: len(x))

print(sorted_strings)
```

10. Create a lambda function that takes two lists as input and returns a new list containing the common elements between the two lists.

Answer :

- Here's the code that implements the lambda function to find the common elements between two lists:
```
common_elements = lambda list1, list2: [element for element in list1 if element in list2]

list1 = [1, 2, 3, 4, 5]

list2 = [4, 5, 6, 7, 8]

result = common_elements(list1, list2)

print(result)  # Output: [4, 5]
```

11. Write a recursive function to calculate the factorial of a given positive integer.

Answer :

- Certainly! Here's an example of a recursive function in Python to calculate the factorial of a positive integer:
```
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n -  1)

result = factorial(5)
print(result)
```

12. Implement a recursive function to compute the nth Fibonacci number.

Answer :

- Certainly! Here's an example of a recursive function in Python to compute the nth Fibonacci number:
```
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

result = fibonacci(6)
print(result)
```

13. Create a recursive function to find the sum of all the elements in a given list.

Answer :

- a recursive function in Python to find the sum of all the elements in a given list:
```
def recursive_sum(lst):
    if len(lst) == 0:
        return 0
    else:
        return lst[0] + recursive_sum(lst[1:])

# Example usage
my_list = [1, 2, 3, 4, 5]
total_sum = recursive_sum(my_list)
print("Sum of the elements:", total_sum)
```

14. Write a recursive function to determine whether a given string is a palindrome.

Answer :

 ```
def is_palindrome(string):
    if len(string) <= 1:
        return True
    else:
        first_char = string[0]
        last_char = string[-1]
        if first_char == last_char:
            return is_palindrome(string[1:-1])
        else:
            return False


word = "radar"
if is_palindrome(word):
    print(word, "is a palindrome.")
else:
    print(word, "is not a palindrome.")
```

15. Implement a recursive function to find the greatest common divisor (GCD) of two positive integers.

Answer :

```
def gcd(a, b):
    if b == 0:
        return a
    else:
        return gcd(b, a % b)

num1 = 48
num2 = 18
result = gcd(num1, num2)
print("GCD of", num1, "and", num2, "is:", result)
```

