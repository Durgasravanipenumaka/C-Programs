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
##
