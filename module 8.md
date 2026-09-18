# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

## Aim:
To write a C program print the lowercase English word corresponding to the number

## Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
## Program:

```C
#include <stdio.h>

int main() 
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch (n) 
	{
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0;
}

```



## Output:

<img width="218" height="59" alt="image" src="https://github.com/user-attachments/assets/8d188d45-9eae-43ea-ae4b-ff6cb99d07c9" />


<img width="227" height="56" alt="image" src="https://github.com/user-attachments/assets/06c3fe8b-cc09-42f3-96cc-dc501ecbea95" />


<img width="228" height="55" alt="image" src="https://github.com/user-attachments/assets/e1ac9e44-eb29-444b-9917-d215fbaa1211" />






## Result:
Thus, the program is verified successfully

---
 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .

## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.

## Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:

``` c
#include <stdio.h>
#include <string.h>

int main() 
{
    char a[50];
    int i, d, c;

    printf("Enter a string of digits: ");
    scanf("%s", a);

    for (d = 0; d <= 9; d++) 
	{
        c = 0;
        for (i = 0; i < strlen(a); i++) 
		{
            if (a[i] == (d + '0')) 
			{
                c++;
            }
        }
        printf("%d ", c); 
    }

    return 0;
}

```



## Output:

<img width="460" height="51" alt="image" src="https://github.com/user-attachments/assets/05cd5105-eebc-4f50-b381-752373009e6b" />






## Result:
Thus, the program is verified successfully

---

# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.

## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
## Program:

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <stdbool.h>

void swap(char *x, char *y) 
{
    char temp = *x;
    *x = *y;
    *y = temp;
}


void reverse(char str[], int l, int r) 
{
    while (l < r) {
        swap(&str[l], &str[r]);
        l++;
        r--;
    }
}

bool next_permutation(char str[]) 
{
    int n = strlen(str);
    int i = n - 2;

    while (i >= 0 && str[i] >= str[i + 1]) 
	{
        i--;
    }

    if (i < 0) return false; 
    


    int j = n - 1;
    while (str[j] <= str[i]) 
	{
        j--;
    }


    swap(&str[i], &str[j]);


    reverse(str, i + 1, n - 1);

    return true;
}

int main() 
{
    char s[50];


    printf("Enter a string: ");
    scanf("%s", s);


    int n = strlen(s);
    for (int i = 0; i < n - 1; i++) 
	{
        for (int j = i + 1; j < n; j++) 
		{
            if (s[i] > s[j]) 
			{
                swap(&s[i], &s[j]);
            }
        }
    }


    printf("\nPermutations in lexicographical order:\n");
    printf("%s\n", s);
    while (next_permutation(s)) 
	{
        printf("%s\n", s);
    }

    return 0;
}

```



## Output:

<img width="478" height="231" alt="image" src="https://github.com/user-attachments/assets/8420cda4-2b94-4142-a813-4b0a815f38b1" />







## Result:
Thus, the program is verified successfully

---
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW.

## Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.

## Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:

```c
#include <stdio.h>

int main() 
{
    int n;
    printf("Enter n: ");
    scanf("%d", &n);

    int len = n * 2 - 1;

    for (int i = 0; i < len; i++) 
	{
        for (int j = 0; j < len; j++) 
		{
            int min = i < j ? i : j;
            min = min < (len - 1 - i) ? min : (len - 1 - i);
            min = min < (len - 1 - j) ? min : (len - 1 - j);

            printf("%d ", n - min);
        }
        printf("\n");
    }
    return 0;
}

```

## Output:

<img width="196" height="197" alt="image" src="https://github.com/user-attachments/assets/6bc09a3a-0ebb-4f30-806d-119743e0f56a" />




## Result:
Thus, the program is verified successfully

---

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

## Program:

```c
#include <stdio.h>

int square() 
{
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num; 
    
}

int main() 
{
    int result;
    result = square(); 
    printf("Square = %d\n", result);
    return 0;
}

```



## Output:

<img width="224" height="57" alt="image" src="https://github.com/user-attachments/assets/36309ee1-a318-416d-93f5-56b7440587bd" />


## Result:
Thus, the program is verified successfully


