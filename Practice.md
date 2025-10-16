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
## Write a C program to perform k Right rotations on an array.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5};
        int k;
        int len=sizeof(arr)/sizeof(arr[0]);
        printf("Enter the number of rotation:");
        scanf("%d",&k);
        for(int i=0;i<k;i++){
                int temp=arr[len-1];
                for(int j=len-1;j>0;j--){
                        arr[j]=arr[j-1];
                }
                arr[0]=temp;
        }
        for(int i=0;i<len;i++){
                printf("%d ",arr[i]);
        }
        printf("\n");
}
```
## avoid race condition using spinlock.
```c
#include<stdio.h>
#include<pthread.h>
pthread_spinlock_t lock;
int count=0;
void *increment(void *arg){
        int tid=*(int *)arg;
        printf("Thread %d waiting for spin lock..\n",tid);
        pthread_spin_lock(&lock);
        for(int i=0;i<5;i++){
                count++;
        }
        printf("Thread %d updated count value:%d\n",tid,count);
        pthread_spin_unlock(&lock);
        return NULL;
}
int main(){
        int n;
        printf("Enter the n value:");
        scanf("%d",&n);
        pthread_t th[n];
        int threadid[n];
        pthread_spin_init(&lock,PTHREAD_PROCESS_PRIVATE);
        for(int i=1;i<=n;i++){
                threadid[i]=i;
                pthread_create(&th[i],NULL,increment,&threadid[i]);
        }
        for(int i=1;i<=n;i++){
                pthread_join(th[i],NULL);
        }
        pthread_spin_destroy(&lock);
        printf("Final count value:%d\n",count);
}
```

## Rotate matrix 90 degree clockwise.
```c


