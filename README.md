# Menu-Driven Program Using Pointers to Function Report

Table of Contents

Introduction

This report outlines how a menu-driven program is executed in C++ using the pointers to functions elements to perform different mathematical operations. A menu-driven program in the C++ programming language is a type of interactive software application that displays a menu of options and allows the user to choose from a list of actions or functionalities (Javatpoint, 2021). A function pointer in C++ is a variable that stores a function's address and point to executable code within a program. Function pointers are used to obtain the function's address (GeeksforGeeks, 2022). The program allow user to select the appropriate option in the interface or menu of the executed program, enter the numbers to receive the result of the chosen option and if the option is incorrect then it tells us to try again.

Purpose

Declare an array of function pointers, each executing a separate mathematical operation.

• Design an interactive menu to show consumers possible options when the code is implemented.

• Prompt the user for a selection in the given option, then execute the associated function.

Array of Function Pointers

An array named operation is declared to hold pointers to each of the four mathematical functions. This enables the application to choose and execute a function dynamically based on user input.

Implementation Process in the code

Function Declaration

At the top of the code, the code is being declared with different mathematical operations.
• Use int add (int a, int b) to calculate the sum of two integers when the user selects the correct option for addition.
• Int subtraction (int a, int b) calculates the difference between two integers in the selected option for subtraction.
• Int multiply (int a, int b) returns the product of two integers from the available option for multiplication.
• Int divide (int a, int b) provides the quotient for the appropriate option for division in the interface of the code.
![image](https://github.com/user-attachments/assets/10148590-8d94-48f7-bb55-c91e26faa48d)

Main Function

![image](https://github.com/user-attachments/assets/258696fa-605a-497e-917c-ed63160f9358)


Menu Display

In this section of the code, it defines the type of mathematical operations and the number of elements which will be displayed in the program when executed in the menu section.
1.	Add
2.	Subtract
3.	Multiply
4.	Divide
5.	Exit
![image](https://github.com/user-attachments/assets/7eeea100-03eb-433f-8e09-a1bd86cdac98)

User Interaction and Execution

The application prompts the user to choose an option from the menu. The selected operation is then performed with the relevant function pointer from the operations array, and the result is displayed. If the user selects the correct option from the available choices in option 1 to 4 for the different mathematical operation, it prompts the user to enter two numbers as shown in the code below. When the two numbers are entered it displays the result of the different mathematical operations respectively and exits the program when option 5 is chosen. If the invalid option is selected such as 6, the user is prompted to try again. 

![image](https://github.com/user-attachments/assets/daf9d605-b77c-40b4-81ce-a0329680c02f)
![image](https://github.com/user-attachments/assets/d0be3eaf-e56a-4177-9ca7-a3ab27df47aa)
![image](https://github.com/user-attachments/assets/8c6290b2-89ca-44d6-8247-61eab227e3b4)
![image](https://github.com/user-attachments/assets/3bf31ccb-707f-4762-9186-7cc6e42fcf02)
![image](https://github.com/user-attachments/assets/0b76e07c-c552-4546-a93e-9b8babf05583)
![image](https://github.com/user-attachments/assets/7178faa5-6389-4676-aed1-f380c2ae6115)


Code used in the Program with Comments

#include <iostream>

// Function declaration for the different mathematical operations
int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

int divide(int a, int b) {
    if (b != 0)
        return a / b;
    else {
        printf("Error: Division by zero\n");
        return 0;
    }
}

int main() {
    // Array of pointers to functions
    int (*operations[])(int, int) = {add, subtract, multiply, divide};
    
    int choice, a, b, result;
    
    while (1) {
        // Menu that displays the available options in the interface of the program
        printf("\nMenu:\n");
        printf("1. Add\n");
        printf("2. Subtract\n");
        printf("3. Multiply\n");
        printf("4. Divide\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        
        // Loop for exit condition
        if (choice == 5) {
            printf("Exiting...\n");
            break;
        }
        
        // Checking the validity of the choice
        if (choice < 1 || choice > 4) {
            printf("Invalid choice, please try again.\n");
            continue;
        }
        
        // Get numbers from user input
        printf("Enter two numbers: ");
        scanf("%d %d", &a, &b);
        
        // Executes the selected option for operation
        result = operations[choice - 1](a, b);
        printf("Result: %d\n", result);
    }
    
    return 0;
}

Conclusion

The menu-driven program demonstrates the use of pointers to functions in C++ and how to pass the pointers to functions. The program serves as the practical example of dynamic function execution based on the user input when the user selects the different available option for mathematical operation in the program it gives its expected result.

References

GeeksforGeeks. (2022, December 28). Function Pointer in C++. GeeksforGeeks; GeeksforGeeks. https://www.geeksforgeeks.org/function-pointer-in-cpp/
Menu-driven program in C++ - javatpoint. (2021). Www.javatpoint.com. https://www.javatpoint.com/menu-driven-program-in-cpp#:~:text=A%20text%2Dbased%20or%20graphical.
