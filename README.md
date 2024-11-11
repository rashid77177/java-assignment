# java-assignment
Write a Java program that takes an integer input from the user and
calculates the factorial of the number. Then, write a method to calculate
the sum of the digits of this factorial. For example, if the user enters 5,
calculate 5! (120) and then find the sum of its digits (1 + 2 + 0 = 3). 
Java code and eximport java.math.BigInteger;
import java.util.Scanner;

public class FactorialDigitSum {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user for input
        System.out.print("Enter an integer: ");
        int number = scanner.nextInt();

        // Calculate factorial
        BigInteger factorial = calculateFactorial(number);

        // Calculate sum of digits of factorial
        int sumOfDigits = sumOfDigits(factorial);

        // Display results
        System.out.println(number + "! = " + factorial);

        
      Create a program that accepts 10 integers from the user, stores them in 
an array, and then prints only the prime numbers in that array.

Implement a separate method to check if a number is prime
Java code and explain  System.out.println("Sum of digits = " + sumOfDiplain
import java.util.Scanner;

public class PrimeNumbersInArray {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[] numbers = new int[10];

        // Accept 10 integers from the user
        System.out.println("Enter 10 integers:");
        for (int i = 0; i < 10; i++) {
            numbers[i] = scanner.nextInt();
        }

        // Print prime numbers in the array
        System.out.println("Prime numbers in the array:");
        for (int num : numbers) {
            if (isPrime(num)) {
                System.out.print(num + " ");
            }
        }
    }

    // Method to check if a number is prime
    public static boolean isPrime(int num) {
        if (num <= 1) return false; // 0, 1, and negative numbers are not prime
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }
}
Build a menu-driven calculator that performs addition, subtraction, 
multiplication, or division based on the user's choice. Use if-else

statements to determine the operation.

Keep prompting the user to perform another operation until they choose
to exit.
import java.util.Scanner;

public class MenuDrivenCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean continueCalculating = true;

        while (continueCalculating) {
            // Display menu options
            System.out.println("\nCalculator Menu:");
            System.out.println("1. Addition");
            System.out.println("2. Subtraction");
            System.out.println("3. Multiplication");
            System.out.println("4. Division");
            System.out.println("5. Exit");
            System.out.print("Enter your choice: ");
            
            int choice = scanner.nextInt();

            if (choice >= 1 && choice <= 4) {
                // Prompt for two numbers if the choice is a calculation operation
                System.out.print("Enter the first number: ");
                double num1 = scanner.nextDouble();
                
                System.out.print("Enter the second number: ");
                double num2 = scanner.nextDouble();

                // Perform the chosen operation using if-else statements
                if (choice == 1) {
                    System.out.println("Result: " + (num1 + num2));
                } else if (choice == 2) {
                    System.out.println("Result: " + (num1 - num2));
                } else if (choice == 3) {
                    System.out.println("Result: " + (num1 * num2));
                } else if (choice == 4) {
                    if (num2 != 0) {
                        System.out.println("Result: " + (num1 / num2));
                    } else {
                        System.out.println("Error: Division by zero is not allowed.");
                    }
                }
            } else if (choice == 5) {
                // Exit the loop
                continueCalculating = false;
                System.out.println("Exiting the calculator. Goodbye!");
            } else {
                System.out.println("Invalid choice. Please select a valid option.");
            }
        }

        scanner.close();
    }
}

Accept a string input from the user and check if it’s a palindrome (a word
that reads the same forwards and backwards). Create a method to
reverse the string and compare it to the original to determine if it’s a
palindrome.
import java.util.Scanner;

public class PalindromeChecker {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter a string
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        // Check if the string is a palindrome
        if (isPalindrome(input)) {
            System.out.println("The string \"" + input + "\" is a palindrome.");
        } else {
            System.out.println("The string \"" + input + "\" is not a palindrome.");
        }

        scanner.close();
    }

    // Method to check if a string is a palindrome
    public static boolean isPalindrome(String str) {
        // Get the reversed string
        String reversed = reverseString(str);
        // Compare the original and reversed strings (ignoring case)
        return str.equalsIgnoreCase(reversed);
    }

    // Method to reverse a string
    public static String reverseString(String str) {
        StringBuilder reversed = new StringBuilder(str);
        return reversed.reverse().toString();
    }
}

Write a program that takes an integer input n and stores the first n terms
of the Fibonacci sequence in an array. Then, print the array. For example,
if the user enters 7, store and display the first 7 terms of the Fibonacci
sequence: 0, 1, 1, 2, 3, 5, 8.

import java.util.Scanner;

public class FibonacciSequence {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user for the number of terms
        System.out.print("Enter the number of terms for the Fibonacci sequence: ");
        int n = scanner.nextInt();

