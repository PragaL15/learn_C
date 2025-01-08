1. Find if the string is isometric or not

```c
#include <stdio.h>
#include <stdbool.h>
#include <string.h>
int main() {
    char s1[100]; 
    scanf("%[^\n]",s1);
    getchar();
    char s2[100];  
    scanf("%[^\n]",s2);
    if (strlen(s1) != strlen(s2)) {
        printf("The strings are not isometric.\n");
        return 0;
    }
    int num1[256] = {0}; 
    int num2[256] = {0};
    int is_isometric = 1;
    for (int i = 0; s1[i] && s2[i]; ++i) {
        char c1 = s1[i];
        char c2 = s2[i];
        if (num1[c1] == 0 && num2[c2] == 0) {
            num1[c1] = c2;
            num2[c2] = c1;
        } else if (num1[c1] != c2 || num2[c2] != c1) {
            is_isometric = false;
            break;
        }
    }
    if (is_isometric) {
        printf("The strings are isometric.\n");
    } else {
        printf("The strings are not isometric.\n");
    }
    return 0;
}
```
**(or)**
```c
#include <stdio.h>
#include <string.h>
#include <stdbool.h>

int main() {
    char s1[100], s2[100];
    scanf("%[^\n]", s1);
    getchar();
    scanf("%[^\n]", s2);
    if (strlen(s1) != strlen(s2)) {
        printf("The strings are not isometric.\n");
        return 0;
    }
    for (int i = 0; s1[i]; ++i) {
        if (strchr(s1, s1[i]) - s1 != strchr(s2, s2[i]) - s2) {
            printf("The strings are not isometric.\n");
            return 0;
        }
    }
    printf("The strings are isometric.\n");
    return 0;
}
```

---

2. The first letter is caps of a word.

```c
#include<string.h>
#include<stdio.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  for(int i=0;i<len;i++){
    if(str[i-1]==' ' || i==0){
      printf("%c",toupper(str[i]));
    }
    else{
      printf("%c",tolower(str[i]));
    }
  }
}
```
---
3. Remove the duplicate letter from the string like ex:Hello --> Helo

```c
#include<string.h>
#include<stdio.h>
int main()
{
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int freq[256]={0};
  for(int i=0;i<len;i++){
    freq[(int)str[i]]++;
    if(freq[str[i]]==1)
    printf("%c",str[i]);
  }
}
```
---
4.  Remove the specific character from the string and print the rest of rest of the character.

```c
#include <stdio.h>
#include <string.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  getchar();
  char target;
  scanf("%c",&target);
  int len = strlen(str);
  for(int i=0;i<len;i++){
    if(str[i] == target){
      continue;
    }
    printf("%c",str[i]);
  }
}
```
---
5. To print the words whose size is less that the target number.

```c
#include <stdio.h>
#include <string.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  getchar();
  int target;
  scanf("%d",&target);
  int count =0;
  int i=0;
  char* token;
  char* tokens[100];
  int len = strlen(str);
  token = strtok(str," ");
  while(token != NULL){
    tokens[i++]=token;
    token=strtok(NULL," ");
    count++;
  }
  for(int j=0;j<i;j++){
    if(strlen(tokens[j])<target){
      printf("%s ",tokens[j]);
    }
  }
}
```
---
6. To convert railway time to normal time

```c
#include <stdio.h>
#include <stdlib.h>
int isValidTime(int hours, int minutes, int seconds) {
    if (hours < 0 || hours > 23) {
        return 0;  
    }
    if (minutes < 0 || minutes > 59) {
        return 0; 
    }
    if (seconds < 0 || seconds > 59) {
        return 0;  
    }
    return 1; 
}
int main() {
    char time[9];
    int hours, minutes, seconds;
    scanf("%s", time);
    if (sscanf(time, "%d:%d:%d", &hours, &minutes, &seconds) != 3) {
        printf("Invalid time format\n");
        return 1;  
    }
    if (isValidTime(hours, minutes, seconds)) {
        printf("Hour:%02d Minutes:%d Seconds:%d\n", hours, minutes, seconds);
    } else {
        printf("Invalid time\n");
    }

    return 0;
}
```
---
7. To find the most frequently appeared letter in string.

