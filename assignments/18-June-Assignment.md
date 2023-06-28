
# 18-June-Assignment

1. What is the role of the 'else' block in a try-except statement? Provide an example scenario where it would be useful.

Answer :

- In a try-except statement, the 'else' block is like a special section of code that gets executed only if everything in the 'try' block goes well, without any errors or exceptions.

- The 'else' block allows you to specify code that should only run when the 'try' block succeeds, providing a way to separate the error-handling code from the code that should run when no exceptions occur.



2. Can a try-except block be nested inside another try-except block? Explain with an example.

Answer :

- Yes, a try-except block can be nested inside another try-except block in Python. This is known as nested exception handling.
```
try:
    # Outer try-except block
    try:
        # Inner try-except block
        numerator = 10
        denominator = 0
        result = numerator / denominator
        print("Result:", result)
    except ZeroDivisionError:
        print("Cannot divide by zero!")
except Exception as e:
    print("An error occurred:", str(e))
```
- By nesting try-except blocks, you can have multiple layers of exception handling, each responsible for a specific scope or level of the code.



3. How can you create a custom exception class in Python? Provide an example that demonstrates its usage.

Answer :

- To create a custom exception class in Python, you need to define a new class that inherits from the built-in Exception class or any of its subclasses.
```
class CustomException(Exception):
    pass

def divide_numbers(a, b):
    if b == 0:
        raise CustomException("Cannot divide by zero!")
    return a / b

try:
    result = divide_numbers(10, 0)
    print("Result:", result)
except CustomException as e:
    print("Custom exception occurred:", str(e))
```
- In this example, we define a custom exception class called CustomException, which is a subclass of the built-in Exception class. We can add custom behavior or attributes to this class if needed.



4. What are some common exceptions that are built-in to Python?

Answer :

Python provides a wide range of built-in exceptions that cover various error scenarios. Some common exceptions that you may encounter while working with Python include:

- `SyntaxError`: Raised when there is a syntax error in the code.

- `IndentationError`: Raised when there is an incorrect indentation in the code.

- `NameError`: Raised when a local or global name is not found.

- `TypeError`: Raised when an operation or function is applied to an object of inappropriate type.

- `ValueError`: Raised when a function receives an argument of the correct type but an invalid value.

- `KeyError`: Raised when a dictionary key is not found.

- `IndexError`: Raised when an index is out of range.

- `FileNotFoundError`: Raised when a file or directory is not found.
- `IOError`: Raised when an input/output operation fails.

- `ZeroDivisionError`: Raised when division or modulo by zero occurs.



5. What is logging in Python, and why is it important in software development?

Answer :

Here are some additional points to further explain the importance of logging in software development:

- `Production environment monitoring` : Logging is crucial for monitoring software applications in production environments.

- `Security analysis and forensics` : Logging plays a significant role in security analysis and forensics. 

- `Historical analysis and auditing` : Logs serve as a historical record of a program's execution. 

- `Performance monitoring and optimization` : Logging can aid in performance monitoring and optimization efforts. 

Overall, logging is a crucial tool in software development that provides visibility, facilitates troubleshooting, aids in security analysis, and supports performance monitoring. 




6. Explain the purpose of log levels in Python logging and provide examples of when each log level would be appropriate.

Answer :

Log levels in Python logging allow developers to categorize and prioritize log messages based on their severity or importance. The logging module in Python defines several log levels, each serving a specific purpose. Here are the standard log levels in Python logging.

- `DEBUG` : The DEBUG level is used for detailed information, typically useful for debugging purposes. It provides the most verbose level of logging, often including variable values, function calls, and other fine-grained details. 

- `INFO` : The INFO level is used to convey informational messages that signify the normal flow of the program. 

- `WARNING` : The WARNING level is used to indicate potential issues or situations that could lead to errors or unexpected behavior.

- `ERROR` : The ERROR level is used to indicate errors that occurred during program execution. It represents more severe issues that prevent a particular function, process, or operation from completing successfully.

- `CRITICAL` : The CRITICAL level represents the highest severity level in Python logging. It is used to highlight critical errors or failures that require immediate attention and may result in the program's termination.



7. What are log formatters in Python logging, and how can you customise the log message format using formatters?

Answer :

Log formatters in Python logging are responsible for defining the structure and content of log messages. They determine how log records are formatted and presented in the log output, such as console, files, or other logging destinations.

```
import logging

# Create a logger
logger = logging.getLogger('my_logger')
logger.setLevel(logging.DEBUG)

formatter = logging.Formatter('%(asctime)s - %(levelname)s - %(message)s')

handler = logging.StreamHandler()
handler.setFormatter(formatter)
r
logger.addHandler(handler)

logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message')
```



8. How can you set up logging to capture log messages from multiple modules or classes in a Python application?

Answer :

To capture log messages from multiple modules or classes in a Python application, you can set up a central logger and configure it to handle logging from various sources. Here's a general approach to achieve this :

- Import the logging module:
```
import logging

logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(levelname)s - %(message)s')

logger = logging.getLogger(__name__)

logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message')

logging.basicConfig(filename='application.log', level=logging.DEBUG, format='%(asctime)s - %(levelname)s - %(message)s')
```



9. What is the difference between the logging and print statements in Python? When should you use logging over print statements in a real-world application?

Answer :

The logging and print statements in Python serve different purposes and have distinct characteristics. Here are the key differences between them:

- `Output destination` : The print statement prints messages to the standard output (usually the console) by default, while logging allows you to specify the output destination, such as the console, file, or network stream. This flexibility makes logging more suitable for capturing and managing log messages in real-world applications.

- `Levels of severity` : Logging provides different log levels (e.g., DEBUG, INFO, WARNING, ERROR, CRITICAL) to categorize the severity of log messages. With print, all messages are printed regardless of their importance. 

While `print` statements can be helpful for quick debugging or temporary output during development, logging is a more robust and scalable solution for capturing and managing log messages in real-world applications, providing greater control, configurability, and long-term maintainability.




10. Write a Python program that logs a message to a file named "app.log" with the following requirements:

● The log message should be "Hello, World!"

● The log level should be set to "INFO."

● The log file should append new log entries without overwriting previous ones.

Answer :

```
import logging

# Configure logging

logging.basicConfig(filename='app.log', level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')

# Log the message

logging.info('Hello, World!')
```
- Each time the program is executed, the log message will be appended to the existing log file, preserving the previous log entries without overwriting them.




11. Create a Python program that logs an error message to the console and a file named "errors.log" if an exception occurs during the program's execution. The error message should include the exception type and a timestamp.

Answer :

Here's an example Python program that logs an error message to both the console and a file named "errors.log" if an exception occurs during its execution:
```
import logging
import traceback
from datetime import datetime

def log_exception(ex_type, ex_value, ex_traceback):
    timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    exception = "".join(traceback.format_exception(ex_type, ex_value, ex_traceback))
    error_message = f"[{timestamp}] Exception occurred:\n{exception}"

    # Log to console
    print(error_message)

    # Log to file
    logging.basicConfig(filename="errors.log", level=logging.ERROR, format="%(asctime)s %(message)s")
    logging.error(error_message)

try:
    
    # Example: Dividing by zero to raise an exception
    result = 10 / 0

except Exception as e:
    log_exception(type(e), e, e.__traceback__)

```
