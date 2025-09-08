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
#include<stdio.h>
#include<string.h>
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
        while(fgets(str,sizeof(str),fp1)!=NULL){
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
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp;
        char ch;
        int inword=0,count=0;
        fp=fopen("abc.txt","r");
        if(fp==NULL){
                printf("Error in opening a file");
                exit(1);
        }
        while((ch=getc(fp))!=EOF){
                if(ch==' '||ch=='\t'||ch=='\n'){
                        inword=0;
                }
                else if(inword==0){
                        inword=1;
                        count++;
                }

        }
        fclose(fp);
        printf("Total Words in file:%d\n",count);
}
```
## 4.Write a C program using file handling to compress a string by replacing consecutive repeating characters with the character followed by their count.
```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
int main(){
        FILE *fpin,*fpout;
        char str[100],res[100];
        fpin=fopen("a.txt","w");
        if(fpin==NULL){
                printf("Error");
                exit(1);
        }
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        fprintf(fpin,"%s",str);
        int len=strlen(str);
        int count=1,k=0;
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==str[i+1])
                        count++;
                else{
                        res[k++]=str[i];
                        if(count>1){
                                res[k++]=count+'0';
                        }
                        count=1;
                }
        }
        res[k]='\0';
        fpout=fopen("res.txt","w");
         if(fpout==NULL){
                printf("Error");
                exit(1);
        }
        fprintf(fpout,"%s",res);
        fclose(fpin);
        fclose(fpout);
}
```

