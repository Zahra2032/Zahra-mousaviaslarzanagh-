Converter
Group Members
- Uswatta Liyanage Thilini Mahesha Perera
- Crystal Amy Weerasinghe Jayasinghe Arachchige
- Osama Aamer
- Zahra Mousaviaslarzanagh
- Anjalika Lakmali Perera Singappuli Achchige
Description
Convertor Create a program that can be used to convert temperature, length, weight, pressure. Your program should have a menu displayed for the user to choose from, where are listed the convertion options: temperature fahrenheit to celsius celsiusto fahrenheit length miles to km km to miles weight pound to kilogramms kg to pound exit The program should allow the user to choose the desired convertion over and over again until user chooses to quit using it.

Solution
The below code defines a Python class called Converter that provides methods for converting temperature, distance, and weight measurements between different units. These methods allow to convert temperatures from Fahrenheit to Celsius and vice versa, distances from miles to kilometers and kilometers to miles, and weights from pounds to kilograms and kilograms to pounds. The class ensures that inputs are valid and does not allow negative values for distances and weights. This code is designed to be reusable and provides a straightforward way to perform common unit conversions in Python programs.
class Converter:
    

    # Following Method Converts temperature from Fahrenheit to Celsius.

    
    @staticmethod
    def fahrenheit_to_celsius(temp):
        final_value = (temp - 32) * 5/9
        return final_value
    

    # Following Method Converts temperature from Celsius to Fahrenheit.

    @staticmethod
    def celsius_to_fahrenheit(temp):
        final_value = (temp * 9/5) + 32
        return final_value
    

    # Following Method Converts Distance from Miles to kilometers.

    @staticmethod
    def miles_to_km(miles):
        if miles < 0:
            print("Distance in miles cannot be negative.")
        else:
            km = miles * 1.60934
            return km
        
    
    # Following Method Converts Distance from kilometers to Miles.
    
        
    @staticmethod
    def km_to_miles(km):
        if km <0:
            print("Distance in km cannot be negative.")
        else:
            miles = km / 1.60934
            return miles
    
   
    # Following Method Converts weight from pounds to kilograms.
    

    @staticmethod
    def pound_to_kg(pounds):
        if pounds < 0:
            print("Weight in pounds cannot be negative.")
        else:
            kg = pounds * 0.453592
            return kg
        
 
    # Following Method Converts weight from kilograms to pounds.
        
    @staticmethod
    def kg_to_pound(kg):
        if kg < 0:
            print("Weight in kilograms cannot be negative.")
        else:
            pound = kg / 0.453592
            return pound
         
Following function repeatedly prompts the user for input until valid input is provided. It attempts to convert the user input to the specified type and raises a ValueError if the input cannot be converted or if it is negative. If an error occurs, it prints the error message and prompts the user again. If the input is valid, it returns the converted value.
def get_valid_input(prompt, input_type):
    
    while True:
        user_input = input(prompt)
        
        try:
            value = float(user_input)
            
            if input_type == "positive":
                if value < 0:
                    print("Enter valid postive value")
                else:
                    return int(user_input)
            else:
                return int(user_input)
            
        except ValueError:
            print("Invalid input. Please enter a numerical value.")

 
            
Main program for unit conversion.

This function repeatedly prompts the user to choose a conversion option and performs the corresponding conversion using the Converter class methods.It uses the get_valid_input function to ensure that user inputs are valid.

The program starts by creating an instance of the Converter class. Then, it enters a loop where it displays a menu of conversion options (Fahrenheit to Celsius, Celsius to Fahrenheit, Miles to Kilometers, etc.) and prompts the user to select an option.

Depending on the user's choice, the program prompts for the appropriate input value (temperature in Fahrenheit or Celsius, length in miles or kilometers, weight in pounds or kilograms), validates the input, and performs the conversion using the corresponding method of the Converter class.

The program continues to loop until the user chooses to exit by entering '7'. If the user enters an invalid choice, the program displays an error messagebnand prompts the user to enter a valid choice.

Upon exiting the loop, the program prints a farewell message and terminates. Returns: None
def main():
    converter = Converter()
    while True:
        print("1. Convert Fahrenheit to Celsius")
        print("2. Convert Celsius to Fahrenheit")
        print("3. Convert Miles to Kilometers")
        print("4. Convert Kilometers to Miles")
        print("5. Convert Pounds to Kilograms")
        print("6. Convert Kilograms to Pounds")
        print("7. Exit")
        print('\n' * 2)

        user_choice = get_valid_input("Enter your choice: ", int)

        if user_choice == 1:
            temp_f = get_valid_input("Enter temperature in Fahrenheit: ", "c_f")
            print("Temperature in Celsius:", converter.fahrenheit_to_celsius(temp_f))
            print('\n' * 2)
        elif user_choice == 2:
            temp_c = get_valid_input("Enter temperature in Celsius: ", "c_f")
            print("Temperature in Fahrenheit:", converter.celsius_to_fahrenheit(temp_c))
            print('\n' * 2)
        elif user_choice == 3:
            miles = get_valid_input("Enter length in miles: ", "positive")
            print("Length in kilometers:", converter.miles_to_km(miles))
            print('\n' * 2)
        elif user_choice == 4:
            km = get_valid_input("Enter length in kilometers: ", "positive")
            print("Length in miles:", converter.km_to_miles(km))
            print('\n' * 2)
        elif user_choice == 5:
            pounds = get_valid_input("Enter weight in pounds: ", "positive")
            print("Weight in kilograms:", converter.pound_to_kg(pounds))
            print('\n' * 2)
        elif user_choice == 6:
            kg = get_valid_input("Enter weight in kilograms: ", "positive")
            print("Weight in pounds:", converter.kg_to_pound(kg))
            print('\n' * 2)
        elif user_choice == 7:
            print("Exiting the program.")
            print('\n' * 2)
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 7.")
            print('\n' * 2)

if __name__ == "__main__":
    main()
1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 1
Enter temperature in Fahrenheit: 23
Temperature in Celsius: -5.0



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 2
Enter temperature in Celsius: 34
Temperature in Fahrenheit: 93.2



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 3
Enter length in miles: 5
Length in kilometers: 8.0467



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 4
Enter length in kilometers: 5
Length in miles: 3.106863683249034



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 5
Enter weight in pounds: 45
Weight in kilograms: 20.41164



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 6
Enter weight in kilograms: 9
Weight in pounds: 19.841619781653996



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: eee
Invalid input. Please enter a numerical value.
Enter your choice: 56
Invalid choice. Please enter a number between 1 and 7.



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 6
Enter weight in kilograms: ee
Invalid input. Please enter a numerical value.
Enter weight in kilograms: 5
Weight in pounds: 11.023122100918888



1. Convert Fahrenheit to Celsius
2. Convert Celsius to Fahrenheit
3. Convert Miles to Kilometers
4. Convert Kilometers to Miles
5. Convert Pounds to Kilograms
6. Convert Kilograms to Pounds
7. Exit



Enter your choice: 7
Exiting the program.



