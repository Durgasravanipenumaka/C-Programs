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

## Rotate the matrix in 90 degree clockwise,90 degrees anti clockwise and 180 degrees.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c];
        int cmat[c][r];
        int amat[c][r];
        int mat[r][c];
        printf("Enter the elements in the matrix:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        cmat[i][j]=arr[r-j-1][i];
                }
        }
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        amat[i][j]=arr[j][c-i-1];
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        mat[i][j]=arr[r-i-1][c-j-1];
                }
        }
        printf("Matrix after 90 degree clockwise rotation :\n");
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        printf("%d ",cmat[i][j]);
                }
                printf("\n");
        }
        printf("\nMatrix after 90 degree anticlockwise rotation :\n");
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        printf("%d ",amat[i][j]);
                }
                printf("\n");
        }
        printf("\nMatrix after 180 degree rotation :\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        printf("%d ",mat[i][j]);
                }
                printf("\n");
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
#include<stdio.h>
#include<stdlib.h>
int main(){
    int *ptr=(int *)malloc(sizeof(int));
    if(ptr==NULL){
        printf("malloc error");
        exit(1);
    }
    *ptr=42;
    printf("Number=%d\n",*ptr);
    free(ptr);
    printf("Accessing pointer after become dangling pointer %p\n",(void *)ptr);
    ptr=NULL;
    if(ptr==NULL){
        printf("Pointer is now NULL(safe to use)\n");
    }
}
```
## Linked List :

## Insert a node:
- At the beginning
- At the end
- At a given position
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void addnodeatbeginning(int b){
        struct node *pnew,*ptemp;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=b;
        pnew->nxt=NULL;
        ptemp=phead;
        phead=pnew;
        phead->nxt=ptemp;
}
void addnodeatparpos(int pos,int size,int a){
        struct node *pnew,*ptemp,*ptrav=phead;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                exit(1);
        }
        pnew->val=a;
        pnew->nxt=NULL;
        if(pos<0 || pos>size){
                printf("Position is in out off range\n");
                free(pnew);
                return;
        }
        if(pos==0){
                pnew->nxt=phead;
                phead=pnew;
                return;
        }
        for(int i=0;i<pos-1 && ptrav!=NULL;i++){
                ptrav=ptrav->nxt;
        }
        if(ptrav==NULL){
                printf("Invalid position\n");
                free(pnew);
                return;
        }
        ptemp=ptrav->nxt;
        ptrav->nxt=pnew;
        pnew->nxt=ptemp;
}
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                exit(1);
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
int countlinkedlist(){
        struct node *ptrav=phead;
        int count=0;
        while(ptrav!=NULL){
                count++;
                ptrav=ptrav->nxt;
        }
        return count;
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL\n");
}
int main(){
        int n,node,ele;
        int pos,num,count;
        printf("Enter total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the value at node %d : ",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        count=countlinkedlist();
        printf("Enter the number to add at begginning:");
        scanf("%d",&ele);
        addnodeatbeginning(ele);
        printf("Enter the position to where it insert:");
        scanf("%d",&pos);
        printf("Enter the number to insert:");
        scanf("%d",&num);
        addnodeatparpos(pos,count,num);
        printf("Nodes in the Linked list : ");
        display();
}
```
## Delete a node:
- From the beginning
- From the end
- From a given position
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                exit(1);
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt != NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL\n");
}
void deletenodeatbeginning(){
        struct node *ptemp;
        ptemp=phead;
        phead=phead->nxt;
        free(ptemp);
}
void deletenodeatend(){
        struct node *prev,*ptrav=phead;
        while(ptrav->nxt!=NULL){
                prev=ptrav;
                ptrav=ptrav->nxt;
        }
        prev->nxt=NULL;
        free(ptrav);
}
int countnodes(){
        struct node *ptrav=phead;
        int count=0;
        while(ptrav!=NULL){
                count++;
                ptrav=ptrav->nxt;
        }
        return count;
}
void deletenodeatparpos(int pos,int size){
        struct node *prev,*ptemp,*ptrav=phead;

        if(pos<0 || pos >size){
                printf("Invalid position");
                return;
        }
        for(int i=0;i<pos-1;i++){
                prev=ptrav;
                ptrav=ptrav->nxt;
        }
        ptemp=prev->nxt;
        prev->nxt=ptemp->nxt;
        free(ptemp);
}

