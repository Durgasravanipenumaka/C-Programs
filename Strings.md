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
## 6. Remove the newline character added by fgets() using strcspn().
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        printf("%s",str);
}
```
## 7.Write a C Program to check if a two strings are Anagram or not.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void sort(char str[]){
        for(int i=0;str[i]!='\0';i++){
                for(int j=i+1;str[j]!='\0';j++){
                        if(str[i]>str[j]){
                        char temp=str[i];
                        str[i]=str[j];
                        str[j]=temp;
                }
                }
        }
}
int main(){
        char str1[100],str2[100];
        int count=0;
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';

        if(strlen(str1)!=strlen(str2)){
                printf("string is not a anagram");
                return 0;
        }
        for(int i=0;str1[i]!='\0';i++){
                str1[i]=tolower(str1[i]);
        }
        for(int i=0;str2[i]!='\0';i++){
                str2[i]=tolower(str2[i]);
        }
        sort(str1);
        sort(str2);
        if(strcmp(str1,str2)==0)
                printf("String is a anagram");
        else
                printf("string is not a anagram");

}
```




