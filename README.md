EX-21-POINTERS
# AIM:
Write a C program to convert a 23.65 into 25 using pointer

## ALGORITHM:
1.	Declare a double variable to hold the floating-point number (23.65).
2.	Declare a pointer to double to point to the address of the variable.
3.	Use the pointer to modify the value to 25.0.
4.	Print the modified value.

## PROGRAM:
    #include <stdio.h>
    
    int main() {
        double num = 23.65;       // Step 1
        double *ptr = &num;       // Step 2
    
        // Step 3: Modify the value using pointer
        *ptr = 25.0;
    
        // Step 4: Print the modified value
        printf("Modified value: %.2lf\n", num);
    
        return 0;
    }


## OUTPUT:
Modified value: 25.00












## RESULT:
Thus the program to convert a 23.65 into 25 using pointer has been executed successfully.
 
 


# EX-22-FUNCTIONS AND STORAGE CLASS

## AIM:

Write a C program to calculate the Product of first 12 natural numbers using Recursion

## ALGORITHM:

1.	Define a recursive function calculateProduct that takes an integer parameter n.
2.	Return n multiplied by the result of the calculateProduct function called with n - 1.
3.	Declare an integer variable n and an unsigned long long variable product.
4.	Initialize n with the value 12 (for the first 12 natural numbers).
5.	Call the calculateProduct function with n and store the result in the product variable.
6.	Print the result, indicating it is the product of the first 12 natural numbers.

## PROGRAM:
    #include <stdio.h>
    
    // Step 1 & 2: Recursive function to calculate product
    unsigned long long calculateProduct(int n) {
        if (n == 1) {
            return 1;  // Base case
        }
        return n * calculateProduct(n - 1);  // Recursive step
    }
    
    int main() {
        int n = 12;   // Step 4
        unsigned long long product;
    
        // Step 5
        product = calculateProduct(n);
    
        // Step 6
        printf("Product of first %d natural numbers is: %llu\n", n, product);
    
        return 0;
    }

## OUTPUT:
Product of first 12 natural numbers is: 479001600
 		
## RESULT:

Thus the program has been executed successfully.
 
 


# EX-23-ARRAYS AND ITS OPERATIONS

## AIM:

Write C Program to find Sum of each row of a Matrix

## ALGORITHM:

1.	Declare and initialize the matrix with the desired values.
2.	Create a loop to iterate through each row of the matrix.
3.	Inside the loop, calculate the sum of the elements in each row.
4.	Print the sum for each row.

## PROGRAM:
    #include <stdio.h>
    
    int main() {
        int matrix[3][4] = {
            {1, 2, 3, 4},
            {5, 6, 7, 8},
            {9, 10, 11, 12}
        };
        
        int rows = 3;
        int cols = 4;
        int i, j, sum;
    
        // Step 2 & 3: Loop through each row and calculate sum
        for (i = 0; i < rows; i++) {
            sum = 0;  // reset sum for each row
            for (j = 0; j < cols; j++) {
                sum += matrix[i][j];
            }
            // Step 4: Print sum of current row
            printf("Sum of row %d is %d\n", i + 1, sum);
        }
    
        return 0;
    }



## OUTPUT

Sum of row 1 is 10
Sum of row 2 is 26
Sum of row 3 is 42

 
 

 ## RESULT
 Thus C program to add row elements executed successfully 


# EX-24-STRINGS

## AIM:

Write C program for the below pyramid string pattern. Enter a string: PROGRAM Enter number of rows: 5 P R O G R A M P R O G R A M P R O G R A M

## ALGORITHM:

1.	Input the number of rows for the pyramid (e.g., num_rows).
2.	Initialize variables:i for the row count (starting from 1),j for the character count (starting from 1)
3.	Start a loop for i from 1 to num_rows (for each row of the pyramid).
4.	Calculate the midpoint position as midpoint = (2 * num_rows - 1) / 2.
5.	End the program.

## PROGRAM:
    #include <stdio.h>
    #include <string.h>
    
    int main() {
        char str[100];
        int num_rows, i, j, len, index = 0;
    
        // Input string and number of rows
        printf("Enter a string: ");
        scanf("%s", str);
    
        printf("Enter number of rows: ");
        scanf("%d", &num_rows);
    
        len = strlen(str);
    
        // For each row in the pyramid
        for (i = 1; i <= num_rows; i++) {
            int total_chars = 2 * i - 1;
    
            // Print spaces for pyramid shape (optional)
            for (j = 0; j < num_rows - i; j++) {
                printf(" ");
            }
    
            // Print characters for current row
            for (j = 0; j < total_chars; j++) {
                printf("%c ", str[index]);
                index = (index + 1) % len;  // wrap around the string
            }
    
            printf("\n");
        }
    
        return 0;
    }


 ## OUTPUT
    Enter a string: PROGRAM
    Enter number of rows: 5
        P 
       R O P 
      G R A M P 
     R O G R A M P R 
    O G R A M P R O G 

 

## RESULT

Thus the C program to String process executed successfully
 

 
.



# EX -25 –DISPLAYING ARRAYS USING POINTERS
## AIM

Write a c program to read and display an array of any 6 integer elements using pointer

## ALGORITHM
Step 1: Start the program.
Step 2: Declare the following:
•	Integer variable i for iteration.
•	Integer variable n to store the number of elements.
•	Integer array arr[10] to hold up to 10 elements.
•	Integer pointer parr and initialize it to point to the array arr.
Step 3: Read the value of n (number of elements) from the user.
Step 4: Loop from i = 0 to i < n:
•	Read an integer value and store it in the address parr + i using pointer arithmetic.
Step 5: Loop from i = 0 to i < n:
•	Print the element at *(parr + i) using pointer dereferencing.
Step 6: End the program.

## PROGRAM
    #include <stdio.h>
    
    int main() {
        int arr[10], *parr;
        int i, n;
    
        parr = arr;  // pointer points to the array
    
        printf("Enter number of elements (max 10): ");
        scanf("%d", &n);
    
        if (n > 10 || n <= 0) {
            printf("Invalid number of elements.\n");
            return 1;
        }
    
        // Reading elements
        printf("Enter %d elements:\n", n);
        for (i = 0; i < n; i++) {
            scanf("%d", parr + i);
        }
    
        // Displaying elements
        printf("Array elements are:\n");
        for (i = 0; i < n; i++) {
            printf("%d ", *(parr + i));
        }
        printf("\n");
    
        return 0;
    }


## OUTPUT
Enter number of elements (max 10): 6
Enter 6 elements:
10 20 30 40 50 60
Array elements are:
10 20 30 40 50 60 

 

## RESULT

Thus the C program to read and display an array of any 6 integer elements using pointer has been executed