int main(){
        int total,node;
        int count,pos;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the node at %d : ",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        deletenodeatbeginning();
        display();
        deletenodeatend();
        display();
        count=countnodes();
        printf("Enter the position to delete:");
        scanf("%d",&pos);
        deletenodeatparpos(pos,count);
        display();
}
```
## create a linked list , display it,print middle node,reverse the linked list and again display it.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
struct node display(struct node *phead){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                exit(1);
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void findmiddlenode(){
        struct node *fast,*slow;
        fast=slow=phead;
        while(fast!=NULL && fast->nxt!=NULL){
                slow=slow->nxt;
                fast=fast->nxt->nxt;
        }
        printf("\nMiddle node = %d\n",slow->val);
}
struct node* reverse(){
        struct node *currentnode,*nxtnode,*prevnode=NULL;
        currentnode=phead;
        nxtnode=NULL;
        while(currentnode != NULL){
                nxtnode=currentnode->nxt;
                currentnode->nxt=prevnode;
                prevnode=currentnode;
                currentnode=nxtnode;
        }
        return prevnode;

}
int main(){
        int total,node;
        struct node *Address;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the value at node %d : ",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        printf("Elements in the linked list:");
        display(phead);
        findmiddlenode();
        Address=reverse();
        display(Address);
}
```

## create linked list ,create loop ,detect the loop and delete the loop.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
void loopcreation(int pos,int size){
        struct node *prev,*ptrav=phead;
        if(pos>size || pos<0){
                printf("Position is in out of bound");
                return;
        }
        for(int i=1;i<pos;i++){
                prev=ptrav;
                ptrav=ptrav->nxt;
        }
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=prev->nxt;
}
void checkingloop(){
        struct node *slow,*fast;
        slow=fast=phead;
        while(fast != NULL && fast->nxt != NULL){
                slow=slow->nxt;
                fast=fast->nxt->nxt;
                if(slow==fast){
                printf("Loop is detected\n");
                return;
                }
        }
        printf("Loop is not detected\n");
}
void deletionloop(){
           struct node *slow,*fast,*ptrav;
           slow=fast=phead;
           while(fast != NULL && fast->nxt != NULL){
                   slow=slow->nxt;
                   fast=fast->nxt->nxt;
                   if(slow==fast){
                           break;
                   }
           }
           if(slow==fast){
                   if(slow==phead){
                           while(slow->nxt != fast){
                                   slow=slow->nxt;
                           }
                           slow->nxt=NULL;
                   }
                   else{
                           slow=phead;
                           while(slow->nxt != fast){
                                   slow=slow->nxt;
                           }
                           slow->nxt=NULL;
                   }
           }
           else{
                   printf("Loop is not detected\n");
           }
}

int main(){
        int total,n,pos;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the node %d : ",i+1);
                scanf("%d",&n);
                createnode(n);
        }
        printf("Nodes in the linked list are : ");
        display();
        printf("\nEnter the position for creating loop:");
        scanf("%d",&pos);
        loopcreation(pos,total);
        checkingloop();
        deletionloop();
        checkingloop();
}
```

## create linked list,sorting the linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void display(struct node *phead){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL\n");
}
struct node* sorting(){
        if(!phead || !phead->nxt){
                return phead;
        }
        struct node *i,*j;
        for(i=phead;i->nxt != NULL;i=i->nxt){
                for(j=i->nxt;j != NULL;j=j->nxt){
                        if(i->val > j->val){
                                i->val = i->val + j->val;
                                j->val = i->val - j->val;
                                i->val = i->val - j->val;
                        }
                }
        }
        return phead;
}
int main(){
        int total,node;
        struct node *add;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the node at %d :",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        printf("Nodes in the linked list :");
        display(phead);
        add=sorting();
        printf("Nodes after sorting:");
        display(add);
}
```

## check if a linked list is palindrome or not.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL\n");
}
void palindromeornot(){
        struct node *ptrav=phead;
        int arr[100];
        int k=0;
        while(ptrav != NULL){
                arr[k++]=ptrav->val;
                ptrav=ptrav->nxt;
        }
        for(int i=0,j=k-1;i<j;i++,j--){
                if(arr[i]!=arr[j]){
                        printf("It is not a palindrome\n");
                        return;
                }
        }
        printf("It is a palindrome\n");
}

