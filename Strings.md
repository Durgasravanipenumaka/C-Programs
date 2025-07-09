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
## 3. Write a program in C to separate individual characters from a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char s1[100];
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        printf("Input string:%s\n",s1);
        printf("Individual characters in the string are:\n");
        for(int i=0;s1[i]!='\0';i++){
                printf("%c\n",s1[i]);
        }
}
```
## 4. Write a program in C to print individual characters of a string in reverse order.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char name[30];
        int len,temp;
        fgets(name,sizeof(name),stdin);
        if(name[strlen(name)-1]=='\n')
                name[strlen(name)-1]='\0';
        printf("string before reversing :%s\n",name);
        len=strlen(name);
        printf("string after reversing:\n");
        for(int i=len-1;i>=0;i--){
                printf("%c\n",name[i]);
        }
}
```
## 5. Write a program in C to count the total number of words in a string.
```c
#include<stdio.h>
int main(){
        char s1[100];
        int count=0;
        fgets(s1,sizeof(s1),stdin);
        printf("string : %s",s1);
        for(int i=0 ;s1[i]!='\0';i++){
                if((i==0 && s1[i]!=' ' && s1[i]!='\n' && s1[i]!='\t')||(s1[i]!=' ' && s1[i]!='\n' && s1[i]!='\t' && (s1[i-1]==' '||s1[i-1]=='\n' ||s1[i-1]=='\t')))
                        count++;
        }
        printf("\nNo of words in a string:%d",count);
}
```
## 6. Write a program in C to compare two strings without using string library functions.