        // Check if n is positive
        if (n <= 0) {
            System.out.println("Please enter a positive integer.");
        } else {
            // Create an array to store the Fibonacci sequence
            int[] fibonacciArray = new int[n];
            
            // Generate the Fibonacci sequence
            for (int i = 0; i < n; i++) {
                if (i == 0) {
                    fibonacciArray[i] = 0;
                } else if (i == 1) {
                    fibonacciArray[i] = 1;
                } else {
                    fibonacciArray[i] = fibonacciArray[i - 1] + fibonacciArray[i - 2];
                }
            }

            // Print the Fibonacci sequence
            System.out.print("Fibonacci sequence: ");
            for (int i = 0; i < n; i++) {
                System.out.print(fibonacciArray[i] + " ");

    Write a program that accepts n integers from the user (where n is also
provided by the user). Store the numbers in an array and write a method
to find and display the second largest number in the array.

import java.util.Scanner;

public class SecondLargestNumber {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user for the number of integers
        System.out.print("Enter the number of integers: ");
        int n = scanner.nextInt();

        // Check if n is at least 2
        if (n < 2) {
            System.out.println("Please enter at least 2 integers.");
        } else {
            int[] numbers = new int[n];
            
            // Accept n integers from the user
            System.out.println("Enter " + n + " integers:");
            for (int i = 0; i < n; i++) {
                numbers[i] = scanner.nextInt();
            }

            // Find and display the second largest number
            int secondLargest = findSecondLargest(numbers);
            System.out.println("The second largest number is: " + secondLargest);
        }

        scanner.close();
    }

    // Method to find the second largest number in an array
    public static int findSecondLargest(int[] array) {
        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;

        for (int num : array) {
            if (num > largest) {
                secondLargest = largest;  // Update second largest
                largest = num;            // Update largest
            } else if (num > secondLargest && num < largest) {
                secondLargest = num;
            }
        }
        
        return

    Write a program that takes an integer input n and prints a pyramid of
numbers up to n rows, where each row has an increasing count of
numbers. For example, if n = 4, the output should be:

import java.util.Scanner;

public class NumberPyramid {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter the number of rows
        System.out.print("Enter the number of rows: ");
        int n = scanner.nextInt();

        // Generate the pyramid pattern
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");
            }
            System.out.println(); // Move to the next line after each row
        }

        scanner.close();
    }
}

Write a program that takes an integer input n and prints an inverted 
triangle of numbers. For example, if n = 5, the output should be
5 4 3 4 1
4 3 2 1 
3 2 1 
2 1 
1

import java.util.Scanner;

public class InvertedNumberTriangle {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter the number of rows
        System.out.print("Enter the number of rows: ");
        int n = scanner.nextInt();

        // Generate the inverted triangle pattern
        for (int i = n; i >= 1; i--) {
            for (int j = i; j >= 1; j--) {
                System.out.print(j + " ");
            }
            System.out.println(); // Move to the next line after each row
        }

        scanner.close();
    }
}

Implement a program that accepts an integer input n and prints Floyd's 
Triangle up to n rows. Floyd’s Triangle has consecutive numbers starting 
from 1. For example, if n = 4, the output should be:
1
1 2
4 5 6
7 8 9 10
import java.util.Scanner;

public class FloydsTriangle {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter the number of rows
        System.out.print("Enter the number of rows for Floyd's Triangle: ");
        int n = scanner.nextInt();

        int number = 1; // Start the first number at 1

        // Generate Floyd's Triangle
        for (int i = 1; i <= n; i++) {      // Outer loop for rows
            for (int j = 1; j <= i; j++) {  // Inner loop for numbers in each row
                System.out.print(number + " ");
                number++;                   // Increment to the next number
            }
            System.out.println();           // Move to the next line after each row
        }

        scanner.close();
    }
}

Take a string input from the user and a character to search for. Write a
method to count the occurrences of the character in the string and return
the count. Then display the count to the user.

import java.util.Scanner;

public class CharacterSearch {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter a string
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine();

        // Prompt the user to enter a character to search for
        System.out.print("Enter a character to search for: ");
        char searchChar = scanner.next().charAt(0);

        // Call the method to count occurrences and display the result
        int count = countOccurrences(inputString, searchChar);
        System.out.println("The character '" + searchChar + "' appears " + count + " times in the string.");

        scanner.close();
    }

    // Method to count occurrences of a character in a string
    public static int countOccurrences(String str, char ch) {
        int count = 0;
        
        // Loop through the string and count occurrences of the character
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) == ch) {
                count++;
            }
        }
        
        return count;
    }
}
