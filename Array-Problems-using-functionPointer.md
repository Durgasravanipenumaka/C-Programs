## 1. Write a program in C to store elements in an array and print them.
```c
#include<stdio.h>
#define n 5
void elements(int array[]){
        for(int i=0;i<n;i++){
                printf("%d ",array[i]);
        }
        printf("\n");
}
int main(){
        int arr[n];
        void (*ptr)(int [])=&elements;
        printf("Enter the elements:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Elements in an array: ");
        ptr(arr);
}
```
## 2. Write a program in C to read n number of values in an array and display them in reverse order.
```c
#include<stdio.h>
#define n 5
void reverse(int array[]){
        for(int i=n-1;i>=0;i--){
                printf("%d ",array[i]);
        }
        printf("\n");
}
int main(){
        int arr[n];
        void (*ptr)(int [])=&reverse;
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Reversed Array:");
        ptr(arr);
}
```
