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
