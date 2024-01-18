# Section 2

## printf()

basic usages
```c
printf("CodeBlocks?\n is a widely used IDE for C");
```
```c
printf("It is actually used with C\\C++ languages");
// for one \, use \\
```
```c
printf("Believe it or not, \"C\" is very essential");
// to make "" in a "", use \"
```

## Commend line
```c
\* I really hate when someone commend a whole book
in this multiline commend sections 
I just want to look at the other solutions
not you super irrelavent thoughts
really irritating *\
// If the kata is too easy for you go and find harder one
```

## Data Types

### Basic Data types

int | %d  
float | %f  
double | %lf ( long float )  
char | %c  

Common ways to define and print a basic variable:
```c
int num1 = 1;
float num2;
num2 = 1.5;
double num3, num4;
num3 = 3.14159265358; // it will only print 6 digit after dote
num4 = 2.17;
char eulers_num = 'e', complex = 'i';
// 1 bite, just one character

printf("All the numbers I have: %d, %.1f, %lf, %.2lf, %c, %c",num1,num2,num3,num4,eulers_num,complex);
// % +.+ number of digits you want it to be shown + variable type
```

## scanf()
It is basically input()
```c
printf("Give me a number then I will tell you if it is even or odd\n"
        "number should be under 21 digits,\n"
        "I have already used \"unsigned long long int\" \n"
        "which is the built-in integer type"
        "that can represent highest numbers of digits possible directly in C\n"
        "so don't you dare enter a longer num : ");

unsigned long long int number; // define a variable that would store the input
scanf("%llu", &number);
// take an input with scanf() function and assign it to "number" variable
    if (number % 2 == 0){
        printf("%llu is even", number);
    } else{
        printf("%llu is odd", number);
    }

```
Sometimes the scanf() function may detect the "\n" in the print command as a character and break the program.
In order to avoid this:
```c
scanf(" %c", &input) 
// use a space before %c
```

## sizeof()
Simply returns the bit size of the given variable
```c
int num1 = 1;
float num2 = 1.5;
double num3 = 3.14159265358;
char character = 'A';  // make sure you DON'T USE DOUBLE QUOTES, use SINGLE QUOTES
/*sizeof() func returns the bit size (it returns a number)
    %lu is used with sizeof()
    because sizeof() returns the size of an object in bytes as an unsigned long value.
    so "%lu" means "long unsigned",
    use it to avoid any data type mismatches: */
printf("The bite size of \"%d\" is %lu \n", num1, sizeof(num1));
printf("The bite size of \"%.3f\" is %lu \n", num2, sizeof(num2));
printf("The bite size of \"%lf\" is %lu \n", num3, sizeof(num3));
printf("The bite size of \"%c\" is %lu \n", character, sizeof(character));

//sizeof() can also return the bite of data types itself:
printf("The bite size of a/an %c is %lu \n", 'i', sizeof(int));
// single quotes for a character, double quotes for a string:
printf("The bite size of a/an %s is %lu \n", "float", sizeof(float));
printf("The bite size of a/an %s is %lu \n", "double", sizeof(double));
printf("The bite size of a/an %s is %lu \n", "character", sizeof(character));
```

## Const and Define

Const (consonant) and define are used for defining a variable that can't be changed
```c
const int num1 = 1.5;
num1 = 2.5;
// code does't work because num1 can't be changed
printf("%f", num1);
```
Define works out of the main function btw
```c
#include <stdio.h>=
#include <stdlib.h>
#define PI 3.14

int main()
{
    printf("%f", PI);
    return 0;
}
```

## Operators

### Arithmatic Operators
>```c
> int x = 5
>```

| Operator | Usage | Output |
|  :----:  |:----: |  ---:  |
| +  | x = x + 5 | 10 |
| -  | x = x - 5 | 0 |
| *  | x = x * 5 | 25 |
| /  | x = x / 5 | 1 |
| %  (modulo) | x = x % 5 | 0 |
| ++ | ++x | 6 |
| -- | --x | 4 |
```c
int x = 1;
printf("%d", ++x); 
// output will be "2"
``` 

