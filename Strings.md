## 1. Write a program in C to input a string and print it.
```c
#include<stdio.h>
int main(){
      char str[100];
      fgets(str,sizeof(str),stdin);
      printf("%s",str);
}
```
