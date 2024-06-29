Name:NANNEBOINA HARI KRISHNA  
Company:CODETECH IT SOLUTIONS
ID:CT08DS1473  Domian:Python
Duration:1st June to 30th June 
Mentor:SRAVANI GOUNI

Creating a Python program to track and manage student grades is a practical project that helps you understand data structures, input/output operations, and basic data processing. Here’s an overview of how to create a student grade management system.

### Project Overview

**Objective**: Build a program that allows users to input grades for different subjects or assignments, calculate the average grade, and display the overall grade along with additional information like the letter grade or GPA.

### Steps to Create the Student Grade Management System

1. **Define Functions**:
    - Functions for adding grades.
    - Functions for calculating average grades.
    - Functions for determining letter grades.

2. **Display Menu**:
    - Display a menu for the user to select actions such as adding grades, viewing the average, and exiting the program.

3. **Get User Input**:
    - Prompt the user to input grades for different subjects or assignments.
    - Ensure that the user input is valid (i.e., numerical grades).

4. **Calculate and Display Results**:
    - Calculate the average grade.
    - Determine and display the letter grade based on the average.

5. **Repeat or Exit**:
    - Allow the user to perform another action or exit the program.

### Sample Code

Here is a simple implementation of the student grade management system in Python:

```python
def add_grade(grades):
    subject = input("Enter the subject or assignment: ")
    try:
        grade = float(input(f"Enter the grade for {subject}: "))
        grades[subject] = grade
    except ValueError:
        print("Invalid input. Please enter a numerical grade.")

def calculate_average(grades):
    if not grades:
        return None
    total = sum(grades.values())
    average = total / len(grades)
    return average

def determine_letter_grade(average):
    if average >= 90:
        return 'A'
    elif average >= 80:
        return 'B'
    elif average >= 70:
        return 'C'
    elif average >= 60:
        return 'D'
    else:
        return 'F'

def display_menu():
    print("\n--- Student Grade Management ---")
    print("1. Add grade")
    print("2. View average grade")
    print("3. Exit")

def main():
    grades = {}
    while True:
        display_menu()
        choice = input("Enter choice (1/2/3): ")
        
        if choice == '1':
            add_grade(grades)
        elif choice == '2':
            average = calculate_average(grades)
            if average is not None:
                letter_grade = determine_letter_grade(average)
                print(f"\nAverage Grade: {average:.2f}")
                print(f"Letter Grade: {letter_grade}")
            else:
                print("No grades available to calculate the average.")
        elif choice == '3':
            print("Exiting the grade management system. Goodbye!")
            break
        else:
            print("Invalid choice. Please choose a valid option.")

if __name__ == "__main__":
    main()
```

### Explanation of the Code

1. **Functions**:
    - `add_grade(grades)`: Prompts the user to input a subject and grade, and adds them to the grades dictionary.
    - `calculate_average(grades)`: Calculates and returns the average grade from the grades dictionary.
    - `determine_letter_grade(average)`: Determines and returns the letter grade based on the average grade.
    - `display_menu()`: Prints the menu options for the user.

2. **Main Loop**:
    - The `main()` function contains a loop that keeps running until the user decides to exit.
    - It displays the menu and gets the user's choice.
    - It then calls the appropriate function based on the user's choice.
    - If the user inputs invalid data or chooses an invalid option, appropriate error messages are displayed.

### Running the Program

- Save the script to a file, for example, `student_grade_manager.py`.
- Run the script using Python: `python student_grade_manager.py`.
- Follow the prompts to add grades and view the average grade.

This project provides a good foundation for managing student grades and can be expanded with additional features such as storing grades in a file, handling more complex grading systems, or implementing a graphical user interface (GUI).
