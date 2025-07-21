## 1.Factorial of a number using recursion.
```c
#include<stdio.h>
int factorial(int x){
        int fact;
        if(x==1)
                return 1;
        fact=x*factorial(x-1);
        return fact;
}
int main(){
        int n,f;
        printf("Enter the number:");
        scanf("%d",&n);
        f=factorial(n);
        printf("factorial of %d = %d",n,f);
}
```
## 2.Fibonacci series of a number using recursion.
```c
#include<stdio.h>
int fibonacci(int x){
        int f;
        if(x<0){
                printf("Invalid input");
                return -1;
        }
        if(x==0)
                return 0;
        if(x==1)
                return 1;
        f=fibonacci(x-1)+fibonacci(x-2);
        return f;
}
int main(){
        int n,f;
        printf("Enter the number:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("%d ",fibonacci(i));
        }
        return 0;
}
```
## 3.Finding prime number using recursion.
```c
#include<stdio.h>
int isprime(int x,int y){
        if(x<2)
                return 0;
        if(y==1)
                return 1;
        if(x%y==0)
                return 0;
        return isprime(x,y-1);
}
int main(){
        int n;
        printf("Enter the number:");
        scanf("%d",&n);
        if(isprime(n,n/2))
                printf("%d is a prime number",n);
        else
                printf("%d is not a prime number",n);
}
```
## 4.Program to display and find out the sum of series.
```c
#include<stdio.h>
int sumofdigits(int n){
    int s=0;
    if(n==1){
        printf("1");
       return 1;
    }
    else{
        s=sumofdigits(n-1);
        printf(" + %d",n);
        return s+n;
    }
}
int main(){
    int sum;
    sum=sumofdigits(5);
    printf("\nSum=%d",sum);
}
```

