#### Questions related to the frequencies

1. To display the frequency of letters in a string.

```c
#include <stdio.h>
#include <ctype.h>
int main(){
  char str[100];
  scanf("%[^\n]",str);
  int freq[26] = {0};
  for(int i=0;str[i]!='\0';i++){
    char ch = tolower(str[i]);
    if(ch>='a' && ch<='z'){
      freq[ch-'a']++;
    }
  }
  for(int i=0;i<26;i++){
    if(freq[i]>0){
      printf("%c: %d\n",i +'a',freq[i]);
    }
  }
}

```
---
2. To find the  Anagram in strings.

```c

```
