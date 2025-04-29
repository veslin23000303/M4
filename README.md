# EX-16-LEFT-SHIFT-OPERATION
## AIM
To write a C Program to perform the basic left shift operation for 44 integer number with 3 shifts.

## ALGORITHM
1.	Start the program.
2.	Assign values of a and b as 44 and 3.
3.	Use left shift operator (<<) and shift the value of a three times.
4.	Display the result.
5.	Stop the program.

## PROGRAM

```

#include <stdio.h>

int main() {
    int num = 44;
    int shifts = 3;
    int result;
    result = num << shifts;
    printf("Original number: %d\n", num);
    printf("After left shifting by %d positions: %d\n", shifts, result);
    return 0;
}


```

## OUTPUT






![image](https://github.com/user-attachments/assets/20792a4b-15bd-4b4d-ab4c-4fbd8847d6ff)



## RESULT
Thus the program to perform the basic left shift operation for 44 integer number with 3 shifts has been executed successfully.




 
 


# EX-17-TWO-NUMBERS-ARE-EQUAL-OR-NOT


## AIM

Write a C Program to check whether the two numbers are equal or not using simple if statement.

## ALGORITHM

1.	Start the program.
2.	Read two numbers.
3.	If first number is equal to second number, display both are equal.
4.	Otherwise display both are not equal.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int num1, num2;
    printf("Enter first number: ");
    scanf("%d", &num1);
    printf("Enter second number: ");
    scanf("%d", &num2);
    if (num1 == num2) {
        printf("The numbers are equal.\n");
    } else {
        printf("The numbers are not equal.\n");
    }

    return 0;
}


```


## OUTPUT
![image](https://github.com/user-attachments/assets/e6ad4b36-ce91-438d-916b-4b1cea3b0c7d)

           
## RESULT

Thus the program to check whether the two numbers are equal or not using simple if statement has been executed successfully
 
 


# EX-18-STRING-LOWERCASE-CONVERSION
## AIM
Write a C Program to convert the given string into lowercase.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using tolower( ) function convert the given string into its lowercase.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = tolower(str[i]); 
    }
    printf("The string in lowercase: %s", str);

    return 0;
}



```


## OUTPUT

![image](https://github.com/user-attachments/assets/ddeb5503-c781-40d7-8ffc-71022b2d0782)



## RESULT
Thus the program to convert the given string into lowercase has been executed successfully
 
 


# EX-19-COUNT-OF-WORDS-IN-A-STRING
## AIM
Write a C Program to count the total number of words in a given string using do While loop.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using for loop, inspect the string character by character.
4.	Whenever a space is encountered increment count by 1.
5.	Display the result.
6.	Stop the program.

## PROGRAM

```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    int count = 0, i = 0;
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    do {
        while (isspace(str[i])) {
            i++;
        }
        if (str[i] != '\0') {
            count++; 
            while (str[i] != '\0' && !isspace(str[i])) {
                i++;
            }
        }

    } while (str[i] != '\0'); 
    printf("Total number of words: %d\n", count);

    return 0;
}


```

## OUTPUT


![image](https://github.com/user-attachments/assets/14fc853c-081e-4e15-9039-24988146dcf8)



## RESULT
Thus the program to count the total number of words in a given string using do While loop has been executed successfully
 
 


# EX  -20 -COMPARING TWO STRINGS
## AIM
write a Program to compare two strings without using strcmp().
## ALGORITHM
Step 1: Start the program.
Step 2: Declare two character arrays c1 and c2 of size 100 to store the strings. Also, declare an integer variable
             flag and initialize it to 0, and i for indexing.      
Step 3: Read the first string c1 using scanf("%[^\n]", c1); — this reads input until a newline is encountered 
            (i.e., can include spaces).
Step 4: Read the second string c2 using scanf("%s", c2); — this reads input until a space or newline (i.e., no 
            spaces in the second string).
Step 5: Start comparing characters of both strings from index i = 0.
Step 6: Repeat the following while neither c1[i] nor c2[i] is '\0' (i.e., end of string):
•	If c1[i] is not equal to c2[i], set flag = 1.
•	Increment i by 1.
Step 7: After the loop, check the value of flag:
•	If flag == 0, print "strings are same".
•	Otherwise, print "strings are not same".
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    char str1[100], str2[100];
    int i = 0;
    int result = 0; // 0 for equal, negative for str1 < str2, positive for str1 > str2

    printf("Enter the first string: ");
    scanf("%s", str1); // Use %s to read the whole string.  No need for &
    printf("Enter the second string: ");
    scanf("%s", str2);

    // Compare characters until a null terminator is reached in either string.
    while (str1[i] != '\0' && str2[i] != '\0') {
        if (str1[i] < str2[i]) {
            result = -1; // str1 is less than str2
            break;       // Exit the loop, no need to compare further
        } else if (str1[i] > str2[i]) {
            result = 1;  // str1 is greater than str2
            break;       // Exit the loop
        }
        i++; // Move to the next character in both strings
    }

    // Handle cases where one string is a prefix of the other.
    if (result == 0) { // If the loop finished without finding a difference
        if (str1[i] == '\0' && str2[i] == '\0') {
            result = 0; // The strings are equal
        } else if (str1[i] == '\0') {
            result = -1; // str1 is shorter (and thus less than) str2
        } else {
            result = 1;  // str2 is shorter (and thus less than) str1
        }
    }

    // Print the result
    if (result == 0) {
        printf("The strings are equal.\n");
    } else if (result < 0) {
        printf("The first string is less than the second string.\n");
    } else {
        printf("The first string is greater than the second string.\n");
    }

    return 0;
}


```

## OUTPUT
 
![image](https://github.com/user-attachments/assets/5f352933-40d2-4d8f-a70a-778732ebf48b)

## RESULT
Thus the C Program to compare two strings without using strcmp() has been executed successfully.

