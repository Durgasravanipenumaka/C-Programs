## 1.Write a C program to demonstrate use of bitwise opeartors.
```c
#include<stdio.h>
int main(){
        int a,b;
        printf("Enter the a and b values:");
        scanf("%d %d",&a,&b);
        printf("a & b=%d\n",a & b);
        printf("a | b=%d\n",a | b);
        printf("a ^ b=%d\n",a ^ b);
        printf("~a=%d\n",~a);
        printf("b<<1=%d\n",b<<1);
        printf("b>>1=%d\n",b>>1);
        return 0;
}
```
## 2.Set the ith bit of a number.
```c
#include<stdio.h>
void kthbit(int n,int k){
        if((n&(1<<(k-1)))!=0)
                printf("yes");
        else
                printf("no");
}
int main(){
        int n,k;
        printf("enter the n value:");
        scanf("%d",&n);
        printf("enter the kth value:");
        scanf("%d",&k);
        kthbit(n,k);
}
```
## 3.Set the ith bit of a number.
```c
#include<stdio.h>
int setithbit(int n,int i){
        return (1<<(i-1)|n);
                        }
int main(){
      int n,i,num;
      printf("Enter the n value:");
      scanf("%d",&n);
      printf("Enter the ith value:");
      scanf("%d",&i);
      num=setithbit(n,i);
      printf("Number after set the ith bit:%d",num);
      }
```
## 4. clear the ith bit of a number.
```c
#include<stdio.h>
int clearithbit(int n,int i){
        int mask=~(1<<(i-1));
        return (mask&n);
}
int main(){
        int n,i,num;
        printf("Enter the n value:");
        scanf("%d",&n);
        printf("Enter the i value:");
        scanf("%d",&i);
        num=clearithbit(n,i);
        printf("Number after clearing the ith bit:%d",num);
}
```
## 5. Remove the last set bit of a number.
```c
#include<stdio.h>
int removelastbit(int n){
        return (n&(n-1));
}
int main(){
        int n,num;
        printf("Enter the number:");
        scanf("%d",&n);
        num=removelastbit(n);
        printf("Number after removing last bit:%d",num);
}
```
## 6.Find whether a number is even or odd
```c

