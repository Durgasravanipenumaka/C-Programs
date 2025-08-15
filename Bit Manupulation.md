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
## 2.Write a C program to check whether the k-th bit of a given integer n is set (i.e., 1) or not.
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
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        evenorodd(num);
}
```
## 11.Check whether the given number is power of 2 or not.
```c
#include<stdio.h>
int ispowerof2(int n){
        if(n>0&&(n&(n-1))==0)
                printf("%d is power of 2\n",n);
        else
                printf("%d is not a power of 2\n",n);
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        ispowerof2(num);
}
```
## 12.Write a program to multiply a number by 2.
```c
#include<stdio.h>
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=num<<1;
        printf("%d after multiplied by 2 is %d",num,res);
}
```
## 13.Write a program to divide a number by 2.
```c
#include<stdio.h>
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=num>>1;
        printf("%d after divided by 2 is %d",num,res);
}
```
## 14.Write a program to swap two numbers without using third variable.
```c
#include<stdio.h>
int main(){
        int a,b;
        printf("Enter the a and b numbers:");
        scanf("%d %d",&a,&b);
        printf("Numbers before swapping:%d %d\n",a,b);
        a=a^b;
        b=a^b;
        a=a^b;
        printf("Numbers after swapping:%d %d\n",a,b);
}
```
## 15.Write a program to swap lower and higher nibble of a number.
```c
#include<stdio.h>
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        int swap=((num&0x0f)<<4)|((num&0xf0)>>4);
        printf("Orginal numbers:%d\n",num);
        printf("After swapping Nibbles:%d\n",swap);
}
```
## 16.Toggle a given range of bits.For example, take the number 245. The equivalent binary format is 11110101and the range is 4 to 7. So, the output should be 000001010 which is 5 in decimal.
```c
#include<stdio.h>
int main(){
        int num,r,l;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("Enter the staring position:");
        scanf("%d",&l);
        printf("Enter the ending position:");
        scanf("%d",&r);
        int mask=((1<<(r-l+1))-1)<<l;
        int result=num^mask;
        printf("Original number:%d\n",num);
        printf("after toggling bit from %d to %d=%d\n",l,r,result);
}
```