```c
#include <stdio.h>
#include <string.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int freq[256]={0};
  int len = strlen(str);
  for(int i=0;i<len;i++){
    if(freq[i]!=' ')
    freq[(int)str[i]]++;
  }
  int maxFreq=0;
  for(int i=0;i<256;i++){
    if(freq[i]>maxFreq)
    maxFreq=freq[i];
  }
for(int i=0;i<256;i++){
  if(freq[i]==maxFreq){
    for(int j=0;j<maxFreq;j++){
         printf("%c",i);
         break;
    }
  }
}
}
```
---
8. The smallest word and largest word in the whole string 

```c
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   int len = strlen(str);
   getchar();
   int count =0;
   char* token;
   char* tokens[100];
   token= strtok(str," ");
   int i=0;
   while(token != NULL){
     tokens[i++]=token;
     token=strtok(NULL, " ");
   }
     int max=strlen(tokens[0]);
     int min=strlen(tokens[0]);
     char* max_word=tokens[0];
     char* min_word=tokens[0];
   for(int j=0;j<i;j++){
     int count = strlen(tokens[j]);
     if(count>max)
     {
       max=count;
       max_word=tokens[j];
     }
     if(count<min){
       min=count;
       min_word = tokens[j];
     }
   }
   printf("%s\n",min_word);
   printf("%s",max_word);
   
}
```
---
9. Printing the alternate letters in a string 

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  char store[100];
  int len = strlen(str);
  int j=0;
  for(int i=0;i<=len;i+=2){
    if(str[i]!=' ')
    store[j++] = str[i];
  }
  store[j] = '\0';
  printf("%s",store);
}

```
---
10. Printing the alternate letters in a string in reverse order.

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  char* store[100];
  int len = strlen(str);
  int j=0;
  for(int i=1;i<len;i+=2){
      store[j++]=str[i];
  }
  store[j] = '\0'; 
  for(int i = 0;i<j;i++){
    printf("%c",store[i]);
  }
}

```
---
11. To have the first letter of the element as Capital letter

```c
#include <string.h>
#include<stdio.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  for(int i=0;i<len;i++){
    if(str[i-1]==' ' || str[i-1]=='\0'){
      str[i] = toupper(str[i]);
    }
    printf("%c",str[i]);
  }
}
```
---
12. To print only the symbols from the gvn string

```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  for(int i=0;str[i]!='\0';i++){
   if(!isalnum(str[i]) && !isspace(str[i])){
     printf("%c",str[i]);
   }
  }
}
```
---
13. To print only the consonants in the given string 

```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  for(int i=0;str[i]!='\0';i++){
    str[i]=tolower(str[i]);
    if(str[i]!='a' && str[i]!='e' && str[i]!='i' && str[i]!='o' && str[i]!='u'){
     printf("%c",str[i]);
   }
  }
}
```
---
14.  Replace specific char with another char and numbers
with 'n' . 'a' -> 'b'
,
't' -> 'g'
, number -> 'n' Input:
"Education4all"
, Output : "Educbgionnbll"

```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  char ch1='b';
  char ch2='g';
  int len = strlen(str);
  for(int i=0;str[i]!='\0';i++){
     if(str[i]=='a')
      str[i]=ch1;
     if(str[i]=='t')
     str[i] = ch2;
     if(isdigit(str[i])){
       str[i]= 'n';
     }
     printf("%c",str[i]);
  }
}

```
---
15. To print the frequency of each letter present in he string

```c
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   int len = strlen(str);
   getchar();
   int freq[256] = {0};
   for(int i=0;i<len;i++){
     freq[(int)str[i]]++;
   }
   for(int i=0;i<len;i++){
     if(freq[(int)str[i]]!=0){
       printf("%d --> %c\n",freq[str[i]],str[i]);
       freq[(int)str[i]] = 0;
     }
   }
}
```
---
16. Replace all the space with special characters

```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  char target = '@';
  for(int i=0;i<len;i++){
    if(str[i]==' '){
      str[i] = target;
    }
    printf("%c",str[i]);
  }
}
```
---
17. To print the first Uppercase character
```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  for(int i=0;i<len;i++){
    if(str[i] > 'A' && str[i]<'Z'){
       printf("%c",str[i]);
       break;
    }
  }
}
```
---
18. To print the first non repeating character in the string

