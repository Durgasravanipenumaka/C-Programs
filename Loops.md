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
#include<stdio.h>
int main(){
        int num,rev=0,isnegative=0;
        printf("Enter the number:");
        scanf("%d",&num);
        if(num<0){
                num=-num;
                isnegative=1;
        }
        while(num>0){
                rev=(rev*10)+(num%10);
                num=num/10;
        }
        if(isnegative)
                rev=-rev;
        printf("Number after reversing:%d",rev);
}

```
## 5.WRITE A C PROGRAM TO CHECK WHETHER A GIVEN NUMBER IS A PALINDROME IN BOTH DECIMAL AND BINARY REPRESENTATIONS USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int num,rem,arr1[15],arr2[15];
        int temp;
        int flag=1;
        printf("Enter the number:");
        scanf("%d",&num);
        temp=num;
        int rev=0;
        int original=num;
        while(num>0){
                rem=num%10;
                rev=rev*10+rem;
                num=num/10;
        }
        if(original==rev)
                printf("Palindrome\n");
        else
                printf("Not a Palindrome\n");
        int k=0;
        while(temp>0){
                arr1[k++]=temp%2;
                temp=temp/2;
        }
        printf("Binary format of %d is : ",original);
        for(int i=0;i<k;i++){
                printf("%d",arr1[i]);
        }
        int j=0;
        for(int i=k-1;i>=0;i--){
                arr2[j++]=arr1[i];
        }
        printf("\nBinary format of %d after revesing:",original);
        for(int i=0;i<j;i++){
                printf("%d",arr2[i]);
        }
        printf("\n");
        for(int i=0;i<j;i++){
                if(arr1[i]!=arr2[i]){
                        flag=0;
                        break;
                }
        }
        if(flag)
                printf("Two binary formats are equal\n");
        else
                printf("Binary formats are not equal\n");

}
```
