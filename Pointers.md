## 1.Write a Program to print the address of variables using the address operator.
```c
#include<stdio.h>
int main(){
        int a=10;
        printf("%x",&a);
}
```
## 2. Write a program to print size of pointer variables.
```c
#include<stdio.h>
int main(){
        int *ptr;
        printf("Size of int pointer:%zu",sizeof(ptr));
}
```
## 3. Write a program to print size of pointer variables and size of values Dereferenced by them.
```c
#include<stdio.h>
int main(){
        int a=10;
        int *p=&a;
        printf("size of pointer variables:%zu\n",sizeof(p));
        printf("size of values:%zu",sizeof(*p));
}
```
## 4. Write a program to illustrate the dereferencing of pointers.
```c
#include<stdio.h>
int main(){
        int a=10;
        int *p=&a;
        printf("value of a :%d\n",a);
        printf("address of value:%p\n",(void*)&a);
        printf("address of stored in pointer:%p\n",(void*)p);
        printf("value pointed to pointer:%d",*p);
}
```
## 5. C program to illustrate pointer arithmetic.
```c

## 25. Implement a function to copy one string into another using pointers, without using any standard library functions.
```c
#include<stdio.h>
#include<string.h>
int copystr(char *str1,char *str2){
        while(*str1!='\0'){
                *str2=*str1;
                str1++;
                str2++;
        }
        *str2='\0';
}
int main(){
        char str1[]="Linux";
        int len=strlen(str1);
        char str2[len];
        copystr(str1,str2);
        printf("%s",str2);
}
```
##  Write a program to print array of pointer.
```c
#include<stdio.h>
int main(){
        int a=1,b=2,c=3,d=4,e=5;
        int *arr[5];
        arr[0]=&a;
        arr[1]=&b;
        arr[2]=&c;
        arr[3]=&d;
        arr[4]=&e;
        for(int i=0;i<5;i++){
                printf("%d ",*arr[i]);
        }
}
```
## Write a program to print pointer to an array.
```c
#include<stdio.h>
int main(){
        int arr[5];
        int (*ptr)[5]=&arr;
        printf("Enter the elements in an array:");
        for(int i=0;i<5;i++){
                scanf("%d",&(*ptr)[i]);
        }
        printf("Elements in the array are:");
        for(int i=0;i<5;i++){
                printf("%d ",(*ptr)[i]);
        }
}
```