```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int freq[256]={0};
  for(int i=0;str[i]!='\0';i++){
    str[i] = tolower(str[i]);
    freq[(unsigned char)str[i]]++;
  }
  for(int i=0;i<256;i++){
    if( freq[(unsigned char)str[i]]==1)
    {
      printf("%c",str[i]);
      break;
    }
  }
  }
```
---
19. Remove the duplicate characters and print he rest of the charecters

```c 
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int freq[256]={0};
  for(int i=0;str[i]!='\0';i++){
    str[i] = tolower(str[i]);
    freq[(unsigned char)str[i]]++;
  }
  for(int i=0;i<256;i++){
    if(freq[(unsigned char)str[i]]==1)
    {
      printf("%c",str[i]);

    }
  }
  }
```
---
20. Print only the repeating charecters in a given string.

```c 
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int freq[256]={0};
  for(int i=0;str[i]!='\0';i++){
    str[i] = tolower(str[i]);
    freq[(unsigned char)str[i]]++;
  }
  for(int i=0;i<256;i++){
    if(freq[(unsigned char)str[i]]>1)
    {
      printf("%c",str[i]);

    }
  }
  }
```
---
21. Check if the particular program is an anagram i.e input --> apple pleap  o/p --> it's anagram

```c 
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[100], str2[100];
    scanf("%[^\n]", str);
    getchar();  
    scanf("%[^\n]", str2);
    int freq[256] = {0};
    int freq2[256] = {0};

     for (int i = 0; str[i] != '\0'; i++) {
        if (isalpha(str[i])) {
            freq[tolower(str[i])]++;
        }
    }
    for (int i = 0; str2[i] != '\0'; i++) {
        if (isalpha(str2[i])) {
            freq2[tolower(str2[i])]++;
        }
    }
    int anagram = 1;
    for (int i = 0; i < 256; i++) {
        if (freq[i] != freq2[i]) {
            anagram = 0;
            break;
        }
    }
    if (anagram)
        printf("It's an anagram\n");
    else
        printf("Not an anagram\n");
    return 0;
}
```
---
22. Count the number of charecters in the gvn string and check if it is count prime number or not,

```c 
#include <string.h>
#include<stdio.h>
#include<ctype.h>
#include<math.h>
int main(){
  char str1[100];
  scanf("%[^\n]",str1);
  int count =0;
  int len = strlen(str1);
  for(int i=0;i<len;i++){
    if(str1[i]!=' '){
      count++;
    }
  }
  int is_prime =1;
  if(count<=1)
  is_prime=0;
  if(count ==2 || count == 3){
    is_prime=1;
  }
  if(count%2==0)
  is_prime=0;
  else
  for(int i=3;i<=sqrt(count);i+=2){
    if(count%i==0)
    is_prime=0;
    break;
  }
  printf("%d\n",count);
  if(is_prime)
  printf("It's prime");
  }
```

---
23. Printing the first occurance of the charecters

```c 
#include <stdio.h>
int main()
{
   char str[100];
   scanf("%[^\n]",str);
   char ch='a';
   int len = strlen(str);
   for(int i=0;i<len;i++){
     if(str[i]==ch){
       printf("%d",i);
       break;
     }
   }
}
```
---
24. Printing the last occurance of the charecters

```c 
#include <stdio.h>
int main()
{
   char str[100];
   scanf("%[^\n]",str);
   char ch='a';
   int str2[100];
   int len = strlen(str);
   for(int i=len-1;i>0;i--){
     if(str[i]==ch){
       printf("%d ",i);
       break;
     }
   }
   }
   ```
   ---
   25. Printing the all occurance of the charecters

   ```c 
  #include <stdio.h>
  int main()
  {
    char str[100];
    scanf("%[^\n]",str);
    char ch='a';
    int str2[100];
    int len = strlen(str);
    for(int i=len-1;i>0;i--){
      if(str[i]==ch){
        printf("%d ",i);
      }
    }
    }
   ```
   ---
   26. Count the occurance of a given letter in a string.

   ```c 
    #include <stdio.h>
    int main()
    {
    char str[100];
    scanf("%[^\n]",str);
    char ch='a';
    int str2[100];
    int count=0;
    int len = strlen(str);
    for(int i=len-1;i>0;i--){
      if(str[i]==ch){
        count++;
      }
    }
    printf("%d",count);
    }
   ``` 
   ---
   27. Find the frequency of each letter in a string

   ```c 
  #include <stdio.h>
  #include<string.h>

  int main()
  {
    char str[100];
    scanf("%[^\n]",str);
    int freq[256]={0};
    int len = strlen(str);
    for(int i=0;i<len;i++){
      str[i] = tolower(str[i]);
      freq[(unsigned char)str[i]]++;
    }
    for(int i=0;i<256;i++){
      if(freq[i]!=0){
        printf("%c --> %d\n",i,freq[i]);
      }
    }
    }
   ```
