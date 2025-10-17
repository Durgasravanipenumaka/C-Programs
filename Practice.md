## Write a C program to perform k left rotations on an array.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5};
        int k;
        int len=sizeof(arr)/sizeof(arr[0]);
        printf("Enter the number of rotations:");
        scanf("%d",&k);
        for(int i=0;i<k;i++){
                int temp=arr[0];
                for(int j=0;j<len-1;j++){
                        arr[j]=arr[j+1];
                }
                arr[len-1]=temp;
        }
        for(int i=0;i<len;i++){
                printf("%d ",arr[i]);
        }
}
```
## Write a C program to perform k Right rotations on an array.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5};
        int k;
        int len=sizeof(arr)/sizeof(arr[0]);
        printf("Enter the number of rotation:");
        scanf("%d",&k);
        for(int i=0;i<k;i++){
                int temp=arr[len-1];
                for(int j=len-1;j>0;j--){
                        arr[j]=arr[j-1];
                }
                arr[0]=temp;
        }
        for(int i=0;i<len;i++){
                printf("%d ",arr[i]);
        }
        printf("\n");
}
```
## avoid race condition using spinlock.
```c
#include<stdio.h>
#include<pthread.h>
pthread_spinlock_t lock;
int count=0;
void *increment(void *arg){
        int tid=*(int *)arg;
        printf("Thread %d waiting for spin lock..\n",tid);
        pthread_spin_lock(&lock);
        for(int i=0;i<5;i++){
                count++;
        }
        printf("Thread %d updated count value:%d\n",tid,count);
        pthread_spin_unlock(&lock);
        return NULL;
}
int main(){
        int n;
        printf("Enter the n value:");
        scanf("%d",&n);
        pthread_t th[n];
        int threadid[n];
        pthread_spin_init(&lock,PTHREAD_PROCESS_PRIVATE);
        for(int i=1;i<=n;i++){
                threadid[i]=i;
                pthread_create(&th[i],NULL,increment,&threadid[i]);
        }
        for(int i=1;i<=n;i++){
                pthread_join(th[i],NULL);
        }
        pthread_spin_destroy(&lock);
        printf("Final count value:%d\n",count);
}
```
## Rotate matrix 90 degree clockwise.
```c

```
## POINTERS :

## Write a program to print the address of a variable using a pointer.
```c
#include<stdio.h>
int main(){
    int a=10;
    printf("Address of %d is %p",a,&a);
}
```

## Declare an integer variable and a pointer to it. Print the value using both the variable and the pointer.
```c
#include<stdio.h>
int main(){
   int a=10;
   int *ptr=&a;
   printf("Value = %d\nAddress = %p",*ptr,ptr);
}
```

## Demonstrate incrementing and decrementing a pointer.
```c
#include<stdio.h>
int main(){
    int arr[]={10,20,30};
    int *ptr=arr;
    printf("Pointer initially points to value : %d\n",*ptr);
    ptr++;
    printf("After increment, pointer points to value : %d\n",*ptr);
    ptr++;
    printf("After another increment, pointer points to value: %d\n",*ptr);
    ptr--;
    printf("After decrement, pointer points to value : %d\n",*ptr);
}
```

## Write a program to swap two integers using pointers (without using a third variable directly in main).
```c
#include<stdio.h>
void swap(int *a,int *b){
    *a = *a + *b;
    *b = *a - *b;
    *a = *a - *b;
    
}
int main(){
    int a,b;
    printf("Enter first number :");
    scanf("%d",&a);
    printf("Enter the second number :");
    scanf("%d",&b);
    printf("Numbers before swapping : %d %d\n",a,b);
    swap(&a,&b);
    printf("Numbers after swapping : %d %d\n",a,b);
}
```

## Write a program to access and print all elements of an array using a pointer (without using array indexing).
```c
#include<stdio.h>
int main(){
    int n;
    printf("Enter the size:");
    scanf("%d",&n);
    int arr[n];
    printf("Enter the elements in the array:");
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    printf("Elements in the array are :");
    for(int i=0;i<n;i++){
        printf("%d ",*(arr+i));
    }
}
```

## Write a program to calculate the sum of all elements in an array using pointers (do not use array indexing).
```c
#include<stdio.h>
int main(){
    int n;
    int sum=0;
    printf("Enter the size:");
    scanf("%d",&n);
    int arr[n];
    printf("Enter the elements in the array:");
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    printf("Elements in the array are :");
    for(int i=0;i<n;i++){
        sum += *(arr+i);
    }
    printf("Sum of the array elements:%d\n",sum);
}
```

## Print a string using a character pointer.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[]="HelloWorld";
    char *ptr=str;
    int len=strlen(str);
    for(int i=0;i<len;i++){
        printf("%c",*(ptr+i));
    }
}
```

## Double a Number Using Pointer in Function.
```c
#include<stdio.h>
void doubleval(int *n){
    *n = 2 * (*n);
}
int main(){
    int n;
    printf("Enter the number:");
    scanf("%d",&n);
    printf("Value before doubling:%d\n",n);
    doubleval(&n);
    printf("Value after doubling:%d\n",n);
    
}
```

## Pointer to Pointer.
```c
#include<stdio.h>
int main(){
    int n;
    printf("Enter the number:");
    scanf("%d",&n);
    int *ptr=&n;
    int **pptr=&ptr;
    printf("Value of number:%d\n",n);
    printf("Address of number:%d\n",(void*)ptr);
    printf("Value using pointer to pointer:%d\n",**pptr);
}
```

## Write a program to dynamically allocate memory for an integer array, take input, and print the sum of all elements using pointers. Use malloc().
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
    int n;
    int sum=0;
    printf("Enter the size :");
    scanf("%d",&n);
    int *arr=(int *)malloc(n*sizeof(int));
    printf("Enter elements in the array:");
    for(int i=0;i<n;i++){
        scanf("%d",(arr+i));
    }
    for(int i=0;i<n;i++){
        sum += *(arr+i);
    }
    printf("Sum of the array:%d\n",sum);
}
 ```
