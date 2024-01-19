# BasicStringReplace
A Program in C for the following operations on Strings, without using Built-in functions.  
#include <stdio.h> 
int stringmatch_and_replace(char[], char[], char[]); 
int stringlength(char[]); 
void main() 
{ 
char str[100],pat[50],rep[50]; 
printf("Enter the main string\n"); 
gets(str); 
printf("\nEnter a pattern string\n"); 
gets(pat); 
printf("\nEnter a replacement string\n"); 
gets(rep); 
if (stringmatch_and_replace(str, pat, rep)) 
printf("\n The Resultant string is %s\n",str); 
else 
printf("\n Pattern %s is NOT found in %s\n", pat, str); 
} 
//Function to find and Replace all occurrences of PAT in STR with REP if  
//PAT exists in STR 
int stringmatch_and_replace(char str[100],char pattern[50], char  
replace[50]) 
{ 
int i,j,c,m,n,found=0; 
//get the length of STR and PAT  
n=stringlength(str); 
m=stringlength(pattern); 
i=0; 
//logic to find and Replace all occurrences of PAT in STR with REP if  
//PAT exists in STR 
while(i<=(n-m)) 
{ 
c=i; 
j=0; 
//logic for Individual PAT occurrence matching 
while(str[c]==pattern[j]) 
{ 
c++; 
j++; 
if(pattern[j]=='\0') 
{ 
found=1; 
j=0; 
//logic for replacing each occurrence of PAT with REP 
while(j<m) 
str[i+j] = replace[j++]; 
i=i+m; 
j=0; 
} 
} 
i++; 
} 
// 
if(found==1) 
return 1; 
return 0; 
} 
//returns the length of String 
int stringlength(char s[100]) 
{ 
int i, lenght=0; 
for(i=0; s[i]!='\0'; i++) 
lenght++; 
return lenght; 
}
