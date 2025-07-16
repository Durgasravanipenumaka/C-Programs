
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
