## Arrays :

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
## Second highest prime number in a 2D matrix :
```c
#include<stdio.h>
void input(int (*ptr)[3],int r,int c){
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&ptr[i][j]);
        }
    }
}
void display(int (*ptr)[3],int r,int c){
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            printf("%d ",ptr[i][j]);
        }
        printf("\n");
    }
}
int secondhighestprime(int (*ptr)[3],int r,int c){
    int max,smax,found=1;
    max=smax=-1;
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){ 
            if(ptr[i][j] < 0){
                continue;
            }
            found=1;
            for(int k=2;k*k <= ptr[i][j];k++){
                if((ptr[i][j] % k)==0){
                    found=0;
                    break;
                }
            }
            if(found){
                if(ptr[i][j]>max){
                smax=max;
                max=ptr[i][j];
               }
               else if(ptr[i][j] > smax && ptr[i][j] != max){
                    smax=ptr[i][j];
               }
            }
        }
    }
    return smax;
}
int main(){
    int n;
    int arr[3][3];
    input(arr,3,3);
    display(arr,3,3);
    n=secondhighestprime(arr,3,3);
    if(n==-1){
        printf("Not enough prime numbers");
    }
    else{
        printf("Second highest prime  number = %d\n",n);
    }
}
```
## Loops :

## Write a program to print the sum of smallest and largest prime in the given range ?
```c
#include<stdio.h>
#include<limits.h>
int isprime(int n){
    if(n<2){
        return 0;
    }
    for(int i=2;i*i <= n;i++){
        if(n%i==0){
            return 0;
        }
    }
    return 1;
}
int main(){
    int min=INT_MAX,max=INT_MIN;
    for(int i=4;i<20;i++){
        if(isprime(i)){
            if(min > i){
                min=i;
            }
            if(max < i){
                max=i;
            }
        }
    }
    printf("Smallest prime number :%d\n",min);
    printf("Largest prime number :%d\n",max);
    printf("Sum=%d\n",(max+min));
    
}
```
## Write a program to print the next number of the highest number which can be formed with the given number.
```c
#include<stdio.h>
#include<limits.h>
int main(){
    int arr[]={1,5,4,9};
    int sum=0;
    int min=INT_MAX;
    for(int i=0;i<4;i++){
        for(int j=0;j<4;j++){
            if(arr[i]>arr[j]){
                int temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
            }
        }
    }
    for(int i=0;i<4;i++){
        sum=sum*10+arr[i];
    }
    printf("Number=%d",sum+1);
}
```
## Bit Manupulation :

## Write a program to print the largest series of 1's in the given number ?
```c
#include<stdio.h>
#include<limits.h>
void binarybits(int n){
    int mask;
    for(int i=15;i>=0;i--){
        mask=1<<i;
        putchar(n&mask ? '1' : '0');
    }
    printf("\n");
}
int main(){
    int num;
    printf("Enter the number:");
    scanf("%d",&num);
    printf("Number in binary form:");
    binarybits(num);
    int count=0;
    int max=0;
    for(int i=15;i>=0;i--){
        if(num&(1<<i)){
            count++;
        }
        else{
            if(max < count){
                max=count;
            }
            count=0;
        }
    }
    if(max<count){
        max=count;
    }
    printf("Longest series of 1's in given number :");
    for(int i=0;i<max;i++){
        printf("1");
    }
}
```

## Strings :

## Write a program to hide first and last vowel in every word in the given string ?
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[100];
    char word[20],ch;
    int pos1,pos2, k=0;
    printf("Enter the string:");
    fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]='\0';
    for(int i=0;;i++){
        if(str[i]!=' ' && str[i]!='\0'){
            word[k++]=str[i];
        }
        else{
            word[k]='\0';
            pos1=-1;
            pos2=-1;
            for(int j=0;word[j]!='\0';j++){
                ch=tolower(word[j]);
                if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u'){
                    pos1=j;
                    break;
                }
            }
            for(int j=0;word[j]!='\0';j++){
                ch=tolower(word[j]);
                if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u'){
                    pos2=j;
                }
            }
            if(pos1!=-1){
                word[pos1]='*';
            }
            if(pos2!=-1 && pos2!=pos1){
                word[pos2]='*';
            }
            printf("%s ",word);
            k=0;
        }
        if(str[i]=='\0'){
            break;
        }
    }
}
```


## Rotate matrix 90 degree clockwise.
```c

```

## Threads :
## Avoid race condition using spinlock.
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

## Reverse an array using pointers.
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
    for(int i=0,j=n-1;i<j;i++,j--){
        int temp=*(arr+i);
        *(arr+i)=*(arr+j);
        *(arr+j)=temp;
    }
    printf("Array after reversing of array:");
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }
}
```