---
28. Delete the first occurance of a letter in the string

```c 
#include <stdio.h>
#include<string.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char letter;
   scanf("%c",&letter);
   int found = 0;
   int freq[256]={0};
   int len = strlen(str);
   for(int i=0;i<len;i++){
   if(str[i]==letter && !found){
     found=1;
   continue;
   }
   printf("%c",str[i]);
   }
   }
   ```
   ---
   29. Delete the last occurance of the letter in the string.

   ```c 
    #include <stdio.h>
    #include<string.h>
    int main()
    {
      char str[100];
      scanf("%[^\n]",str);
      getchar();
      char letter;
      scanf("%c",&letter);
      int lastIndex = 0;
      int freq[256]={0};
      int len = strlen(str);
      for(int i=0;i<len;i++){
      if(str[i]==letter){
        lastIndex=i;
      }
      }
      for(int i=0;i<len;i++){
      if(str[i]==letter){
      if(lastIndex==i)
      continue;
      }
      printf("%c",str[i]);
      } 
    }
```
---

30. Delete all the occurance of the letter from the string 

```c 
    #include <stdio.h>
    #include<string.h>

    int main()
    {
      char str[100];
      scanf("%[^\n]",str);
      getchar();
      char letter;
      scanf("%c",&letter);
      int freq[256]={0};
      int len = strlen(str);
      for(int i=0;i<len;i++){
      if(str[i]==letter){
      continue;
      }
      printf("%c",str[i]);
      }
    }
```
---
31.  Replace the first occurance of the letter with a wished letter

```c 
#include <stdio.h>
#include<string.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char letter;
   char wished = 'p';
   int first=0;
   scanf("%c",&letter);
   int freq[256]={0};
   int len = strlen(str);
   for(int i=0;i<len;i++){
   if(str[i]==letter && !first){
   first=1;
   str[i]=wished;
   }
   printf("%c",str[i]);
   }
   
}
```
---
32. Replace the last occurance of the letter with the wished letter

```c 
#include <stdio.h>
#include<string.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char letter;
   char wished = 'p';
   int last=0;
   scanf("%c",&letter);
   int freq[256]={0};
   int len = strlen(str);
   for(int i=0;i<len;i++){
   if(str[i]==letter){
   last=i;
   }
   }
   for(int i=0;i<len;i++){
   if(str[i]==letter){
   if(last == i)
   str[i]=wished;
   }
   printf("%c",str[i]);
   }  
}
```
---
33. Replace all the occurance with the wished letter in a string 

```c
#include <stdio.h>
#include<string.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char letter;
   char wished = 'p';
   scanf("%c",&letter);
   int freq[256]={0};
   int len = strlen(str);
   for(int i=0;i<len;i++){
   if(str[i]==letter){

   str[i]=wished;
   }
   printf("%c",str[i]);
   }
}
```
---
34. Find the occurrence of the alphabets, numbers and special characters.

```c 
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char letter;
   int cha[100];
   int num[100];
   int sym[100];
   int c=0;
   int n=0;
   int s=0;
   scanf("%c",&letter);
   int freq[256]={0};
   int len = strlen(str);
   for(int i=0;i<len;i++){
   if(isalpha(str[i])){
    cha[c++]=i;
   }
   if(isdigit(str[i])){
    num[n++]=i;
   }
   if(!isalpha(str[i]) && !isdigit(str[i]) && (str[i]!=' ')){
    sym[s++]=i;
   }
   }
   for(int i=0;i<c;i++){
     printf("\n%d is char",cha[i]);
   }
   printf("\n");
   for(int i=0;i<n;i++){
     printf("\n%d is digit",num[i]);
   }
    printf("\n");
   for(int i=0;i<s;i++){
    printf("\n%d is sym",sym[i]);
    
   }
}
```
---
35. Find the vowels and consonents from the given string.

