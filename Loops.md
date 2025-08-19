## 1.WRITE A PROGRAM IN C TO PRINT THE ARMSTRONG NUMBERS BETWEEN 1 AND 1000 USING A FOR LOOP?
```c
#include<stdio.h>
int main(){
    int rem,sum,cube,temp;
    for(int i=0;i<1000;i++){
        temp=i;
        sum=0;
        while(temp>0){
            rem=temp%10;
            cube=rem*rem*rem;
            sum=sum+cube;
            temp=temp/10;
        }
        if(sum==i)
        printf("%d\n",i);
    }
}
```
## 2..WRITE A PROGRAM IN C TO IMPLEMENT A SIMPLE CALCULATOR USING SWITCH-CASE STATEMENTS?
```c
#include<stdio.h>
int c;
 void add(int x,int y){
        c=x+y;
        printf("Addition=%d",c);
    }
    void sub(int x,int y){
        c=x-y;
        printf("Subtraction=%d",c);
    }
    void mult(int x,int y){
        c=x*y;
        printf("Multiplication=%d",c);
    }
    void divi(int x,int y){
        if(y!=0){
        c=x/y;
        printf("Divison=%d",c);
        }
        else
        printf("denominator cannot be zero");
    }
    void mdiv(int x,int y){
        if(y!=0){
             c=x%y;
        printf("Divison=%d",c);
        }
        else
        printf("denominator cannot be zero");
    }
int main(){
    int op;
    int a,b;
    printf("Enter 1 for addition\n");
    printf("Enter 2 for subtraction\n");
    printf("Enter 3 for Multiplication\n");
    printf("Enter 4 for divison\n");
    printf("Enter 5 for Modular divison\n");
    printf("Enter option:");
    scanf("%d",&op);
    printf("Enter a and b values:\n");
    scanf("%d %d",&a,&b);
    switch(op){
        case 1:
             add(a,b);
             break;
        case 2:
             sub(a,b);
             break;
        case 3:
              mult(a,b);
              break;
        case 4:
              divi(a,b);
              break;
        case 5:
              mdiv(a,b);
              break;
        default:
            printf("Inavalid");
    }
    
}
```
## 3.WRITE A C PROGRAM TO FIND THE SUM OF ALL PRIME NUMBERS BETWEEN 1 AND 1000 USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
    int found=1;
    for(int i=2;i<=1000;i++){
        found=1;
        for(int j=2;j<i/2;j++){
            if(i%j==0){
                found=0;
                break;
            }
        }
        if(found==1)
        printf("%d ",i);
    }
}
```
## 4.Write a C Program to reverse a given number.
```c

