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
 
```