```c
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   int consonants[100];
   int vowels[100];
   int con=0;
   int vow=0;
   int len = strlen(str);
   for(int i=0;i<len;i++){
   if(isalpha(str[i])){
     char low=tolower(str[i]);
   if(low=='a' || low=='e' || low=='i' || low=='o' || low=='u' ){
     vowels[vow++]=i;
   }
   else
    consonants[con++]=i;
   }
   }
   for(int i=0;i<con;i++){
     printf("\n%d is consonants",consonants[i]);
   }
   printf("\n");
   for(int i=0;i<vow;i++){
     printf("\n%d is vowels",vowels[i]);
   }
  printf("\n%d\n%d",vow,con);
}
```
---
36. Removal of  all occurrences of a word in a string.

```c 
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char str2[100];
   scanf("%[^\n]",str2);
   char* token;
   char* tokens[100];
   int len = strlen(str);
   token = strtok(str," ");
   int i=0;
   while( token != NULL){
     tokens[i++]=token;
     token=strtok(NULL," ");
   }
   for(int j=0;j<i;j++){
     if(strstr(str2,tokens[j])==NULL){
        printf("%s ",tokens[j]);
     }
   }
}
```
---
37. Remove the extra white space in the starting and ending of the string.

```c 
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   int len = strlen(str);
   int start = 0;
   int end=len-1;
   while(str[end]==' '){
     end--;
   }
   while(str[start]==' '){
     start++;
   }
   printf("\n");
   for(int i=start;i<=end;i++){
     printf("%c",str[i]);
   }
}
```
---
38. Removes the extra space b/w 2 words in a string, like if i/p 
    hey(3 space)this  is pragal  o/p --> hey this is pragal

```c 
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   int len = strlen(str);
   for(int i=0;i<len;i++){
      if(str[i]==' '){
       if (i + 1 < len && str[i + 1] == ' ')
        continue;
      }
      printf("%c",str[i]);
   }
}
```
---
39. Reverse the words in the string

```c 
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char* token;
   char* tokens[100];
   int i=0;
   int len= strlen(str);
   token = strtok(str," ");
   while(token != NULL){
     tokens[i++]=token;
     token=strtok(str," ");
   }
   for(int j=i-1;j>=0;j--){
     printf("%s ",tokens[j]);
   }
}
```
---
40. Reverse the characters in the words of the string.

```c 
#include <stdio.h>
#include <string.h>
#include <stdbool.h>
#include <ctype.h>

int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int start =0;
  for(int i=0;i<=len;i++){
    if (str[i] == ' ' || str[i] == '\0'){
      for(int j=i-1;j>=start;j--){
        printf("%c",str[j]);
      }
      if(str[i]==' '){
        printf(" ");
      }
      start=i+1;
    }
  }
}
```
---
41. Print the first non-repeating character in the string

```c
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   int len = strlen(str);
   getchar();
   int freq[256]={0};
   for(int i=0;i<len;i++){
     char ch = tolower(str[i]);
     freq[(unsigned char)ch]++;
   }
   for(int i=0;i<256;i++){
     if(freq[i]==1){
       printf("%c",i);
       break;
     }
   }
}
```
---
42. Print the sum of numbers in the string and reverse the sum and print them.

```c
#include <stdio.h>
#include<string.h>
#include <ctype.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   int len = strlen(str);
   getchar();
   int sum=0;
   int rev=0;
   for(int i=0;i<len;i++){
     if(isdigit(str[i])){
       sum += str[i]-'0';
     }
   }
   printf("%d\n",sum);
   while(sum!=0){
     int rem = sum%10;
     rev = rev*10 + rem;
     sum/=10;
   }
   printf("%d",rev);
   
}
```
---

43. Printing the high frequency letters from string.

