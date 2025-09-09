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
## 5.Implement a file management system that allows users to create, read, update, and delete files using C functions.
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void createfile(){
        char filename[100],str[100];
        FILE *fp;
        printf("Enter the filename:");
        scanf("%s",filename);
        fp=fopen(filename,"w");
        if(fp==NULL){
                printf("Error");
                return;
        }
        printf("File %s created successfully",filename);
        printf("\nEnter the string:");
        getchar();
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        fprintf(fp,"%s",str);
        fclose(fp);
}
void readfile(){
        char filename[100],ch;
        FILE *fp;
        printf("\nEnter the filename:");
        scanf("%s",filename);
        fp=fopen(filename,"r");
        if(fp==NULL){
                printf("Error");
                return;
        }
        printf("Contents of file:");
        while((ch=fgetc(fp))!=EOF){
                putchar(ch);
        }
        fclose(fp);
}
void appendfile(){
        char filename[100],data[100];
        FILE *fp;
        printf("\nEnter the filename:");
        scanf("%s",filename);
        fp=fopen(filename,"a");
        if(fp==NULL){
                printf("Error");
                return;
        }
        int i=0;
        printf("append the string that ends with !:");
        while((data[i]=getchar())!='!'){
                i++;
        }
        data[i]='\0';
        fprintf(fp,"%s",data);
        fclose(fp);
}
void deletefile(){
        char filename[100];
        printf("Enter the file name:");
        scanf("%s",filename);
        if(remove(filename)==0)
                printf("File removed successfully");
        else
                printf("Error in removing file");
}

int main(){
        int choice;
        printf("----File Management System------\n");
        printf("1.Create file\n");
        printf("2.Read file\n");
        printf("3.Append file\n");
        printf("4.Delete file\n");
        printf("Enter the choice:");
        scanf("%d",&choice);
        switch(choice){
                case 1 :
                        createfile();
                        break;
                case 2 :
                        readfile();
                        break;
                case 3 :
                        appendfile();
                        break;
                case 4 :
                        deletefile();
                        break;
                default :
                        printf("Invalid");
        }
}
```
## 6.Write a program that checks whether a file exists or not.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        char filename[100];
        printf("Enter the filename:");
        scanf("%s",filename);
        FILE *fp;
        fp=fopen(filename,"r");
        if(fp==NULL){
                printf("Error in opening file");
                exit(1);
        }
        else{
                printf("File Opened successfully");
                fclose(fp);
        }
}
```
## 7.Create a C program to rename a file.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        char newname[100];
        printf("Enter the newname of file:");
        scanf("%s",newname);
        if(rename("cde.txt",newname)==0)
                printf("File name changed successfully");
        else
                printf("Error");
}
```
## 8. Develop a C program that handles errors while opening files and prints appropriate error messages.
```c
#include<stdio.h>
#include<errno.h>
#include<string.h>
int main(){
        FILE *fp;
        fp=fopen("Cde.txt","r");
        if(fp==NULL){
                perror("File doesnot open\n");
                printf("Error:%s\n",strerror(errno));
                return 1;
        }
        printf("File opened successfully");
}
```