## Copy a string using pointers.
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
    int copiedarr[n];
    for(int i=0;i<n;i++){
        copiedarr[i]=*(arr+i);
        
    }
    printf("Array copied array:");
    for(int i=0;i<n;i++){
        printf("%d ",copiedarr[i]);
    }
}
```

## Find length of string using pointer traversal.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
    char str[]="Helloworld";
    char *ptr=str;
    int len=0;
    while(*ptr != '\0'){
        len++;
        ptr++;
    }
    printf("Length of the string:%d\n",len);
}
```

## Create a structure Student and use a pointer to access and print its members.
```c
#include<stdio.h>
#include<stdlib.h>
struct student{
    char name[10];
    int id;
    float marks;
};
int main(){
    struct student s;
    struct student *ptr=&s;
    printf("Enter Id:");
    scanf("%d",&ptr->id);
    printf("Enter Name:");
    scanf("%s",&ptr->name);
    printf("Enter Marks:");
    scanf("%f",&ptr->marks);
    printf("Student Details:");
    printf("ID:%d\n",ptr->id);
    printf("Name:%s\n",ptr->name);
    printf("Marks:%.2f\n",ptr->marks);
}
```

## Store multiple Student records using an array of structure pointers.
```c
#include<stdio.h>
#include<stdlib.h>
struct student{
    char name[10];
    int id;
    float marks;
};
int main(){
    struct student *ptr[3];
    for(int i=0;i<3;i++){
        ptr[i]=(struct student *)malloc(sizeof(struct student));
    }
    for(int i=0;i<3;i++){
        printf("Enter details for sttudent %d :\n",i+1);
        printf("Enter Id:"); 
        scanf("%d",&ptr[i]->id);
        printf("Enter Name:");
        scanf("%s",&ptr[i]->name);
        printf("Enter Marks:");
        scanf("%f",&ptr[i]->marks);
    }
    printf("Student details:\n");
    for(int i=0;i<3;i++){
        printf("ID:%d, ",ptr[i]->id);
        printf("Name:%s, ",ptr[i]->name);
        printf("Marks:%.2f\n",ptr[i]->marks);
    }
}
```

## Write a function that returns a pointer to the largest element in an array.
```c
lude<stdio.h>
int* largestelement(int a[],int s){
    int *max=&a[0];
    for(int i=0;i<s;i++){
        if(a[i]>*max){
            max=&a[i];
        }
    }
    return max;
}
int main(){
    int n;
    printf("Enter the size of the array:");
    scanf("%d",&n);
    int arr[n];
    printf("Enter the elements in the array:");
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    int *ele=largestelement(arr,n);
    printf("Largest element in the array:%d\n",*ele);
}
```

## Write a function that swaps two integers by accepting pointers to pointers as arguments.
```c
#include<stdio.h>
void swapping(int **a,int **b){
    int temp=**a;
    **a=**b;
    **b=temp;
}
int main(){
    int a,b;
    int *ptr1,*ptr2;
    printf("Enter a and b values:");
    scanf("%d %d",&a,&b);
    ptr1=&a;
    ptr2=&b;
    printf("Numbers before swapping:%d %d\n",a,b);
    swapping(&ptr1,&ptr2);
    printf("Numbers after swapping:%d %d\n",a,b);
    
}
```

## Demonstrate a pointer to a function that adds two numbers.
```c
#include<stdio.h>
void add(int a,int b){
    int sum=0;
    sum=a+b;
    printf("Sum=%d\n",sum);
}
int main(){
    int a,b;
    printf("Enter a value:");
    scanf("%d",&a);
    printf("Enter b value:");
    scanf("%d",&b);
    void (*ptr)(int,int)=add;
    ptr(a,b);
}
```

## Demonstrate how a void pointer can store the address of different data types.
```c
#include<stdio.h>
int main(){
    int a=10;
    char ch='c';
    float b=10.02;
    void *ptr=&a;
    printf("Integer Value: %d\n",*(int *)ptr);
    ptr=&ch;
    printf("Character value:%c\n",*(char *)ptr);
    ptr=&b;
    printf("Float value:%.2f\n",*(float *)ptr);
}
```

## Access elements of a 2D array using pointer arithmetic.
```c
#include<stdio.h>
int main(){
    int arr[3][3]={{1,2,3},{4,5,6},{7,8,9}};
    printf("Elements in 2D array using pointer arithmetic:\n");
    for(int i=0;i<3;i++){
        for(int j=0;j<3;j++){
            printf("%d ",*(*(arr+i)+j));
        }
        printf("\n");
    }
}
```

## Write a program that causes and fixes a dangling pointer issue.
```c