```c 
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int freq[256]={0};
  int max_freq=0;
  for(int i=0;i<len;i++){
    int ch = tolower(str[i]);
    freq[(unsigned char)ch]++;
    if(max_freq<freq[(unsigned char)ch]){
      max_freq=freq[(unsigned char)ch];
    }
  }
  for(int i=0;i<256;i++){
    if(max_freq==freq[i]){
      printf("%c ",i);
    }
  }
}
```
---
44. **a** 2nd maximum largest word in the string  

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(){
  char str[100];
  scanf("%[^\n]",str);
  char* token;
  char* tokens[100];
  int len = strlen(str);
  int i=0;
  token = strtok(str," ");
  while( token != NULL){
    tokens[i++] = token;
    token = strtok(NULL," ");
  }
  int max = strlen(tokens[0]);
  char* max_word = NULL;
  char* sec_max = NULL;
  int sec = strlen(tokens[0]);
  
  for(int j=0;j<i;j++){
    int count = strlen(tokens[j]);
    if(count>max){
      sec_max=max_word;
      sec=max;
      max_word=tokens[j];
      max=count;
      if(max>count && max>sec){
        sec_max=tokens[j];
      }
    }
  }
  printf("%s",sec_max); 
}

```
 **b** What is the 2nd smallest word in the given string?
```c
#include <stdio.h>
#include<string.h>
#include <ctype.h>
#include <limits.h>
int main()
{
   char str[100];
   scanf("%[^\n]",str);
   getchar();
   char* token;
   char* tokens[100];
   int len = strlen(str);
   token = strtok(str," ");
   int i=0;
   while(token != NULL){
     tokens[i++]= token;
     token = strtok(NULL," ");
   }
   int min=INT_MAX;
   int sec_min = INT_MAX;
   char* min_word = NULL;
   char* sec_min_word = NULL;
   
   for(int j=0;j<i;j++){
     int count = strlen(tokens[j]);
     if(count<min){
       sec_min = min;
       sec_min_word = min_word;
       min=count;
       min_word=tokens[j];
     }
     if(count>min && count<sec_min){
       sec_min_word=tokens[j];
       sec_min=count;
     }
   }
 printf("%s",sec_min_word);
}
```

---
45. A B C E F G F T N is input and 
    output is 
```
   A E F 
   B F T 
   C G N 
  ```

```c
#include<stdio.h>
int main(){
  char str[3][3];
  for(int i=0;i<3;i++){
    for(int j=0;j<3;j++){
      scanf(" %c",&str[i][j]);
    }
  }
  for(int col=0;col<3;col++){
    for(int row=0;row<3;row++){
      printf("%c ",str[row][col]);
    }
    printf("\n");
  }
}
```
---
46. To rotate the string and need to get the number of rotations from user.

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main() {
    char str[100];
    scanf("%[^\n]", str);
    getchar(); 
    int n;
    scanf("%d", &n); 
    int len = strlen(str);
    if( len==0 || n%len==0)
    {
      printf("%s",str);
      return 0;
    }
    n=n%len;
    char temp[100];
    strncpy(temp,str+n,len-n);
    strncpy(temp + (len-n),str,n);
    temp[len]='\0';
    printf("%s",temp);
}

```
---
47. Remove the first occurance of a word from the string.

```c
#include <stdio.h>
#include<string.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   char str2[100];
   getchar();
   int first = 0;
   scanf("%[^\n]",str2);
   char* token;
   char* tokens[100];
   int len = strlen(str);
   int i=0;
   token = strtok(str," ");
   while(token != NULL){
     tokens[i++]=token;
     token=strtok(NULL," ");
   }
   for(int j=0;j<i;j++){
     if(strcmp(str2,tokens[j])==0){
       if (first == 0) {
                first = j; 
            }
     }
   }
   for(int j=0;j<i;j++)
   if(j!=first)
   printf("%s ",tokens[j]);
}

```
48. Remove the first occurance of a word from the string .

```c
#include <stdio.h>
#include<string.h>

int main()
{
   char str[100];
   scanf("%[^\n]",str);
   char str2[100];
   getchar();
   int last = 0;
   scanf("%[^\n]",str2);
   char* token;
   char* tokens[100];
   int len = strlen(str);
   int i=0;
   token = strtok(str," ");
   while(token != NULL){
     tokens[i++]=token;
     token=strtok(NULL," ");
   }
   for(int j=0;j<i;j++){
     if(strcmp(str2,tokens[j])==0){
      last=j;
     }
   }
   for(int j=0;j<i;j++)
   if(j!=last)
   printf("%s ",tokens[j]);
}
```
---
49. Odd-indexed strings in reverse order

