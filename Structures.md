## Create a structure to represent a student with the following members: name (string), roll number (int), and marks (float). Write a function to display the details of a student. 
```c
##include<stdio.h>
#include<string.h>
struct emp{
        char name[10];
        int rollnumber;
        float marks;
};
void display(char *ptr,int id,float m);
int main(){
        struct emp e[3];
        strcpy(e[0].name,"sai");
        e[0].rollnumber=1;
        e[0].marks=78.9;
        display(e[0].name,e[0].rollnumber,e[0].marks);
        strcpy(e[1].name,"krishna");
        e[1].rollnumber=2;
        e[1].marks=98.7;
        display(e[1].name,e[1].rollnumber,e[1].marks);
        strcpy(e[2].name,"narayan");
        e[2].rollnumber=3;
        e[2].marks=98.6;
        display(e[2].name,e[2].rollnumber,e[2].marks);
}
void display(char *ptr,int id,float m){
        printf("%s %d %f\n",ptr,id,m);
}
```
## 21. Create a structure to represent a book with the following members: title (string), author (string),ISBN (long int), and number of pages (int). Write a function to accept details of a book from the user and store them in a structure variable. 
```c
#include<stdio.h>
#include<string.h>
struct book{
        char title[100];
        char author[100];
        long int ISBN;
        int numofpages;
}e[3];
void display(char *str1,char *str2,long int isbn,int numofpages);
int main(){
        for(int i=0;i<3;i++){
        printf("enter the title:");
        fgets(e[i].title,sizeof(e[i].title),stdin);
        if(e[i].title[strlen(e[i].title)-1]=='\n')
                e[i].title[strlen(e[i].title)-1]='\0';
        printf("enter the author:");
        fgets(e[i].author,sizeof(e[i].author),stdin);
        if(e[i].author[strlen(e[i].author)-1]=='\n')
                e[i].author[strlen(e[i].author)-1]='\0';
        printf("enter the isbn:");
        scanf("%ld",&e[i].ISBN);
        getchar();
        printf("enter num of pages:");
        scanf("%d",&e[i].numofpages);
        getchar();
        }
        for(int i=0;i<3;i++){
        display(e[i].title,e[i].author,e[i].ISBN,e[i].numofpages);
        }
}
void display(char *str1,char *str2,long int isbn,int numofpages){
        printf("%s %s %ld %d\n",str1,str2,isbn,numofpages);
}

```
## 3.Print size of Structure.
```c
#include<stdio.h>
struct node{
        char name[10];
        int empid;
        float sal;
};
int main(){
        struct node e;
        printf("size of the structure:%zu",sizeof(e));
}
```
## 4.Write a program to print size of structure without using sizeof() opeartor.
```c
#include<stdio.h>
struct node{
        char name[10];
        int id;
        float sal;
};
int main(){
        struct node *p=0;
        p++;
        printf("size of the structure=%ld\n",(long)p);
}
```


