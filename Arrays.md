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
## Find the largest element in an array using pointer notation.
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