```c
#include <stdio.h>
#include <string.h>
void reverseString(char str[]) {
    int len = strlen(str);
    for (int i = len - 1; i >= 0; i--) {
        printf("%c", str[i]);
    }
}
int main() {
    int n;
    scanf("%d", &n);
    char strings[n][100];
    for (int i = 0; i < n; i++) {
        scanf("%s", strings[i]);
    }
    printf("Odd-indexed strings in reverse order:\n");
    for (int i = 0; i < n; i++) {
        if ((i + 1) % 2 != 0) { 
            reverseString(strings[i]);
            printf("\n");
        }
    }
    return 0;
}
```
---
50. Input from the user for an array of words and calculates the second-largest string length.

```c
#include <stdio.h>
#include <string.h>

int main() {
    int n;
    scanf("%d", &n);
    char words[n][100]; 
    int lengths[n]; 
    int i, max = 0, second_max = 0;
    for (i = 0; i < n; i++) {
        scanf("%s", words[i]); 
        lengths[i] = strlen(words[i]); 
    }
    for (i = 0; i < n; i++) {
        if (lengths[i] > max) {
            second_max = max;
            max = lengths[i];
        } 
        else if (lengths[i] > second_max && lengths[i] != max) {
            second_max = lengths[i];
        }
    }
    if (second_max == 0) {
        printf("0");
    } else {
        printf("The second largest string length is: %d\n", second_max);
    }
    return 0;
}
```
---
51. Print the largest palindrome found in the substring.

```c
#include <stdio.h>
#include <string.h>

void longestPalSubstr(const char* s, char* result) {
    int n = strlen(s), start = 0, maxLen = 1;
    for (int i = 0; i < n; i++) {
        for (int j = i; j < n; j++) {
            int len = j - i + 1, k;
            for (k = 0; k < len / 2; k++) 
                if (s[i + k] != s[j - k]) break;
            if (k == len / 2 && len > maxLen) {
                start = i;
                maxLen = len;
            }
        }
    }
    strncpy(result, s + start, maxLen);
    result[maxLen] = '\0';
}
int main() {
    char s[100]; 
    char result[100]; 
    scanf("%[^\n]", s); 
    longestPalSubstr(s, result);
    printf("The longest palindromic substring is: %s\n", result);
    return 0;
}
```
---
52. To get the input in array form and then find the maximum length and print.

```c
#include <stdio.h>
#include <string.h>

int main() {
    int n;
    scanf("%d", &n);

    char strings[n][100]; 
    int maxLength = 0;
    int index = 0;
    for (int i = 0; i < n; i++) {
        scanf("%s", strings[i]); 
        int length = strlen(strings[i]);
        if (length > maxLength) {
            maxLength = length;
            index = i;
        }
    }
    printf("The longest string is: %s\n", strings[index]);
    printf("Its length is: %d\n", maxLength);
    return 0;
}
```
---
53. Rotate the 2-D matrix into 90 degree.

```c
#include <stdio.h>
void rotateMatrix(int n, int matrix[n][n]) {
    int rotated[n][n];
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            rotated[j][n - 1 - i] = matrix[i][j];
        }
    }
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            matrix[i][j] = rotated[i][j];
        }
    }
}
int main() {
    int n;
    scanf("%d", &n);
    int matrix[n][n];
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    rotateMatrix(n, matrix);
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
---
55.  Calculates and prints the average of an array.
```c
#include <stdio.h>

int main() {
    int n;
    float sum = 0.0, average;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];  
    }
    average = sum / n;
    printf("The average is: %.2f\n", average);

    return 0;
}
```
---
56. To find the longest common prefix (LCP) of a list of strings in C, you can compare characters across all strings one by one until you find a mismatch.

```c
#include <stdio.h>
#include <string.h>

char* longestCommonPrefix(char strs[][100], int n) {
    if (n == 0) return "";  
    static char prefix[100];
    int i = 0;
    
    for (int j = 0; strs[0][j] != '\0'; j++) {
         for (i = 1; i < n; i++) {
            if (strs[i][j] != strs[0][j]) {
                prefix[j] = '\0';
                return prefix;
            }
        }
        prefix[j] = strs[0][j];
    }
    prefix[i] = '\0';
    return prefix;
}
int main() {
    int n;
    scanf("%d", &n);
    char strs[n][100];  
    for (int i = 0; i < n; i++) {
        scanf("%s", strs[i]);
    }
    char* result = longestCommonPrefix(strs, n);
    printf("Longest Common Prefix: %s\n", result);
    return 0;
}
```
i/p -> 
```
4
flower
flow
flight
flame
```
o/p ->
```
Longest Common Prefix: fl
```
---
57. Check if the given is Pangram or not.(Means the charecter from a-z must be used atleast once in the given string).

```c
#include <string.h>
#include<stdio.h>
#include<ctype.h>

