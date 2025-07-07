## 1. Write a program in C to input a string and print it.
```c
#include<stdio.h>
int main(){
      char str[100];
      fgets(str,sizeof(str),stdin);
      printf("%s",str);
}
```
## 2. Write a program in C to find the length of a string without using library functions.
```c
#include<stdio.h>
int main(){
        char s1[30];
        scanf("%s",s1);
        printf("string=%d",s1);
        int i=0;
        while(i!='\0'){
                count++;
                i++;
        }
        printf("length of the string:%d",count);
}
```
