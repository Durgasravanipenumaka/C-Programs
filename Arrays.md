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

