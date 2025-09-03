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
## 1.Write a C program to read content from one file and write it to another file.
```c
#include<stdlib.h>
int main(){
        FILE *fp1,*fp2;
        char str[100];
        char ch;
        fp1=fopen("abc.txt","r");
        if(fp1==NULL){
                printf("Error in opening file");
                return 0;
        }
        fp2=fopen("cde.txt","w");
        if(fp2==NULL){
                printf("Error in opening file");
                return 0;
        }
        while(!feof(fp1)){
        fgets(str,sizeof(str),fp1);
        fprintf(fp2,"%s",str);
        }
        fclose(fp1);
        fclose(fp2);
}
```
## 2.Create a program that reads integers from a file and calculates their sum, then writes the sum to another file.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp1,*fp2;
        int num,sum=0;
        fp1=fopen("int.txt","r");
        if(fp1==NULL){
                printf("Error in opening file");
                exit(1);
        }
        while(fscanf(fp1,"%d",&num)==1){
                sum=sum+num;
        }
        fclose(fp1);
        fp2=fopen("sum.txt","w");
        if(fp2==NULL){
                printf("Error in opening file");
                exit(1);
        }
        fprintf(fp2,"%d",sum);
        fclose(fp2);
}
```
## 3. Develop a program to read a text file and count the number of words in it.
```c


