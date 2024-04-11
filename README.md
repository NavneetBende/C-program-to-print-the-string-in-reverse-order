Reverse a string in C
Today in this article we will learn how to reverse a string in C language. There are various method top reverse a sting that we will be discussing in this page.

Reversing a string is a technique so that the 1st character becomes the last character and so on.

Lets understand this with the help of an example:- 

Input sting:- RITIKA
Output sting:- AKITIR
reverse a string
Algorithm
Step 1. Take the string which you have to reverse as the input variable says str.
Step 2:- Calculate the length of the string. The actual length of the string is one less than the number of characters in the string. Let actual length be len.
Step 3:- Use a for loop to iterate the string using a temporary variable to swap the elements.
Step 4:- Print the reversed string.
C-Program-to-Reverse-A-String
C Code :-
Method 1
Run
#include <stdio.h>

#include <string.h>  

// function definition of the revstr() 
void revstr(char *str1) 
{ 
  // declare variable 
  int i, len, temp; 
  len = strlen(str1); // use strlen() to get the length of str string 

  // use for loop to iterate the string 
  for (i = 0; i < len/2; i++) 
  { 
  // temp variable use to temporary hold the string 
   temp = str1[i]; 
   str1[i] = str1[len - i - 1]; 
   str1[len - i - 1] = temp; 
  } 
 } 

int main() 
{ 
  char str[50]="priyanka"; // size of char string 
  pri

  printf (" \n Before reversing the string: %s \n", str); 

  // call revstr() function 
  revstr(str); 
  printf (" After reversing the string: %s", str); 
 }
Output:-
Before reversing the string: priyanka 
After reversing the string: aknayirp
Method 2
We can also do the same by using build in functions.

like strrev() in C programming language
strrev() is a built in function in C which is comes under string.h header file
this function returns the string after reversing it.
Run
#include <stdio.h>

#include <string.h>
int main() 
{ 
  // declare the size of character string 
char str[100] = "Ritika"; 

// use strrev() function to reverse a string 
printf ("After the reverse of a string: %s ", strrev(str)); 
return 0;
}
Output:-
Enter a string to be reversed: Ritika
After the reverse of a string: akitiR
Method 3
We can also reverse the string by storing the reverse in another array and then print.

The idea is to transfer the string to another string in a reverse manner let the another array is rev.
All we need is the size of the string.
The method is to initialize a character array of the equal size and start copying the elements of the input string from the end.
And display the rev
Run
#include <stdio.h>

#include <string.h>

int main() {
    char str[1000] = "Priya", rev[1000];
    int i, j, count = 0;
    printf("String Before Reverse: %s", str);
    // finding the length of the string
    while (str[count] != '\0') {
        count++;
    }
    j = count - 1;
    // reversing the string by swapping
    for (i = 0; i < count; i++) {
        rev[i] = str[j];
        j--;
    }
    printf("String After Reverse: %s", rev);
    return 0;
}
Output:-
String Before Reverse: priya
String After Reverse: ayirp
Method 4
This includes use of two pointers one at the starting and one at the end.
the characters are then reversed one by one
The process of reversing the string is done with the help of two pointers.
Run
#include <stdio.h>

#include <string.h>
// function declaration str_len that  
int str_len(char *ptr) 
{ 
  int i = 0; 
  while ( *(ptr + i) != '\0') 
  i++; 
  return i; 
}
void revstr(char *st) 
{ 
  int len, i; 
  char *start, *end, temp; 
  len = str_len (st); 
  start = st; 
  end = st; 

  for (i = 0; i < len - 1; i++) 
  end++; 

  for (i = 0; i < len/2; i++) 
  { 
    temp = *end; 
    *end = *start; 
    *start = temp; 

    start++; 
    end--; 
   } 
 }

int main() 
{ 
  char st[50]="priyanka"; 
 
  revstr(st); 
  printf (" The reverse string is: %s", st); 
  return 0; 
}
Output:-
 Enter a string to be reversed: priyanka
The reverse string is: aknayirp
