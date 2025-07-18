## 1.Rotate an array by 180 and 360 degrees.
```c
#include<stdio.h>
int main(){
        int arr[10]={2,3,5,6,1,3,2,1,4,5};
        int length=sizeof(arr)/sizeof(arr[0]);
        for(int i=0,j=length-1;i<j;i++,j--){
                int temp;
                temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
        }
        printf("Array in 180 degrees:");
        for(int i=0;i<length;i++){
                printf("%d ",arr[i]);
        }
        for(int i=0,j=length-1;i<j;i++,j--){
                int temp;
                temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
        }
        printf("\nArray in 360 degrees:");
        for(int i=0;i<length;i++){
                printf("%d ",arr[i]);
        }

}
```
## 2.Find the largest element in an array using pointer notation.
```c
#include<stdio.h>
void largest(int arr[],int len){
        int max=*(arr);
        for(int i=0;i<len;i++){
                if(*(arr+i)>max){
                        max=*(arr+i);
                }
        }
        printf("Largest element=%d",max);
}
int main(){
        int arr1[]={4,5,6,7,10,8};
        int length=sizeof(arr1)/sizeof(arr1[0]);
        largest(arr1,length);
}
```
## 3.Write a program to rotate a 3×3 matrix by 90 degrees clockwise.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c],tran[c][r],rev[c][r];
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        tran[j][i]=arr[i][j];
                }
        }
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        rev[i][j]=tran[i][r-1-j];
                }
        }
        printf("Matrix after Rotated to 90 degrees in clockwise\n");
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        printf("%d ",rev[i][j]);
                }
                printf("\n");
        }
}
```
## 4.Write a program to rotate a 3×3 matrix by 90 degrees Anti-clockwise.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c],tran[c][r],rev[c][r];
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        tran[j][i]=arr[i][j];
                }
        }
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        rev[i][j]=tran[c-1-i][j];
                }
        }
        printf("Matrix after Rotated to 90 degrees in anticlockwise\n");
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        printf("%d ",rev[i][j]);
                }
                printf("\n");
        }
}
```
## 5.Write a program to rotate a matrix by 180 degrees.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c],rev[r][c];
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        rev[i][j]=arr[r-1-i][c-1-j];

                }
        }
        printf("Matrix after Rotated to 180 degrees\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        printf("%d ",rev[i][j]);
                }
                printf("\n");
        }
}
```
## 6.Print the address and value of each element in an integer array using pointer arithmetic.
```c
#include<stdio.h>
int main(){
        int arr[]={2,3,4,6,7,8};
        int len=sizeof(arr)/sizeof(arr[0]);
        int *ptr=arr;
        for(int i=0;i<len;i++){
                printf("Address=%p and Values=%d\n",ptr+i,*(ptr+i));
        }
}
```
## 7.Swap two arrays of equal size using pointers.
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={6,7,8,9,10};
        int *p1,*p2;
        int len=sizeof(arr1)/sizeof(arr1[0]);
        p1=arr1;
        p2=arr2;
        for(int i=0;i<len;i++){
                int temp=*(p1+i);
                *(p1+i)=*(p2+i);
                *(p2+i)=temp;
        }
        printf("first array:\n");
        for(int i=0;i<len;i++){
                printf("%d ",arr1[i]);
        }
        printf("\nSecond array:\n");
        for(int i=0;i<len;i++){
                printf("%d ",arr2[i]);
        }

}
```
## 8.Write a C program to print highest sum of adjacent elements in an array.
```c
#include<stdio.h>
int main(){
    int arr[]={1,4,7,2,3,8};
    int sum=0;
    int len=sizeof(arr)/sizeof(arr[0]);
    int max=0;
    for(int i=0;i<len-1;i++){
        sum=arr[i]+arr[i+1];
        if(max<sum){
            max=sum;
        }
    }
    printf("Highest sum=%d",max);
}
```
## 9.Write a program to find the sum of rows and columns of a 2-d array and store the sums in the same array.
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r+1][c+1]={0};
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);\
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        arr[i][c]+=arr[i][j];
                        arr[r][j]+=arr[i][j];
                        arr[r][c]+=arr[i][j];
                }
        }
        for(int i=0;i<=r;i++){
                for(int j=0;j<=c;j++){
                        printf("%d ",arr[i][j]);
                }
                printf("\n");
        }
}
```
## 10.Write a C Program to Print all Non Repeated Elements in an Array.
```c
#include<stdio.h>
int main(){
    int arr[]={2,3,4,5,1,2,6,9,6,4,3};
    int len=sizeof(arr)/sizeof(arr[0]);
    int freq[len];
    for(int i=0;i<len;i++){
        freq[i]=-1;
    }
    for(int i=0;i<len;i++){
        if(freq[i]==-1){
            for(int j=i+1;j<len;j++){
                if(arr[i]==arr[j]){
                    freq[i]=freq[j]=0;
                    break;
                }
            }
        }
    }
    for(int i=0;i<len;i++){
        if(freq[i]!=0)
           printf("%d ",arr[i]);
    }
}
```
## 11.Write a program in C to print all unique elements in an array.
```c
#include<stdio.h>
int main(){
    int arr[]={2,3,4,5,1,2,6,9,6,4,3};
    int len=sizeof(arr)/sizeof(arr[0]);
    int freq[len];
    for(int i=0;i<len;i++){
        freq[i]=-1;
    }
    for(int i=0;i<len;i++){
        if(freq[i]==-1){
            for(int j=i+1;j<len;j++){
                if(arr[i]==arr[j]){
                    freq[j]=0;
                    break;
                }
            }
        }
    }
    for(int i=0;i<len;i++){
        if(freq[i]!=0)
           printf("%d ",arr[i]);
    }
}
```
## 12.Write a program to find the sum of rows and columns of a 2-d array and store the sums in the same array.
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
    int arr[r+1][c+1]={0};
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            arr[i][c]+=arr[i][j];
            arr[r][j]+=arr[i][j];
            arr[r][c]+=arr[i][j];
        }
    }
    for(int i=0;i<=r;i++){
        for(int j=0;j<=c;j++){
            printf("%d ",arr[i][j]);
        }
        printf("\n");
    }
    
}
```
## 13.Maximum Average of Subarrays of Size 4.
```c
#include<stdio.h>
int main(){
        int arr1[6]={1,12,-5,-6,50,3};
        int arr2[6];
        int sum=0,n=0,k=4;
        float len,max;
        len=sizeof(arr1)/sizeof(arr1[0]);
        for(int i=0;i<=len-k;i++){
                sum=0;
                for(int j=i;j<(i+k);j++){
                        sum=sum+arr1[j];
                }
                arr2[n++]=(sum/4);
        }

        for(int i=0;i<n;i++){
                printf("%d ",arr2[i]);
        }
        max=arr2[0];
        for(int i=0;i<n;i++){
                if(arr2[i]>max)
                        max=arr2[i];
        }
        printf("\naverage sum=%f",max);
}
```



