# Zahra-mousaviaslarzanagh-
Assignment 4
Date:17.02.2024
Exercise 1

product=lambda x,y: x*y
result= product(5,6)
print("output:",result)
output: 30

Exercise 2


import math def circle_area(radius): 
return math.pi * radius**2 
result = circle_area(10) 
print("Oitput:", result) 

Oitput: 314.1592653589793


Exercise 3


def calculator(num1, num2, operation): 
if operation == 'a': 
return num1 + num2 
elif operation == 's': 
return num1 - num2 
elif operation == 'm': 
return num1 * num2 
elif operation == 'd': 
if num2 != 0: 
return num1 / num2 
else:return "Error: Division by zero" 
else:return "Error: Invalid operation" 
result = calculator(2,5, 'd') 
print("Output:", result) 

Output: 0.4



