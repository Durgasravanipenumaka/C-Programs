## Open file in read mode.
```c
#include<stdio.h>
void main(){
        char a[10];
        int val;
        FILE *fp;
        fp=fopen("file.txt","r");
        if(NULL==fp){
                printf("Failed to open the file");
                return;
        }
        fscanf(fp,"%s %d",a,&val);
        printf("%s %d\n",a,val);
        fclose(fp);
        return;
}
```
## Open the file in write mode.
```c
#include<stdio.h>
void main(){
        FILE *fp;
        fp=fopen("file.txt","w");
        if(fp==NULL){
                printf("failed to open the file");
                return;
        }
        char a[100]="world";
        fprintf(fp,"%s",a);
        fclose(fp);
        return;
}
```
