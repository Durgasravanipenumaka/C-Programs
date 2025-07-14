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
## 6.Write a C program to clear 4th and 2nd bit of the number input by the user.
```c
#include<stdio.h>
int clear4and2bit(int a){
        int result;
        result = a & ~ ((1<<3)|(1<<1));
        return result;
}
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=clear4and2bit(num);
        printf("result=%d",res);
}
```
## 7.Write a program to find state of 3rd and 2nd bit.
```c
#include<stdio.h>
void checkbit(int num){
        if(((1<<2)&num)!=0)
                printf("state of the 3rd position is 1\n");
        else
                printf("state of the 3rd position is 0\n");
        if(((1<<1)&num)!=0)
                printf("state of the 2nd position is 1\n");
        else
                printf("state of the 2nd position is 0\n");
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        checkbit(num);
}
```
## 8.Write a program to toggle 7th,5th,4th and 1st bits.
```c
#include<stdio.h>
int toggle(int n){
        int mask,res;
        mask=((1<<6)|(1<<4)|(1<<3)|(1<<0));
        res=n^mask;
        return res;
}
int main(){
        int num,result;
        printf("Enter the number:");
        scanf("%d",&num);
        result=toggle(num);
        printf("Result=%d\n",result);
}
```
## 9.Write a program to count number of set bits in a number input by user.
```c
#include<stdio.h>
int countsetbit(int n){
        int count;
        while(n>0){
                if(n&1)
                        count++;
                n=n>>1;
        }
        return count;
}
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=countsetbit(num);
        printf("Number of set bits=%d",res);
}
```
## 10.Find whether the number is odd or even
```c
#include<stdio.h>
void evenorodd(int n){
        if(n&1)
                printf("Odd Number");
        else
                printf("Even Number");
}
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        evenorodd(num);
}
```