### Assingment Operators
>```c
> int x = 5
>```

| Operator | Usage | Output |
|  :----:  |:----: |  ---:  |
|  =  | x  = 3 | 3 |
| +=  | x += 3 | 8 |
| -=  | x -= 3 | 2 |
| *=  | x *= 3 | 15 |
| /=  | x /= 3 | 1 |
| %=  | x %= 3 | 2 |
```c
int x = 5;
printf("%d", x %= 3 ); 
// output will be "2"
``` 

### Comparison Operators

>```c
> int x = 5, y = 10; // Use coma between variables
>```
```
x == y  
Is it equal? __ YES __ return 1   
           |
           | __  NO __ return 0 [x] 
                                  
```
```
x != y  
Isn't it equal? __ YES __ return 1 [x]
              |
              | __  NO __ return 0
                                  
```
| Operator | Usage | Output |
|  :----:  |:----: |  ---:  |
| == | x == y | 0 |
| != | x != y | 1 |
| <  | x < y  | 1 |
| >  | x > y  | 0 |
| <= | x <= y | 1 |
| >= | x >= y | 0 |
```c
int x = 5, y = 10;
printf("%d", x != y ); 
// output will be "1"
``` 

### Logical Operators
>It is actually similar to math logic

| Operator | Usage | Output |
|  :----:  |:----: |  ---:  |
|  && (∧) | T && T | 1 |
|         |  else  | 0 |
|  // (V) | F && F | 0 |
|         |  else  | 1 |
|   ! (') | !( T ) | 0 |

// is actually || but table content dosen't allow me to write in it

```c
int x = 5, y = 10;
printf("%d", !(x < y || y < x) ); 
// output will be "0"
``` 


## if conditions
I think the ***FizzBuzz Game*** one of the best examples for this :
```c
for (int i = 1; i <= 100; i++) {
    if (i % 3 == 0 && i % 5 == 0) {
        printf("FizzBuzz ");
    } else if (i % 3 == 0) {
        printf("Fizz ");
    } else if (i % 5 == 0) {
        printf("Buzz ");
    } else {
        printf("%d ", i);
    }
```
> And there is an another way to aproach this simulation:
```c
 for (int i = 1; i <= 100; i++) {
        if (i % 3 == 0 || i % 5 == 0) { 
        //  checking if it can be divided by 3 or 5 or both
            if (i % 3 == 0) {
                printf("Fizz");
            }
            if (i % 5 == 0) {
                printf("Buzz");
            }
            // it requaires two seperated if statements
            // "else if" does not work since it can not cover two conditions at the same time
            // so we use nested if conditions 
        } else {
            printf("%d", i); 
            // if "i" can not be devided any of the numbers given, just return the number
        }
        
        printf("\n");
        // since it works in the for loop, 
        // it should return all numbers in a new line 
    }
```

## for loop

```
for (initializationStatement; testExpression; updateStatement){
    //code here
}
```
More clear expression:
```
for(startPoint; condition; step)
```
```c
int i;
for(i=1; i<=5; i++) {
    printf("%d ",i);
}
```
>sum function example:
```c
int i, number, result=0;
printf("Please give a number: ");
scanf("%d", &number );

for (i=0; i<=number; i++){
    result += i;
}
printf("Sum of the numbers up to %d is %d",number,  result);
```
>Here is a block of code that prints specified number of " * ":
```c
int graph[10];

for (int i=0; i<10; i++)
{
    printf("\n%d. item: (Please enter) ",i+1);
    scanf("%d", &graph[i]);
}

for (int i=0; i<10; i++)
{
    printf("\n%4d. item:%5d --> ",i, graph[i]); // use %4d and %5d to alter spaces
    for (int j=0; j<graph[i]; j++)
    {
        printf("*");
    }
}
```
## while loop

```
while (condition) {
    //code here
}
```
```c
int i, number, result=0;
printf("Please give a number: ");
scanf("%d", &number );

while (i <= number){
    result += i;
    i++; 
    // don't forget to add 1 
    // or while loop executes forever, fr...
}
printf("Sum of the numbers up to %d is %d",number,  result);
```

> ###  do while 
first do  
then check the condition
```c
do {
    //code here
} while (condition);

// Use it when you want the code to run 
// at least once, without checking the condition 
```
> ###  break & continue

```c
int input, i=0;
printf("Which number would you like me to count to (I only know how to count to 100 btw): ");
scanf("%d", &input);
while (i<input){
    i++;
    if (i % 13 == 0){
        printf("I don't like 13. \n");
        continue;
    }
    if (i == 100) {
        break;
    }
    printf("%d \n", i);
}

    return 0;
```

> do while is very conveninent when it comes to get inputs from the user over and over again, here is an example:

```c
#include <stdio.h>
int main()
{
   int num;

   do {
        int fac=1; // the result should be redefined at the beginning of each iteration
        printf("Give me a positive integer and I will calculate the factorial of it: ");
        scanf("%d", &num);

        if (num>0)
        {
            for (int i=num; i>1; i--)
            {
                printf("%d x ",i);
                fac *= i;
            }
            printf("1 = %d \n", fac);
        }else
            continue;

    }while (num <= 0); // it will continue to ask until the user enters a positive number


    return 0;
}
```

## Switch-Case 

Similar to dictionary structure
```
switch (input) {
    case 'input' :  // code here ;
    break; 
    case 'input' :  // another code here ;
    break;
    ...
    // if you don't code "break", it will check all the cases
}
```

> Basic calculater :

```c
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h> // Include for scanf format specifier "%c"

int main() {
    char oprt;
    float num1, num2;
    printf("Enter two numbers pls: ");
    scanf("%f %f", &num1, &num2); 

    printf("Choose an operator pls (+ * - /): ");
    scanf(" %c", &oprt);

    switch (oprt) {
        case '+': printf("%f + %f = %f", num1, num2, num1 + num2);
        break;
        case '-': printf("%f - %f = %f", num1, num2, num1 - num2);
        break;
        case '*': printf("%f * %f = %f", num1, num2, num1 * num2);
        break;
        case '/': if (num2 != 0) {
                      printf("%f / %f = %f", num1, num2, num1 / num2);
                  } else {
                      printf("Division by zero is not allowed.");
                  }
        break;
        default:  printf("Invalid input, try again pls");
    }

    return 0; 
}
``` 

## Booleans 
It is a data type that can only store "true" (1) or "false" (0)  
Here is an example:

> Prime number or not?

```c
#include <stdio.h>=
#include <stdlib.h>
#include <stdbool.h>  // don't forget this

int main() {
    bool check = true;  // defining a boolean
    int number;
    printf("Give me an integer and I'll tell you whether it is a prime number or not: ");
    scanf("%d", &number);

    if (number < 2)  // if the number is smaller than 2, don't need to check anyting
    {
        printf("%d is not a prime number.", number);
    }
    else  // if the number is 2 or bigger than 2, execute this
    {
        for (int i = 2; i*i <= number; i++)  // if the number is 2 or 3, it doesn't go into that block
        {
            if (number % i == 0)
            {
                check = false;  // if the number can be divided by i, return false
                break;
            }
        }

        if (check)  // if the check is true (returns 1)
        {
            printf("%d is a prime number.", number);
        }
        else  // if the check is not true (returns 0)
        {
            printf("%d is not a prime number.", number);
        }
    }

    return 0;
}
```

## Math.h Library

> Basic calculator 2:

 ```c
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <math.h>  // don't forget this

int main() {
    char oprt;
    float num;
    int power;
    printf("Enter a number please: ");
    scanf("%f", &num);

    printf("Choose an operator please (c for ceil, f for floor, s for sqrt, p for pow, a for abs): ");
    scanf(" %c", &oprt);  // Note that switch statement can only use one character as a case

    switch (oprt) {
        case 'c': printf("%f", ceil(num));  // to round to the nearest greater number
        break;
        case 'f': printf("%f", floor(num));  // to round to the nearest smaller number
        break;
        case 's': printf("%f", sqrt(num));
        break;
        case 'p' : printf("Enter the power please: ");
                   scanf("%d", &power);
                   printf("%f", pow(num, power));
        break;
        case 'a': printf("%f", fabs(num));  // for integers-> abs \ for floating numbers-> fabs
        break;
        default:  printf("Invalid input, try again please");
    }

    return 0;
}
```



## Type casting

to change the type

```c
printf("To sum, enter two numbers pls \n: ");
float num1, num2;
scanf("%f %f", &num1,&num2);

printf("Actual Result: %lf \n", num1 + num2);

// forget about the decimal places (digits after the comma)
printf("Basic Result: %d\n", (int)num1 + (int)num2);
```


## ASCII table

Evey character has a numeric symbol

for exemple 'a' = 97, 'b' = 98, ..., 'z' = 122 ...

Let's print ASCII codes of characters 
and then whole alphabeth with the help of ASCII codes:

```c
for (int a='a'; a<='z'; a++)  // so 'a' means 97 and so on
{
    printf("%d\t", a);
}
printf("\n");
for (int a='a'; a<='z'; a++) // using 'a' as a counter for for loop
{
    printf("%c\t", a);  // and printing them as characters
}
```

## Arrays

```c
int myArray[10] = {1,2,3,4,5,6,7,8,9,10} 
// don't forget the curly brackets
```
more clear expression here:
```
(types of the items) (name of the array)[size]
```

Let's assign this items to an array with for loop;
```c
int arr[5];
for (int i=0; i<5; i++)
{
    arr[i] = i * 2;
    printf("%d \n", arr[i]);
}
``` 
Let's have the user assign these items and then sum them:
```c
    printf("Enter 5 items to assign to array: \n");
    int sum, arr[5];
    for (int i=0; i<5; i++)
    {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }
    printf("Sum of the nums is: %d", sum);
```

> Arrays can be nested and this type of arrays are named
> Multidimensional Arrays, here is an example:

> Checking Tic-Tac-Toe Gameboard

```c
    int board[3][3] =
        {{1, 2, 2},
         {2, 1, 1},
         {1, 0, 1}};

    int winner = 0;  // Nobody has win, yet

    for (int i = 0; i < 3; i++) {
        // Check rows
        if (board[i][0] == board[i][1] && board[i][1] == board[i][2]) {
            winner = board[i][0];
            break;
        }
        // Check columns
        if (board[0][i] == board[1][i] && board[1][i] == board[2][i]) {
            winner = board[0][i];
            break;
        }
    }

    // Check diagonals for a winner
    if (board[0][0] == board[1][1] && board[1][1] == board[2][2]) {
        winner = board[0][0];
    }
    if (board[0][2] == board[1][1] && board[1][1] == board[2][0]) {
        winner = board[0][2];
    }

    // Display the board and result
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j] == 1) {
                printf("X ");
            } else if (board[i][j] == 2) {
                printf("O ");
            } else {
                printf(". ");  // Display a dot for empty cells
            }
        }
        printf("\n");
    }

    if (winner == 1) {
        printf("Player X wins\n");
    } else if (winner == 2) {
        printf("Player O wins\n");
    } else {
        printf("No winner\n");
    }

```

## Strings

String is an array of characters  

Defining a string:
```c
// to define characters one by one
char name[] = {'l','o','f','i','\0'}; 
// don't forget the '\0' -> it shows the string is end

char surname[] = "cat";
// int this way, no need to '\0' but it still holds 4 bite in the memory

printf("My name is %s %s \nWhat is yours? ", name, surname);
char yourName[100];  // This can hold up to 99 characters plus the null terminator
scanf(" %[^\n]", &yourName);
// This format specifier reads characters until a newline character ('\n') is encountered
// This allows the user to enter their full name with spaces
printf("Good luck with your coding profession %s", yourName);
```

To make the first char uppercase: 
```c
#include <ctype.h> // don't forget to include library 
yourName[0] = toupper(yourName[0]);  // making the first char upper and replacing it 
```


### strlen()

To declare the size of the given string

```c
char name[100];
printf("Your name? ", name);
scanf(" %[^\n]", &name);

printf("Your name is %d character long. \n", strlen(name));
printf("Your name hold %d bite in memory.", sizeof(name));
// it shows the difference between strlen() and sizeof()
```

### strcmp() and strncmp()

It is used to compare strings
```
strcmp(firstString, secondString)
    if firstString < secondString __ returns -1
    if firstString == secondString __ returns 0
    if firstString < secondString __ returns 1

(According to ASCII codes)
```
```
strncmp(firstString, secondString, number)
// number -> number of characters which will be considered
// works as the same...
```

>Let's find the alphabetically first strign in the given array:
```c
char alp[][4] = {"cba", "bca", "abc"};
char firstOne[4];
strcpy(firstOne, alp[0]); // Copy the first string to firstOne

for (int i = 1; i < 3; i++) {
    if (strcmp(alp[i], firstOne) < 0) {
        strcpy(firstOne, alp[i]); // Copy the smaller string to firstOne
    }
}

printf("Alphabetically first string is: %s\n", firstOne);
```

### strcpy() and strncpy()

It is used to copy strings

```
strcopy(firstString, secondString)

secondString is copied to firstString
```
```
strncpy(firstString, secondString, number)

secondString is copied to firstString
works as the same 
and the number is like a limit here
```

Note that, when using strncpy, it would help  
if you define the string even as an empty char  
otherwise it would cause some unexpected result, so:

```
firstStirng[] = "";  // define it as en empty string
```

And note that;
strncpy() is considered more safe than the strcpy() function
So use strNcpy()

It can also be used for overwriting:
```c
char str1[] = "bonne";
char str2[] = "seiree";
char result[100] = "";

strcpy(result, str1);
strncpy(result+3, str2, 5);  // copying over the string, starts rewriting from 3. index

printf("%s", result);
// output: bonseire
```
### strcat() and strncat()

It is used to concatenate(combine) two strings  
by appending the characters of the second string to the end of the first string

```c
char warning[100];
char fact[100] = "John Wick is the best.";

strcpy(warning, "Don't mess ");
strcat(warning, "with ");
strncat(warning, fact, 9);

printf("%s", warning);

// output: Don't mess with John Wick
```

### taking input with gets() and fgets()

```
gets(input)  // doesn't recommend to use couse of security problems

fgets(input, sizeof(input), file)
// here the file is "stdin"
```

```c
char name[100], profession[100];

printf("Enter your name pls: ");
gets(name);

printf("Hi %s, what is your profession?", name);
fgets(profession, sizeof(profession), stdin);

printf("It must be a hard job. %s", profession);
```

### strrev()

It reverses the string

```c
char name[] = "Bob Returner";
printf("%s", strrev(name));
```

### strlwr() and strupr()

They make all the characters lower and upper case respectively
```c
char name[] = "Bob Lowever";
printf("%s", strlwr(name));
```
```c
char name[] = "Bob Upperer";
printf("%s", strupr(name));
```


## Functions

### Functions that doesn't return something
Example: 
```c
void evenOrOdd(num)
{
    if (num % 2 == 0)
    {
        printf("%d is even", num);
    }
    else
    {
        printf("%d is odd", num);
    }
}


int main() {
    int input;
    printf("Enter a number pls: \n");
    scanf("%d", &input);
    evenOrOdd(input);

    return 0;
}
```

### Functions that returns something
Example: 
```c
int evenOrOdd(num)
{
    if (num % 2 == 0)
    {
        return 1;
    }
    else
    {
        return 0;
    }
}


int main() {
    int input;
    printf("Enter a number pls: \n");
    scanf("%d", &input);
    if (evenOrOdd(input))
    {
        printf("%d is even", input);
    }
    else
    {
        printf("%d is odd", input);
    }
    return 0;
}
```

### Global and Local Variables
Here is an example:
```c
void printx()
{
    int x=3;  
    // it is in a fun, so doesn't matter what is going on outside
    printf("%d", x);
}

int x = 1;

int main() {
    int x = 2;  // it is in inner brackets os it take precedence
    printf("%d\n",x);

    printx();

    return 0;
}

// Output: 
// 2
// 3 
```
So local variables take precedence


 ### Pointers (basically)

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int x;
    int *p;  // declaring that p is a pointer
    x = 5;
    p = &x;  // declaring that p points x (p stores the adress of x)

    printf("The address of x: %d \n", p);
    printf("The value of x : %d \n", *p);


    *p = 6;  // reaching the value of x and modifying it
    printf("The value of x : %d (modifeid) \n", *p);

    int** q;
    q = &p;

    printf("The address of p: %d \n", q);
    printf("The value of p : %d \n", *q);
    printf("The address of x: %d \n", *q);
    printf("The value of x : %d \n", **q);

    **q = 7;  // reaching the value of x and modifying it
    printf("The value of x : %d (modified again) \n", **q);

    return 0;
}
```

### Operating with the value and the address of a variable

Operating with the value of the variable requares a function that returns the final conclusion

On the other hand, opearating with the address of the variable is more conveninent in therms of memory saving and provides the ability of accessing and changeing the value directly.

> Here is an example

```c
#include <stdio.h>
#include <stdlib.h>

