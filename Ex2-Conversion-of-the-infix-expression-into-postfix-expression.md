# Ex1(b) Conversion of the infix expression into postfix expression
## DATE:23/2/25
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Declare a character stack and set top = -1 to track stack operations.Read an infix expression as input.
2. Loop through the characters of the expression one by one.
3. If the character is an operand (letter or digit), print it directly.If it is a left parenthesis (, push it onto the stack.
If it is a right parenthesis ), pop and print from the stack until a left parenthesis is encountered.
4. If the character is an operator, compare its precedence with the operator on top of the stack using the priority() function.
Pop and print operators from the stack while they have higher or equal precedence, then push the current operator.
5. After traversing the entire expression, pop and print any remaining operators in the stack.
## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: Kamalesh S
RegisterNumber:  212223040083

#include<stdio.h>
#include<ctype.h>

char stack[100];
int top = -1;

void push(char x)
{
   stack[++top]=x;
}

char pop()
{
    if(top==-1)
    {
        return -1;
    }
    else
    {
        return stack[top--];
    }
}
int priority(char x)
{
    if(x=='('))
    {
        return 0;
    }
    if(x=='&'|| x=='|')
    {
        return 1;
    }
    if(x=='+' || x=='-')
    {
        return 2;
    }
    if(x=='*' || x=='/')
    {
        return 3;
    }
    if(x=='^')
    {
        return 4;
    }
    return 0;
}
char IntoPost(char *exp)
{
    char *e,x;
    e=exp;
    while(*e!='\0')
    {
        if(isalnum(*e))
        {
            printf("%c ",*e);
        }
        else if(*e=='(')
        {
            push(*e);
        }
        else if(*e==')')
        {
            while((x=pop())!='('))
            {
                printf("%c ",x);
            }
        }
        else
        {
            while(priority(stack[top])>=priority(*e))
            {
                printf("%c ",pop());
            }
            push(*e);
        }
        e++;
    }

    while(top != -1)
    {
       printf("%c",pop());
    }
    return 0;
}
int main()
{
    char exp[100];
    scanf("%d",exp);
    IntoPost(exp);
    return 1;
}

*/
```

## Output:

![alt text](image-1.png)

## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
