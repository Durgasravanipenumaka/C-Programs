## Create a structure to represent a student with the following members: name (string), roll number (int), and marks (float). Write a function to display the details of a student. 
```c
#include<stdio.h>
#include<string.h>
struct student{
        char name[10];
        int rollNo;
        float Marks;
};
void display(struct student s){
        printf("Name:%s\n",s.name);
        printf("Roll NO:%d\n",s.rollNo);
        printf("Marks:%.2f\n",s.Marks);
}
int main(){
        struct student s[3];
        for(int i=0;i<3;i++){
                printf("Enter the name:");
                fgets(s[i].name,sizeof(s[i].name),stdin);
                if(s[i].name[strlen(s[i].name)-1]=='\n')
                        s[i].name[strlen(s[i].name)-1]='\0';
                printf("Enter the Roll no:");
                scanf("%d",&s[i].rollNo);
                getchar();
                printf("Enter the Marks:");
                scanf("%f",&s[i].Marks);
                getchar();
        }
        printf("-----Student Details-----\n");
        for(int i=0;i<3;i++){
                display(s[i]);
        }
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
## 5.. Define a structure to represent a point in 2D space with x and y coordinates (both integers). Write a function to check if two points are equal (have the same x and y coordinates).
```c
#include<stdio.h>
struct point{
        int x;
        int y;
};
int equalornot(struct point p1,struct point p2){
        if(p1.x==p2.x && p1.y==p2.y)
                return 1;
        else
                return 0;
}
int main(){
        struct point s1,s2;
        printf("Enter the coordinates of first point(x,y):");
        scanf("%d %d",&s1.x,&s1.y);
        printf("Enter the coordinates of second point(x,y):");
        scanf("%d %d",&s2.x,&s2.y);
        if(equalornot(s1,s2))
                printf("The points are equal");
        else
                printf("The points are not equal");
}
```
