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
#include <string.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  getchar();
  int target;
  int hour = atoi(strtok(str,":"));
  int min = atoi(strtok(NULL,":"));
  int sec = atoi(strtok(NULL,":"));
  if(hour<0 || hour>23 || min<0||min>59||sec<0||sec>59)
  printf("Invalid time format");
  char period[3];
  int disp_hr = hour%12;
  if(disp_hr==0){
    disp_hr=12;
  }
  if(hour<12){
    strcpy(period,"AM");
  }
  else
  {
    strcpy(period,"PM");
  }
  printf("Hour:%d min:%d sec:%d %s",disp_hr,min,sec,period);
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
         printf("%c ",i);
    }
  }
}
}
```
---
8. The smallest word in the whole string 

```c
#include <stdio.h>
#include <string.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  char* token;
  char* tokens[100];
  int i = 0;
  int count = 0;
  token = strtok(str," ");
  while(token != NULL){
    tokens[i++] = token;
    token = strtok(NULL," ");
  }
  char* min_word = tokens[0];
  int min = strlen(tokens[0]);
  
  for(int j=0;j<i;j++){
    if(strlen(tokens[j]) < min_word){
      min_word= tokens[j];
    }
  }
  printf("%s",min_word);
}
```
---
9. To count the largest word in a string.

```c
#include <stdio.h>
#include <string.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  char* token;
  char* tokens[100];
  int i = 0;
  int count = 0;
  token = strtok(str," ");
  while(token != NULL){
    tokens[i++] = token;
    token = strtok(NULL," ");
  }
  char* max_word = tokens[0];
  int max = strlen(tokens[0]);
  
  for(int j=0;j<i;j++){
    if(strlen(tokens[j]) > max_word){
      max_word= tokens[j];
    }
  }
  printf("%s",max_word);
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
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int len = strlen(str);
  int freq[256]={0};
  for(int i=0;str[i]!='\0';i++){
    freq[(unsigned char)str[i]]++;
  }
  
  for(int i=0;i<256;i++){
    if(freq[i]!=0)
    printf("%c , %d\n",i,freq[i]);
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
18. To print the firat non repeating character in the string

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
19. Remove the duplicate characters and peint he rest of the charecters

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
#include <string.h>
#include<stdio.h>
#include<ctype.h>
int main(){
  char str1[100];
  scanf("%[^\n]",str1);
  getchar();
  char str2[100];
  scanf("%[^\n]",str2);
  int len1 = strlen(str1);
  int len2 = strlen(str2);
  int freq1[256]={0};
  int freq2[256]={0};
  for(int i=0;str1[i]!='\0';i++){
    str1[i] = tolower(str1[i]);
    freq1[str1[i]-'a']++;
  }
  for(int i=0;str2[i]!='\0';i++){
    str2[i] = tolower(str2[i]);
    freq2[str2[i]-'a']++;
  }
  int anagram=1;
  for(int i=0;i<26;i++){
    if(freq1[i]!=freq2[i]){
      anagram=0;
      break;
    }
  }
  if(anagram)
  printf("Anagram");
  else
  printf("Not anagram");
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
23. 