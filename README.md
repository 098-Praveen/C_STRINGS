# C_STRINGS
INTRODUCTION TO STRINGS
A strings is multiple characters enclosed with double quotes terminated by null character '\0'
at the end of every string null character will be present
"HELLO"
THIS IS STRING BUT INTERNALLY C STORES THIS AS "H E L L O \0"

HOW STRING IS STORED?
char str[]="HELLO";
here char is the data type
str is array name 
[] indicates we are declaring an array
"hello" is string used to initialize the array
"COMPILER ADDS THE NULL CHAR AT THE END OF EVERY STRING"

FIRST PROGRAMME:
#include<stdio.h>
int main(void)
{
    char str[]="HELLO";
    printf("%s\n",str);
    return 0;
}
%s format specifier tells printf to print string.
when printing this string, C Processes its characters until it reaches the termination null character.

FIRST QUESTION:

char str[]="CAT";
here array size is 4 including null character.
string length is 3.
here also we access same like arrays using array index.

SECOND QUESTION:

char str1[]="CAT";
char str2[]={'C','A','T'};
here this is how we initialize the strings in 2 waqys but in second way we need to explicitly add the null character.

#include<stdio.h>
int main()
{
    char str[]={'c','a','t'};
    printf("%s\n",str);
    return 0;
}
here undefined behavior because we don't have the terminating character.
#include<stdio.h>
int main()
{
    char str[]={'c','a','t','\0'};
    printf("%s\n",str);
    return 0;
}
this is the right way.
OUTPUT GUESSING

#include <stdio.h>

int main(void)
{
    char str[] = {'C', 'A', 'T', '\0'};

  printf("%c\n", str[1]);
  printf("%c\n", str[3]);

  return 0;
}
HERE THE OUTPUT IS A
BECAUSE  it it trying to access null character in ascill null has nothing to print so A prints 
why not error here becuase it is not trying to access the outside of bound but within the bounds so it is right

STAGE 2:CHAR ARRAYS AND MEMORY:

#include<stdio.h>
int main()
{
    char str[]="DOG";
    printf("%zu\n",sizeof(str));
    return 0;
}
output is :4 because string length is 4 
size of operator returns the size in bytes of array 
string length is 3 here 

OUTPUT GUESSING:
WHAT ARE THE VALUES OF SIZEOF(STR) AND THE STRING'S LENGTH?
char str[] = "APPLE";
SIZE IS 6 AND STRING LENGTH IS 5

STAGE 3:
UNDERSTANDING THE NULL CHARACTER '\0':

HERE '\0' this and '0' this is different:
'\0' null character whose value is 0
'0' is digit represented as char
OUTPUT GUESSING:
#include <stdio.h>

int main(void)
{
  char str[] = {'A', 'B', '\0', 'C', 'D', '\0'};

  printf("%s", str);

  return 0;
}
ANS : AB
#include <stdio.h>

int main(void)
{
    char str[] = {'A', 'B', '\0', 'C', 'D', '\0'};

  printf("%c\n", str[3]);
    printf("%s\n", str);

  return 0;
}
ANS IS A AND C D
THE STRING ENDS AT THE FIRST NULL CHAR BUT NOT NECESSARILY AT THE END OF IT'S ARRAY:

#include <stdio.h>
#include<string.h>
int main(void)
{
    char str[] = "CAT";
printf("%zu\n", sizeof(str));
printf("%zu\n",strlen(str));
    return 0;
}
output is 4 and 3
array is including null character and string length is excluding null character 

STAGE 4: READING A STRING IN C:
DEFINITION:
 reading a string means accepting a sequence of characters from an input source , such as the keyboard and storing those 
 characters in a character array.

 #include <stdio.h>
#include<string.h>
int main(void)
{
    char str[6];
    printf("enter a string:");
    scanf("%3s",str);
    printf("%s\n",str);
    return 0;
}
user enters:hello
hel
like that we can specify how many we need to take from the entered string
QUESTION:

char str[20];
scanf("%19s", str);
USER ENTERS:
APPLE MANGO 
scanf reads characters until it encounters whitespace

READING STRING USING fgets()
#include <stdio.h>
#include<string.h>
int main(void)
{
    char str[16];
    printf("enter a string:");
scanf("%s",str);   
   //fgets(str,sizeof(str),stdin); //stdin is keyboard
    printf("%s\n",str);
    return 0;
}
scanf reads until space and fgets reads beyond spaces