int main(){
  char str[100];
  scanf("%[^\n]",str);
  int freq[26]={0};
  for(int i=0;str[i]!='\0';i++){
    str[i]=tolower(str[i]);
    freq[str[i]-'a']++;
  }
  for(int i=0;i<26;i++){
    if(freq[i]==0)
    {
      printf("Not pangram");
      return 0;
    }
  }
  printf("It's Pangram");
}
```
---
58. Remove leading zeros and check if the strings are equal,lesser or greater.

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s1[100];
    fgets(s1, 100, stdin);
    s1[strcspn(s1, "\n")] = '\0';

    char s2[100];
    fgets(s2, 100, stdin);
    s2[strcspn(s2, "\n")] = '\0'; 
    int i = 0, j = 0, n1 = strlen(s1), n2 = strlen(s2);
    printf("%s and %s are ", s1, s2);
    while (s1[i] != '\0') {
        i++;
    }
    if (i > 0) {
        strcpy(s1, &s1[1]);
    }
    while (s2[j] != '\0') {
        j++;
    }
    if (j > 0) {
        strcpy(s2, &s2[1]);
    }
    int res = strcmp(s1, s2);
    if (res == 0)
        printf("equal");
    else if (res > 0)
        printf("greater");
    else if (res < 0)
        printf("lesser");

    return 0;
}
```
---
59. Left rotation in the string.

```c
#include <stdio.h>
#include <string.h>
void leftRotateString(char *str, int n) {
    int len = strlen(str);
    if (n <= 0 || len == 0) {
        return; 
    }
    n = n % len; 
    char temp[n];
    for (int i = 0; i < n; i++) {
        temp[i] = str[i];
    }for (int i = n; i < len; i++) {
        str[i - n] = str[i];
    }
    for (int i = 0; i < n; i++) {
        str[len - n + i] = temp[i];
    }
}
int main() {
    char str[100];
    int n;
    scanf("%s", str);
   scanf("%d", &n);
    leftRotateString(str, n);
    printf("String after %d left rotations: %s\n", n, str);
    return 0;
}
```
---
60. Right rotation in the string.
    
```c
#include <stdio.h>
#include <string.h>

void rightRotateString(char *str, int n) {
    int len = strlen(str);
    if (n <= 0 || len == 0) {
        return; 
    }
    n = n % len; 
    char temp[n];
    for (int i = 0; i < n; i++) {
        temp[i] = str[len - n + i];
    }
    for (int i = len - 1; i >= n; i--) {
        str[i] = str[i - n];
    }
    for (int i = 0; i < n; i++) {
        str[i] = temp[i];
    }
}
int main() {
    char str[100];
    int n;
    scanf("%s", str);
    scanf("%d", &n);
    rightRotateString(str, n);
    printf("Right rotations: %s\n", str);
    return 0;
}
```
---
61. Check if the time is valid time or not.
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int isValidTime(const char *time) {
     if (strlen(time) != 5) {
        return 0;
    }
         if (!isdigit(time[0]) || !isdigit(time[1]) || time[2] != ':' ||
        !isdigit(time[3]) || !isdigit(time[4])) {
        return 0;
    }
    int hours = (time[0] - '0') * 10 + (time[1] - '0');
    int minutes = (time[3] - '0') * 10 + (time[4] - '0');
    if (hours < 0 || hours > 23 || minutes < 0 || minutes > 59) {
        return 0;
    }
    return 1;
}
int main() {
    char time[10];
    printf("Enter a time in HH:MM format: ");
    scanf("%s", time);
    if (isValidTime(time)) {
        printf("The time \"%s\" is valid.\n", time);
    } else {
        printf("The time \"%s\" is not valid.\n", time);
    }
    return 0;
}
```
---
62. 