int decreasement(int a)  // Operating with the value
{
    int result = --a;
    return result;
}

void increasement(int a, int *result)  // Operating with the value
{
    *result = ++a;
}

int main() {
    int x = 5;
    int conclusion = decreasement(x);  // have to take the returned value of the function

    int outcome;  // prepeare a variable and send the address of it, function will be executed and it will change the value globally
    increasement(x, &outcome);

    printf("%d %d", conclusion, outcome);

    return 0;
}
```

## C Preprocessors

### Macro

#### Object-like macro
```c
#define PI 3.14
``` 

#### Function-like macro
```c
#define circleArea(r) (PI*r*r)  // returns the result
``` 

#### Predefined Macros
They are the macros that already defined in the stdio.h library
```c
int main() {
    printf("File : %s\n", __FILE__);
    printf("Date : %s\n", __DATE__);
    printf("Time : %s\n", __TIME__);
    printf("Line : %d\n", __LINE__);  // gives the line number 
    printf("STDC : %d\n", __STDC__);  // it returns 1 if the compiler conforms to the C standard.
    return 0;
}
```

### #undef
it removes a defined macro
```c
#undef PI
```

### #ifdef
if the macro is defined, it executes the code block it covers
```c
#include <stdio.h>
#include <stdlib.h>
#define e 2.17


int main() {
    #ifdef e
        printf("Approximate e as 2.17 \n");
    #endif

    int pi;
    #ifdef PI
        printf("Approximate pi as 3.14");
    #else
        printf("Please enter the value of pi: ");
        scanf("%d", &pi);
        printf("%d is approximated as the value of pi.", pi);
    #endif // remember that ifdef must be ended with this
    return 0;
}
```

### #if #else
Macros can also be checked with the help of #if
```c
#include <stdio.h>
#include <stdlib.h>
#define constant 7


int main() {
    int con;
    #if constant == 7
        printf("Approximate the constant as 7");
    #else
        printf("Please enter the value of the constant: ");
        scanf("%d", &con);
        printf("%d is approximated as the value of constant.", con);
    #endif
    return 0;
}
```

### #error
It used to throw an error mesage at the terminal
```c
#include <stdio.h>
#include <stdlib.h>
#define PI 4

#if !defined PI || PI != 3
#error PI is not defined or not aproximated as 3
#endif

int main() {

    return 0;
}
```