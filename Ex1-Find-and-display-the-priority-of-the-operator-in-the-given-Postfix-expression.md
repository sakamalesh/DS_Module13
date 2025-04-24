# EX 1 Display operator precedence in the infix expression.
## DATE:
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Initialize and Define Operators Declare a character array ch containing a set of operators (e.g., +, /, *, |).
Define integer variables i and j for loop and priority value handling.
2. Use a for loop to iterate over each character in ch using strlen.
3. For each character, check if it is a valid operator (+, -, *, /,%, ^, &, |) using an if condition.
4.  If valid, call a priority() function (assumed to be defined elsewhere) to determine the priority level of the operator and store the result in j.
5.  Use a switch statement on j to print the corresponding priority level (e.g., "Lowest Priority", "Highest Priority") for each operator. 

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Kamalesh S
RegisterNumber: 212223040083

#include <stdio.h>
#include<string.h>
int main()
{
   int i,j;
   char ch[100]="+/*|";
   for(i=0;i<strlen(ch);i++)
   {
       if(ch[i]=='+'||
       ch[i]=='-'||
       ch[i]=='*'||
       ch[i]=='/'||
       ch[i]=='%'||
       ch[i]=='^'||
       ch[i]=='&'||
       ch[i]=='|')
       
    j=priority(ch[i]);
           switch(j)
        {    
            case 1:
                printf("%c  ----> ",ch[i]);
            printf("Lowest Priority\n");    
                break;
            case 2:
                printf("%c  ----> ",ch[i]);
            printf("Second Lowest Priority\n");
                break;
            case 3:
                printf("%c  ----> ",ch[i]);
            printf("Second Highest Priority\n");
                break;
            case 4:
                printf("%c  ----> ",ch[i]);
            printf("Highest Priority\n");    
        }    
    
    }return 0;

}
*/

```

## Output:
![alt text](image.png)


## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