int main(){
        int total,node;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the node at %d :",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        printf("Nodes in the linked list :");
        display();
        palindromeornot();

}
```

## Chaeck if the linked list is palindrome or not without using array.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt != NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
struct node* reverse(struct node *phead){
        struct node *currentnode,*nextnode,*prevnode;
        nextnode=prevnode=NULL;
        currentnode=phead;
        while(currentnode!=NULL){
                nextnode=currentnode->nxt;
                currentnode->nxt=prevnode;
                prevnode=currentnode;
                currentnode=nextnode;
        }
        return prevnode;
}
int isplaindrome(){
        if(phead==NULL || phead->nxt==NULL){
                return 1;
        }
        struct node *slow,*fast;
        slow=fast=phead;
        while(fast != NULL && fast->nxt != NULL){
                slow=slow->nxt;
                fast=fast->nxt->nxt;
        }
        struct node *secondhalf=slow->nxt;
        struct node *temp=reverse(secondhalf);
        struct node *firsthalf=phead;
        int palindrome=1;
        while(temp!=NULL){
              if(firsthalf->val != temp->val){
                   palindrome=0;
                   break;
              }
              firsthalf=firsthalf->nxt;
              temp=temp->nxt;
        }
        return palindrome;
}


int main(){
        int total,node;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the node %d :",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        if(isplaindrome())
                printf("\nPalindrome\n");
        else
                printf("\nNot a palindrome\n");
}
```

## Remove duplicates from the linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        ptrav=phead;
        while(ptrav->nxt != NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pnew;
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
void sorting(){
        struct node *i,*j;
        for(i=phead;i!=NULL;i=i->nxt){
                for(j=i->nxt;j!=NULL;j=j->nxt){
                        if(i->val > j->val){
                                int temp=i->val;
                                i->val=j->val;
                                j->val=temp;
                        }
                }
        }
}

void removeduplicates(){
        struct node *p=phead,*q;
        while(p != NULL && p->nxt != NULL){
                while(p->val == p->nxt->val){
                        q=p->nxt->nxt;
                        if(q == NULL){
                                p->nxt = NULL;
                                break;
                        }
                        p->nxt=q;
                }
                if(p->val != p->nxt->val)
                        p=p->nxt;
        }
}

int main(){
        int total,node;
        printf("Enter the total number of nodes:");
        scanf("%d",&total);
        for(int i=0;i<total;i++){
                printf("Enter the node %d :",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        sorting();
        printf("\nSorted list :");
        display();
        removeduplicates();
        printf("\nList after removing of duplicates:");
        display();
}
```


# Strings :

## Reverse a string without using built-in reverse functions.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int len=strlen(str);
        for(int i=0,j=len-1;i<j;i++,j--){
                char temp=str[i];
                str[i]=str[j];
                str[j]=temp;
        }
        printf("String after reversing:%s\n",str);
}
```

## Palindrome or not 
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int len=strlen(str);
        for(int i=0,j=len-1;i<j;i++,j--){
                if(str[i]!=str[j]){
                        printf("String is not a palindrome\n");
                        found=1;
                        break;
                }
        }
        if(!found)
                printf("String is a palindrome\n");
}
```
## Convert all lowercase characters to uppercase and vice-versa.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string :");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0;str[i]!='\0';i++){
                if(str[i]>='a' && str[i]<='z'){
                        str[i]=str[i]-32;
                }
                else if(str[i]>='A' && str[i]<='Z'){
                        str[i]=str[i]+32;
                }
        }
        printf("String:%s\n",str);
}
```

## Find the ASCII value of each character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string :");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0;str[i]!='\0';i++){
                printf("Ascii character of %c : %d\n",str[i],str[i]);
        }
}
```

## Find the frequency of a given character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string :");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int visited[256]={0};
        for(int i=0;str[i]!='\0';i++){
                visited[str[i]]++;
        }
        for(int i=0;i<256;i++){
                if(visited[i]>0){
                        printf("%c repeats %d times\n",i,visited[i]);
                }
        }
}
```

## Non repeating substring :
```cinclude<stdio.h>
#include<string.h>
int main(){
        char str[100];
        char word[100],largest[100];
        int k=0,max=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                int repeat=1;
                for(int j=0;j<k;j++){
                        if(str[i]==word[j]){
                                repeat=0;
                                break;
                        }
                }
                if(repeat==1){
                        word[k++]=str[i];
                }
                else{
                        word[k]='\0';
                        if(k>max){
                                max=k;
                                strcpy(largest,word);
                        }
                        k=0;
                        word[k++]=str[i];
                }
        }
        word[k]='\0';
        if(k>max){
                strcpy(largest,word);
        }
        printf("Largest=%s\n",largest);
}
```

```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int maxlen=0,start=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                int visited[256]={0};
                int count=0;
                for(int j=i;str[j]!='\0';j++){
                        if(visited[str[j]]==1){
                                break;
                        }
                        else{
                                visited[str[j]]=1;
                                count++;
                        }
                        if(count>maxlen){
                                maxlen=count;
                                start=i;
                        }
                }
        }
        printf("Longest substring:");
        for(int i=start;i<start+maxlen;i++){
                printf("%c",str[i]);
        }
        printf("\n");
}
```

